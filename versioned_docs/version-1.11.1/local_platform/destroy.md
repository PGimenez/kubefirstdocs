---
sidebar_position: 8
---

# Destroy Kubefirst Local

## Automated teardown

Before you attempt to recreate a Kubefirst local platform, you'll need to destroy your k3d cluster and the git repositories that we created for you using this command:

```shell
kubefirst local destroy
```

## Localhost file cleanup

You can clean kubefirst files from your localhost by running:

```shell
kubefirst clean
```

This command will remove the following content:

- ```~/.kubefirst```
- ```~/.k1/*```

## Removing CA of trusted store

If you executed the steps of install the CA of MkCert (described on Install process) and if you want, you can also clean your trusted store.

```shell
mkcert -uninstall
```

But when you will execute ```kubefirst local``` posteriorly, to have the certificates trusted in browsers again, you will need to execute ```mkcert -install``` again.

<br></br>

:::tip Avoid tools re-download

The kubefirstCLI downloads some tools used during cluster provisioning, for example, Terraform, Helm, and Kubectl, in versions compatible with Kubefirst and stores them in the K1 folder. If you are using Kubefirst to demo in conferences or using poor connections (mobile, hotels) you should consider using this additional flag ```--preserve-tools``` for each cycle of create/destroy. This will preserve tools downloaded and will save time and network bandwidth during cluster provisioning.

:::