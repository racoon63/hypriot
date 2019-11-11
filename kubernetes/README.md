# Kubernetes on hypriot

## Supported Kubernetes versions

* `v1.14.2`

List the available versions for `kubelet`, `kubectl`, `kubeadm` on hypriot with:

```bash
apt-cache madison kubelet
apt-cache madison kubectl
apt-cache madison kubeadm
```

Install specific version with:

```bash
apt-get install -y kubelet=1.14.2 kubectl=1.14.2 kubeadm=1.14.2
```

## Docker

Kubernetes supports only specific versions of docker. The latest supported version is `18.09.0`. The latest image of hypriot (`1.11.0`) has docker already installed in version `19.04.0`. So you have to downgrade it.

### Downgrade Docker

First remove the installed docker package:

```bash
apt-get remove docker
```

Add the mirror for Debian Stretch. Currently there is no Docker package for Debian (10) Buster.

Install Docker in specific version:

```bash
apt-get install -y docker-ce=5:18.09.0~3-0~raspbian-stretch docker-ce-cli=5:18.09.0~3-0~raspbian-stretch
```

## CNI

Following CNI are supported:

* flannel

## Troubleshooting

Can not access DaemonSet:

run `iptables -A FORWARD -j ACCEPT` as root to allow forwarding of incoming traffic to the pods.
