# timstaley.voeventdb

An [Ansible][] [role][] that provides an installation of the 
[voeventdb][] database and REST API, served via Apache.


[Ansible]: http://www.ansible.com/configuration-management
[role]: http://docs.ansible.com/ansible/playbooks_roles.html

[voeventdb]: https://github.com/timstaley/voeventdb


## Vagrant VM for testing
To pull up a working VM with voeventdb installed, you will need:

 - vagrant: https://www.vagrantup.com/
 - Ansible: http://docs.ansible.com/ansible/intro_installation.html
 
Then:

    cd vagrant
    ansible-galaxy install -r requirements.txt
    vagrant up
    
## Notes

If the role-variable ``rest_enabled`` is passed as true, then apache2 will 
be installed and configured as necessary. If ``rest_enabled`` is false,
then the only action taken is that the voeventdb site is disabled using
``a2dissite`` if the relevant file is present in 
`/etc/apache2/sites-enabled`