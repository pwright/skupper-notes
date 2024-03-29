# Changelog

This document provides a summary of all notable changes by release.
For a detailed view of what’s changed, refer to the repository’s [commit history](https://gitlab.com/antora/expand-path-helper/commits/main).

## 2.0.0 (2021-07-17)

* **Breaking:** move context arguments to an options object (aka keyword arguments) (#4)
* allow base to be specified as the second positional argument (#7)
* resolve empty path to value of start argument (#5)
* allow working directory to be overridden using the cwd argument (#6)
* use npm instead of yarn for development
* expand testing to Node.js 16 on Linux and Node.js on Windows
* configure CI to automate release (#3)

## 1.0.0 (2018-02-27)

* initial stable release
* test cases when parameters are explicitly undefined

## 1.0.0-rc.3 (2018-02-23)

* BREAKING: change order of parameters to `path, start = '~+', dot = '.'`
* link leading dot segment to start value by default
* allow both start and dot parameters to accept an arbitrary path
* allow start and dot parameters to be controlled independently
* rewrite tests to match new parameter order
* update API doc and README
* clarify in README that function generates paths which are system dependent
* add npm package badge to README

## 1.0.0-rc.2 (2018-02-22)

* add third argument to make default prefix for relative path configurable
* use `+~` as default value for default prefix
* add API docs and more examples to README
* switch README to AsciiDoc; add scripts to include Markdown version in package

## 1.0.0-rc.1 (2018-02-22)

* initial release
