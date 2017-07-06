Vagrant.configure("2") do |config|
  config.vm.define "server1" do |machine|
    machine.vm.hostname = "server1"
    machine.vm.box = "bento/ubuntu-16.04"
    machine.vm.provision :ansible do |ansible|
      # Specific call out to remove all limits
      ansible.limit = "all"
      ansible.playbook = "playbook.yml"
      ansible.groups = {
        "webservers" => ["server1"]
      }
    end
  end
end
