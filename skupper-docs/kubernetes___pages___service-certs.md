sid:: encrypting-traffic-pod-router 
# Encrypting traffic from a pod to the Skupper router

This section describes how to apply certificates to encrypt the traffic within a cluster.

By default:

* {Skupper-name} creates certificates to establish links between sites using mutual TLS so that traffic between sites is encrypted. 
To use custom certificates for traffic between sites, see [index.adoc](index.adoc).
* Network traffic between pods and the Skupper router is not encrypted. 

You can use certificates to encrypt traffic between pods and the Skupper router as follows:

* [Exposing services on the {service-network} with Skupper-generated certificates](#exposing-services-on-the-{service-network}-with-skupper-generated-certificates) - does not require that you provide certificates.
* [user-provided-certs](#user-provided-certs) - requires that the certificate authority, and the signed certificates, are distributed across all sites.

**📌 NOTE**\
With both procedures, you reference the certificates when exposing the service on the {service-network}.
If you do not reference certificates, the traffic between pods and the Skupper router is unencrypted.

## Exposing services on the {service-network} with Skupper-generated certificates

A {skupper-name} installation includes a certificate authority which can generate certificates that can be used to encrypt traffic from the pod to the Skupper router.
This procedure describes how to use those certificates in your {service-network}.

* Access to the Kubernetes site where the service is exposed
* Access to the Kubernetes site where the service is called from
* service sync is enabled on both sites

1. Expose the service on the {service-network}:
   1. If you use the `expose` option:

      ```
      $ skupper expose  <target-type> <target-name> --generate-tls-secrets
      ```
      For example, to expose a `backend` deployment using `http2`:
      ```
      $ skupper expose deployment backend --port 8080 --protocol http2 --generate-tls-secrets
      ```
   2. If you use `create` and `bind` options:

      ```
      $ skupper service create <service-name> --generate-tls-secrets
      $ skupper service bind <service-name>  <target-type> <target-name>
      ```
2. Check that the service is available on another site:

   ```
   $ skupper service status
   Services exposed through Skupper:
   ╰─ nghttp2tls (http2 port 443)
   ```

   On this site, a secret is created named `skupper-tls-<service-name>`. 
   The secret contains the generated certificates under `data/ca.crt`, `data/tls.crt`, and `data/tls.key`.
3. Configure components that call the exposed service to use the certificates stored in `skupper-tls-<service-name>`.

   For example, modify a deployment to mount the secret in a container.

   ```
         volumes:
         - name: certs
           secret:
             secretName: skupper-tls-nghttp2tls
   ```
4. Configure the exposed service, which is the component that responds to the request, to use the certificates stored in `skupper-service-client`.

   The `skupper-service-client` secret contains the certificate and private key of the Skupper certificate authority.
   For example, modify a deployment to mount the secret in a container.

   ```
         volumes:
         - name: certs
           secret:
             secretName: skupper-service-client
   ```

sid:: user-provided-certs 
## Exposing services on the {service-network} with user-provided certificates

You can encrypt traffic from the pod to the Skupper router using certificates provided by a certificate authority.

* Access to the Kubernetes site where the service is exposed
* Access to the Kubernetes site where the service is called from
* Certificate authority access (intermediate certificate is sufficient)

1. Create a TLS secret from the certificate authority to store the private key and certificate.

   The required format of the secret is:

   * **`data/ca.crt`**\
   CA TLS certificate
   * **`data/tls.crt`**\
   CA TLS certificate (same certificate as above)
   * **`data/tls.key`**\
   CA Private key

   For example, you might name the secret `ca-tls-secret`:

   ```
   $ kubectl create secret tls ca-tls-secret --key=rootCA.key.pem --cert=rootCA.crt.pem
   $ kubectl patch secret ca-tls-secret -p="{\"data\":{\"ca.crt\": \"$(kubectl get secret ca-tls-secret -o json -o=jsonpath="{.data.tls\.crt}")\"}}"
   ```
2. Create a secret from the signed certificate and private key files:

   The required format of the secret is:

   * **`data/ca.crt`**\
   CA TLS certificate from step 1
   * **`data/tls.crt`**\
   Signed TLS certificate 
   * **`data/tls.key`**\
   Signed Private key

   For example, to encrypt a service named `backend`, you might name the secret `user-tls-backend`:
   ```
   $ kubectl create secret tls user-tls-backend --key <key-path> --cert <cert-path>
   $ kubectl patch secret user-tls-backend  -p="{\"data\":{\"ca.crt\": \"$(kubectl get secret ca-tls-secret -o json -o=jsonpath="{.data.tls\.crt}")\"}}"
   ```
3. Expose the service on the {service-network}:
   1. If you use the `expose` option, you specify the certificate secret and the CA secret, for example:

      ```
      $ skupper expose deployment backend --port 5432 --protocol http2 --tls-cert user-tls-backend --tls-trust ca-tls-secret
      ```
   2. If you use the `create` and `bind` options:

      ```
      $ skupper service create backend 5432 --tls-cert user-tls-backend
      $ skupper bind deployment backend  --port 5001  --protocol http2 --tls-trust ca-tls-secret
      ```
