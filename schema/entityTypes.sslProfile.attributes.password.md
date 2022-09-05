# entityTypes.sslProfile.attributes.password

'The password that unlocks the certificate key. You can specify the password by specifying an environment variable that stores the password, a file that stores the password, or by entering the password in clear text. To use an environment variable, specify ''password: env:<var>''. Use this option with caution, because the environment of other processes is visible on certain platforms (for example, ps on certain Unix OSs). To use a file, specify ''password: file:<absolute-path-to-file>''. This option is the most secure, because permissions can be set on the file that contains the password. To specify the password in clear text, specify ''password: pass:<password>'', or ''password: literal:<password>'', or ''password: <password>''. This option is insecure, so it should only be used if security is not a concern.'
