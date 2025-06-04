# Talos Homelab

## Production Setup


## Local Cluster

This creates a Talos local cluster with a custom CNI (non-Flannal):
```
talosctl cluster create --custom-cni-url=https://raw.githubusercontent.com/projectcalico/calico/v3.30.1/manifests/calico.yaml
```

or create one on QEMU:
```
mkdir -p _out/
curl https://github.com/siderolabs/talos/releases/download/<version>/vmlinuz-<arch> -L -o _out/vmlinuz-<arch>
curl https://github.com/siderolabs/talos/releases/download/<version>/initramfs-<arch>.xz -L -o _out/initramfs-<arch>.xz
mkdir -p ~/.talos/clusters
sudo --preserve-env=HOME talosctl cluster create --provisioner qemu
```

and to install argocd:
```
task argocd-deploy
```
