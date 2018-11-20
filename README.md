# Ansible Laptop Configuration

The Ansible playbook `playbook.yml` relies on some roles which must be installed from [Ansible Galaxy](https://galaxy.ansible.com/home). These roles can be automatically downloaded and installed with:

```shell
ansible-galaxy install -r requirements.yml
```

Install all the things (you will need to type your sudo password once).

```shell
ansible-playbook -K playbook.yml
```

You can also check that the playbook does not have any syntactic errors.

```shell
ansible-playbook playbook.yml --syntax-check
```

# TODO

- use latest ansible to [install snap packages](https://stackoverflow.com/questions/47305658/install-snap-packages-with-ansible)

