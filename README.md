# Ansible Laptop Configuration

Configuration for my Laptop (I use Xubuntu).

![INSTALL ALL THE THINGS!](https://github.com/jackdbd/ansible-laptop/blob/master/install-all-the-things.jpg "INSTALL ALL THE THINGS!")

First of all, you will need Ansible 2.8+ (because it can manage [snaps](https://docs.ansible.com/ansible/latest/modules/snap_module.html))

Here are the instructions from the [official Ansible documentation](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#latest-releases-via-apt-ubuntu).

```sh
sudo apt update
sudo apt install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt install ansible --yes
```

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

## Credits

- [Benoth/ansible-ubuntu](https://github.com/Benoth/ansible-ubuntu)
