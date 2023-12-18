# vagrant-k3sbox

[![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/dmotte/vagrant-k3sbox/release.yml?branch=main&logo=github&style=flat-square)](https://github.com/dmotte/vagrant-k3sbox/actions)
[![Vagrant Cloud](https://img.shields.io/badge/vagrant-dmotte/k3sbox-blue?logo=vagrant&style=flat-square)](https://app.vagrantup.com/dmotte/boxes/k3sbox)

:package: **Debian Vagrant box** with **K3s** configured as a **single-node**, installed using the official [Bash script](https://docs.k3s.io/quick-start).

> :package: This box is also on **Vagrant Cloud** as [`dmotte/k3sbox`](https://app.vagrantup.com/dmotte/boxes/k3sbox).

## Usage

See https://github.com/dmotte/misc/blob/main/examples/vagrant-ansible-provisioner for inspiration on how you could use this box.

If you want to [install Helm](https://helm.sh/docs/intro/install/#from-script) inside the VM:

```ruby
config.vm.provision "shell", inline: <<-SHELL
    bash <(curl -fsSL https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3)
SHELL
```
