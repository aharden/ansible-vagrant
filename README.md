# Vagrant-Powered Ansible Workspace for AWS provisioning

## Reference

[DV Dasari: Use Ansible for AWS Provisioning and Configuration Management](http://dasari.me/2016/08/26/ansible-for-aws-provisioning-configuration-management.html)

## Requirements

[Vagrant](https://www.vagrantup.com/)

## Layout

The `playbook.yml` and `files`, `group_vars/` & `templates/` directories in the root control the configuration of the Vagrant machine.  The environment contained in the `ansible/` directory is the instance used by the Vagrant machine.

## Prepare

`group_vars/all` should be created on your instance with your own AWS credentials supplied for the corresponding variables.

`files/awsprivatekey.txt` should be edited on your instance with your own AWS EC2 key pair's private key (required for EC2 instance deployment)

## Activate

`vagrant up` and `vagrant ssh` into your virtual Ansible development environment.

After VM has been created, you can run `vagrant provision` to adjust the running configuration when required.  It's recommended to run `vagrant provision` every time the VM is resumed after creation.  (See below.)

## Adjust

If your Vagrant machine is suspended, its time can become out of sync, and AWS
modules may fail to connect after it is resumed.  Run:

`sudo ntpdate time.nist.gov`

to synchronize the Vagrant machine's clock after it resumes.

This command is included in a `vagrant provision` run.

## Acknowledgement

Thanks to [DV Dasari](https://github.com/dv2) for inspiring this toolset.
