# -*- mode: ruby -*-
# vi: set ft=ruby :


VAGRANT_COMMAND = ARGV[0]
VAGRANT_VERSION = "2"

Vagrant.configure(VAGRANT_VERSION) do |config|

  if VAGRANT_COMMAND == 'ssh'
    config.ssh.username = "camelot"
    config.ssh.private_key_path = "~/.ssh/id_rsa_vm"
    config.ssh.forward_agent = true
  end

  config.vm.box = "ubuntu/trusty64"

  config.vm.provision "ansible" do |ansible|
    ansible.host_vars = {
        "default"=> {"ansible_python_interpreter" => "/usr/bin/python3"}
    }
    ansible.playbook = "playbook.yml"
  end
end
