# -*- mode: ruby -*-
# vi: set ft=ruby :

# TODO: add ruby debugger
# TODO: test raw ruby code before using with Vagrantfile
uname = `uname -s`.chomp

Vagrant.configure('2') do |config|
  config.ssh.max_tries = 40
  config.ssh.timeout   = 120
end

vagrantfiles = %w[vagrant/Vagrantfile.qemu vagrant/Vagrantfile.libvert]
vagrantfiles.each do |vagrantfile|
if uname == 'Darwin'
    load File.expand_path('vagrant/Vagrantfile.qemu')
else
    load File.expand_path('vagrant/Vagrantfile.libvert')
end
