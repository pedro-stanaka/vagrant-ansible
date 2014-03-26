VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"
  config.vm.network "private_network", ip: "192.168.13.37"
  config.vm.synced_folder ".", "/vagrant", :nfs => true

  config.vm.provision "ansible" do |ansible|
    ansible.limit = 'all' # Added to let Ansible connect (multiple times) to all hosts from the inventory file
    ansible.playbook = "ansible/development.yml"
    ansible.inventory_path = "ansible/hosts"
  end
end
