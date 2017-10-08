# -*- mode: ruby -*-
# vi: set ft=ruby :


VAGRANT_COMMAND = ARGV[0]
VAGRANT_VERSION = "2"

# User configs
ADMIN_USER = 'camelot'
ADMIN_PATH_SSH_KEY_PUBLIC = '~/.ssh/id_rsa_vm.pub'
ADMIN_PATH_SSH_KEY_PRIVATE = '~/.ssh/id_rsa_vm'


Vagrant.configure(VAGRANT_VERSION) do |config|

  # Connect ssh with admin user
  if VAGRANT_COMMAND == 'ssh'
    config.ssh.username = "camelot"
    config.ssh.private_key_path = ADMIN_PATH_SSH_KEY_PRIVATE
    config.ssh.forward_agent = true
  end

  config.vm.box = "ubuntu/trusty64"

  config.vm.provision "ansible" do |ansible|
    ansible.host_vars = {
        "default"=> {"ansible_python_interpreter" => "/usr/bin/python3"}
    }
    ansible.playbook = "site.yml"
  end


end
