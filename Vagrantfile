Vagrant.configure("2") do |config|
  config.vm.box = "geerlingguy/centos7"
  config.vm.synced_folder ".", "/vagrant"
  config.vm.synced_folder "./ansible", "/home/vagrant/ansible"
  config.vm.provision "ansible_local" do |ansible|
    # ansible.verbose = "v"
    ansible.install_mode = "pip"
    ansible.version = "2.8.12"
    ansible.playbook = "provisioning/playbook.yml"
  end
end
