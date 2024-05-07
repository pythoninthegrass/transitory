# -*- mode: ruby -*-

ENV['VAGRANT_LOG'] = 'info'
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'qemu'
ENV['VAGRANT_EXPERIMENTAL'] = "cloud_init,disks"

Vagrant.configure("2") do |config|
  config.env.enable
  config.vm.box = "perk/ubuntu-20.04-arm64"     # debian/bullseye64 | generic/fedora39

  config.vm.provider "qemu" do |qe|
    # qe.arch = "x86_64"
    qe.arch = "aarch64"
    qe.machine = "virt,accel=hvf,highmem=off"
    qe.cpu = "cortex-a72"
    qe.memory = "2G"
    qe.smp = "cpus=2,sockets=1,cores=2,threads=1"
    qe.net_device = "virtio-net-pci"
    qe.extra_netdev_args = "net=192.168.8.0/24,dhcpstart=192.168.8.10"
    qe.ssh_port = "22222"
    qe.machine = "virt,accel=hvf,highmem=off"
  end

#   TODO: these are ignored by qemu provider
#   config.vm.network "forwarded_port", guest: 53, host: 53, protocol: "tcp", auto_correct: true
#   config.vm.network "forwarded_port", guest: 53, host: 53, protocol: "udp", auto_correct: true

#   smb_host = ENV['SMB_HOST'] || "127.0.0.1"
#   config.vm.synced_folder ".", "/vagrant", type: "smb", smb_host: smb_host, disabled: true

#   TODO: debug
#   cloud_config = "cloud-init.yml"
#   config.vm.cloud_init :user_data, content_type: "text/cloud-config", path: cloud_config
#   config.vm.cloud_init :user_data do |cloud_init|
#     cloud_init.content_type = "text/cloud-config"
#     cloud_init.path = cloud_config
#   end

# TODO: test after adding cloud-init
#   config.vm.provision "ansible" do |ansible|
#     ansible.playbook = "playbook.yml"
#   end

end
