## ansible_template
Basic Ansible template designed for single-project servers. The playbook establishes the standard Ansible project structure outlined in the [ansible documentation](https://docs.ansible.com).

## Usage
Firstly you need to create `production` file where you describe your way to connect to the server
```
[production]
mainserver ansible_host=1.2.3.4 ansible_user=root ansible_ssh_private_key_file=path/to/sshkey

[production:vars]
env=production
```
Before running please take a look at `group_vars/all.yml` and set it up to for your purposes.
Now you can use this command to set up your new server.
```sh
ansible-playbook init.yml -i production --extra-vars='{"project_name": "testproject"}'
```

## License
Apache 2.0 — use and adapt at your own risk.