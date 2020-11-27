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
  config.vm.provision "shell", inline: "pip3 install --upgrade ansible==#{ vagrant_config['ansible_version'] }"
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
  end
end
