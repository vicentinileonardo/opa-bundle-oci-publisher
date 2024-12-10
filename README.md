# OPA Bundle OCI Publisher

## Overview

This repository contains a GitHub Action that builds and pushes an OPA bundle to an OCI registry.
It serves as a template for building and pushing OPA bundles to an OCI registry.

## How to use

- Change the variable `REGISTRY` in the file `.github/workflows/release.yml` to the registry you want to push the bundle to. Default is `docker.io`.

- Change the variable `REPOSITORY` in the file `.github/workflows/release.yml` to the repository you want to push the bundle to. Default is `your-repository`.

- Create GitHub repository secrets for the following:
    + `REGISTRY_USERNAME`
    + `REGISTRY_PASSWORD`
    + `REGISTRY_NAMESPACE`
(For individual accounts, `REGISTRY_NAMESPACE` is the same as the `REGISTRY_USERNAME`.)

- In order to trigger the GitHub Action, you need to push a tag to the repository, for example:
```bash
git commit --allow-empty -m "Whatever (v0.1.0)"
git tag -a 0.1.0 -m "Whatever (v0.1.0)"
git push origin main --tags
```

## References

- [OPA Bundles in OCI registries](https://www.openpolicyagent.org/docs/latest/management-bundles/#oci-registry)