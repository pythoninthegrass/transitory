# -*- mode: ruby -*-

Vagrant.configure("2") do |config|
#   config.vm.box = "centos/7"
#   config.vm.box = "perk/ubuntu-20.04-arm64"
  config.vm.box = "debian/bullseye64"

  config.vm.provider "qemu" do |qe|
    # qe.arch = "x86_64"
    qe.arch = "aarch64"
    qe.cpu = "cortex-a72"
    qe.memory = "2G"
    qe.smp = "cpus=2,sockets=1,cores=2,threads=1"
    qe.net_device = "virtio-net-pci"
    qe.extra_netdev_args = "net=192.168.8.0/24,dhcpstart=192.168.8.10"
    qe.ssh_port = "22222"
    qe.machine = "virt,accel=hvf,highmem=off"
  end

#   config.vm.network "forwarded_port", guest: 80, host: 8080

  smb_host = ENV['SMB_HOST'] || "127.0.0.1"
  config.vm.synced_folder ".", "/vagrant", type: "smb", smb_host: smb_host, disabled: true

#   config.vm.provision "ansible" do |ansible|
#     ansible.playbook = "playbook.yml"
#   end
end
