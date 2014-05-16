vagrant-docker-centos-minimal
=============================

Vagrant setting to up centos6 docker container with only sshd, puppet.

## Setting up

    $ git clone git://github.com/tnmt/vagrant-docker-centos-minimal.git

and vagrant up with `--provider=docker`.

    $ cd vagrant-docker-centos-minimal
    $ vagrant up --provider=docker 

now you can login container via ssh using `vagrant ssh`
