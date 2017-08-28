Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"
  config.vm.synced_folder "./ansible", "/home/vagrant/ansible"
  config.vm.provision "ansible" do |ansible|
    # ansible.verbose = "v"
    ansible.playbook = "provisioning/playbook.yml"
  end
end
