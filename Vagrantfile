# Reference: https://stackoverflow.com/a/26394449
# encoding: utf-8
# -*- mode: ruby -*-
# vi: set ft=ruby :

require 'yaml'

current_dir     = File.dirname(File.expand_path(__FILE__))
configs         = YAML.load_file("#{current_dir}/config.yaml")
vagrant_config  = configs['configs'][configs['configs']['use']]#[configs['configs']['use']]

Vagrant.configure("2") do |config|
  config.vm.box = vagrant_config['vagrant_box']
  config.vm.synced_folder ".", "/vagrant"
  config.vm.synced_folder "./ansible", "/home/vagrant/ansible"
  config.vm.provision "shell", inline: "dnf update -y"
  #config.vm.provision "shell", inline: "dnf remove python36 -y"
  config.vm.provision "shell", inline: "dnf install python38 -y"
  config.vm.provision "shell", inline: "python3.8 -m pip install --upgrade pip"
  config.vm.provision "shell", inline: "python3.8 -m pip install --upgrade ansible==#{ vagrant_config['ansible_version'] }"
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
  end
end
