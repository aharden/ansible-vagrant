Vagrant.configure("2") do |config|
  config.vm.box = "geerlingguy/centos8"
  config.vm.synced_folder ".", "/vagrant"
  config.vm.synced_folder "./ansible", "/home/vagrant/ansible"
  config.vm.provision "shell", inline: "pip3 install --upgrade ansible==2.8.17"
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
  end
end
