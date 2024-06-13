# Backend Helm Chart

This is a [Helm Chart](https://helm.sh/docs/topics/charts/) for [Krateo Backend](https://github.com/krateoplatformops/backend).

## Requirements

Krateo Backend needs etcd installed as a storage layer. The easiest way to install it is the following:

```sh
helm install etcd bitnami/etcd --version 10.2.2 \
--set auth.rbac.create=false
kubectl wait --for=condition=Ready=True pod -l app.kubernetes.io/name=etcd --timeout=300s
```

> **Note**
>
> Etcd and Backend must be installed in the same namespace.

## How to install

```sh
helm repo add krateo https://charts.krateo.io
helm repo update krateo
helm install backend krateo/backend
```
