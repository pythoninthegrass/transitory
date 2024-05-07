# transitory

<!-- markdownlint-disable MD022 MD031 MD032 -->

Vagrant playground to test docker and traditional VM deployments.

## Minimum Requirements

* brew dependencies
  ```bash
  brew install qemu gcc libvirt
  ```
* [Vagrant](https://www.vagrantup.com/downloads.html)
  * Plugins
    ```bash
    vagrant plugin install vagrant-env vagrant-qemu
    ```
* [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

## Recommended Requirements

* [taskfile](https://taskfile.dev/#/installation)
* [devbox](https://www.jetify.com/devbox/docs/quickstart/#install-devbox)

## Quickstart

```bash
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
