enix/elastic-repo for Ansible
=================

A role for deploying softare repository from [elastic.co](http://www.elastic.co). It provide Elastic Search, Logstash and Kibana software suite.

Supports
--------

Supported targets:

- Debian 8 "Jessie"
- RedHat EL 6/7

Dependencies:

- None


Usage
-----

Clone this repo into your roles directory:

    $ git clone ssh://gitlab.enix.org/ansible/ansible-elastic-repo.git roles/elastic-repo

Or use Ansible galaxy requirements.yml, or integrated Dependencies into role meta informations.

And add it to your play's roles:

    - hosts: ...
      roles:
        - $role
        - ...

This roles comes preloaded with almost every available default. You can override each one in your hosts/group vars, in your inventory, or in your play. See the annotated defaults in `defaults/main.yml` for help in configuration. All provided variables start with `elastic_`.

You can also use the role as a playbook. You will be asked which hosts to provision, and you can further configure the play by using `--extra-vars`.

    $ ansible-playbook -i inventory --extra-vars='{...}' main.yml


Still to do
-----------

- Make a var to install either local GPG key using file or by default with external url
- Make it compatible with Ubuntu distributions and newer debian releases (Using generated apt repo informations)
- Make tests working on all systems
- Relabel debian: / RedHat: tasks


Changelog
---------

### 0.1

Initial version.
