# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "debian/bookworm64"

    config.vm.hostname = "k3sbox"

    config.vm.provision "shell", inline: <<-SHELL
        apt-get update; apt-get install -y curl
        bash <(curl -fsSL https://get.k3s.io)
    SHELL

    config.vm.provision "shell", privileged: false, inline: <<-SHELL
        install -Dm600 <(sudo kubectl config view --raw) ~/.kube/config
        echo 'export KUBECONFIG="$HOME/.kube/config"' >> ~/.bashrc
    SHELL

    config.ssh.insert_key = false # This is usually recommended for base boxes
end
