Vagrant.configure("2") do |config|
  config.vm.define "nginx" do |machine|
    machine.vm.hostname = "nginx"
    machine.vm.network "private_network", ip: "192.168.77.21"
    machine.vm.box = "bento/ubuntu-16.04"
    machine.vm.provision :ansible do |ansible|
      # Specific call out to remove and limits
      ansible.limit = "all"
      ansible.playbook = "playbook.yml"
      ansible.groups = {
        "webservers" => ["nginx"]
      }
      ansible.extra_vars = {
        project_name: "nginx",
      }
    end
  end
end
