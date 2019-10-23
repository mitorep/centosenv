Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.network "private_network", ip: "192.168.56.2"
  config.vm.hostname = "centos"
  config.vm.synced_folder "./provision/", "/provision/", create: true

  config.vm.provision "ansible_local" do |ansible|
      ansible.provisioning_path = "/provision/"
      ansible.become = true
      ansible.playbook = "init.yml"
  end
end