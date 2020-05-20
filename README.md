# Ansible Laptop Configuration

Configuration for my Laptop (I use Xubuntu).

![INSTALL ALL THE THINGS!](https://github.com/jackdbd/ansible-laptop/blob/master/install-all-the-things.jpg "INSTALL ALL THE THINGS!")

First of all, you will need Ansible 2.8+ (because it can manage [snaps](https://docs.ansible.com/ansible/latest/modules/snap_module.html))

The easiest way to install ansible is with [pipx](https://github.com/pipxproject/pipx).

```sh
pipx install ansible
```

The Ansible playbook `playbook.yml` contains serval tasks (i.e. the Ansible unit of action) grouped by [roles](https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html) and identified by [tags](https://docs.ansible.com/ansible/latest/user_guide/playbooks_tags.html). You can see the list tasks with this command:

```sh
ansible-playbook playbook.yml -K --list-tasks
```

The playbook relies on some roles which must be installed from [Ansible Galaxy](https://galaxy.ansible.com/home). These roles can be automatically downloaded and installed with:

```shell
ansible-galaxy install -r requirements.yml
```

Install all the things (you will need to type your sudo password once).

```sh
ansible-playbook playbook.yml -K --tags "docs,fonts"
```

OR install only the tasks you want:

```sh
ansible-playbook playbook.yml -K --tags "docs,fonts" --list-tasks
ansible-playbook playbook.yml -K --tags "docs,fonts"
```

If some tasks fail, try re-running the playbook while skipping them:

```sh
ansible-playbook playbook.yml -K --skip-tags "js,python"
```

You can also check that the playbook does not have any syntactic errors:

```sh
ansible-playbook playbook.yml --syntax-check
```

## Note

If, after the installation is completed, you notice that keyboard shortcuts perform the expected action only after A LOT of time, try uninstalling `dbus-user-session` as suggested [here](https://askubuntu.com/a/916263/731701).

## Credits

- [Benoth/ansible-ubuntu](https://github.com/Benoth/ansible-ubuntu)
