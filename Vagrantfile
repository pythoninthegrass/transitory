# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['VAGRANT_LOG'] = 'info'
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'qemu'

Vagrant.configure("2") do |config|
  config.env.enable
  # perk/ubuntu-20.04-arm64 | debian/bullseye64 | generic/fedora39
  config.vm.box = "debian/bullseye64"

  smb_host = ENV['SMB_HOST'] || "127.0.0.1"
  config.vm.synced_folder ".", "/vagrant", type: "smb", smb_host: smb_host, disabled: true

  config.vm.provider "qemu" do |qe|
    # "x86_64" | "aarch64"
    qe.arch = "aarch64"
    qe.machine = "virt,accel=hvf,highmem=off"
    qe.cpu = "cortex-a72"
    qe.memory = "2G"
    qe.smp = "cpus=2,sockets=1,cores=2,threads=1"
    qe.net_device = "virtio-net-pci"
    qe.ssh_port = "22222"
    qe.machine = "virt,accel=hvf,highmem=off"
  end

  config.vm.provision "docker" do |d|
    d.run "hello-world"
  end
end
