Vagrant.configure("2") do |config|
  config.vm.provider "docker" do |d|
    d.vagrant_machine = 'docker'
    d.build_dir       = './docker'
    d.cmd             = ['/usr/sbin/sshd', '-D']
    d.has_ssh         = true
  end

  config.ssh.username = "root"
  config.ssh.private_key_path = "./docker/misc/insecure_private_key"
end
