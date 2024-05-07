# transitory

<!-- markdownlint-disable MD022 MD031 MD032 -->

Vagrant playground to test docker and traditional VM deployments.

## Minimum Requirements
* [Vagrant](https://www.vagrantup.com/downloads.html)
  * Plugins
    ```bash
    vagrant plugin install vagrant-env vagrant-qemu vagrant-libvirt
    ```
* [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

## System Requirements
* macOS
  ```bash
  brew install qemu gcc libvirt
  ```
* Fedora
  ```bash
  sudo dnf install -y qemu gcc libvirt libvirt-devel
  ```

## Recommended Requirements
* [taskfile](https://taskfile.dev/#/installation)
* [devbox](https://www.jetify.com/devbox/docs/quickstart/#install-devbox)

## Quickstart
```bash
# Install shell completion
vagrant autocomplete install --bash

# Add a box
vagrant box add fedora/39-cloud-base --provider=libvirt

# Validate the Vagrantfile
vagrant validate

# Start the VM
vagrant up

# SSH into the VM
vagrant ssh

# Stop the VM
vagrant halt

# Destroy the VM (w/o prompt)
vagrant destroy -f
```
