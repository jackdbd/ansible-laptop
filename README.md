# Ansible Laptop Configuration

Configuration for my Laptop (I use Xubuntu).

![INSTALL ALL THE THINGS!](https://github.com/jackdbd/ansible-laptop/blob/master/install-all-the-things.jpg "INSTALL ALL THE THINGS!")

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

## Note

If, after the installation is completed, you notice that keyboard shortcuts perform the expected action only after A LOT of time, try uninstalling `dbus-user-session` as suggested [here](https://askubuntu.com/a/916263/731701).

## TODO

- Upgrade to Ansible 2.8 which allows to [install snap packages](https://stackoverflow.com/questions/47305658/install-snap-packages-with-ansible) with the `snap` Ansible *module* (instead of using `snap` as a *command*).

## Credits

- [Benoth/ansible-ubuntu](https://github.com/Benoth/ansible-ubuntu)
