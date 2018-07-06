eNiXHosting.elastic-repo for Ansible
=================

A role for deploying softare repository from [elastic.co](http://www.elastic.co). It provide Elastic Search, Logstash and Kibana software suite.

Supports
--------

Supported targets:

- Debian 7 "wheezy"
- Debian 8 "Jessie"
- Debian 9 "Stretch"
- Ubuntu 16.04 "Xenial"
- Ubuntu 18.04 "Bionic"
- RedHat EL / CentOS 6
- RedHat EL / CentOS 7

Role Variables
--------------

This roles comes preloaded with almost every available default. You can override each one in your hosts/group vars, in your inventory, or in your play. See the annotated defaults in `defaults/main.yml` for help in configuration. All provided variables start with `elastic_repo__`.

- `elastic_repo__branch: 5.x` - Branch of repository to setup on the host. curently supported: 5.x, 6.x.
- `elastic_repo__local_gpgkey: false` - Use local copy of elastic.co repository GPG key, shipped with the role. Can be usefull for hosts that don't have direct access to internet (using apt-proxy).

Usage
-----

Clone this repo into your roles directory:

    $ git clone ssh://gitlab.enix.org/ansible/ansible-elastic-repo.git roles/elastic-repo

Or use Ansible galaxy requirements.yml

    # eNiXHosting.elastic-repo galaxy role
    - src: eNiXHosting.elastic-repo

And add it to your play's roles:

    - hosts: ...
      roles:
        - elastic-repo

You can also use the role as a playbook. You will be asked which hosts to provision, and you can further configure the play by using `--extra-vars`.

    $ ansible-playbook -i inventory --extra-vars='{...}' main.yml


Still to do
-----------



Changelog
---------

### 2.0
Debian 9 Stretch support
Ubuntu Xenial and Bionic support
Allow 5.x and 6.x repository branches

### 1.0

Initial version.
