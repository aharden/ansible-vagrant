# Vagrant-Powered Ansible Workspace for AWS provisioning

## Reference

[DV Dasari: Use Ansible for AWS Provisioning and Configuration Management](http://dasari.me/2016/08/26/ansible-for-aws-provisioning-configuration-management.html)

## Requirements

[Vagrant](https://www.vagrantup.com/)

### Layout

The `playbook.yml` and `files/`, `group_vars/` & `templates/` directories in the `/provisioning/` directory control the configuration of the Vagrant machine.  The file system in the `/ansible/` directory is used by the Vagrant-Powered Ansible management system.

### Prepare

`/provisioning/group_vars/all` should be created on your instance with your own AWS credentials supplied for the corresponding variables.

`/provisioning/files/awsprivatekey.txt` should be edited on your instance with your own AWS EC2 key pair's private key (required for EC2 instance deployment)

## Activate

`vagrant up` and `vagrant ssh` into your virtual Ansible development environment.

After the Ansible management VM has been created, you can run `vagrant provision` to adjust the running configuration when required.  It's recommended to run `vagrant provision` every time the VM is resumed after creation.  (See below.)

## Acknowledgement

Thanks to [DV Dasari](https://github.com/dv2) for inspiring this toolset.
