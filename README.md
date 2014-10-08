# Demo Docker playbook

This playbook installs Docker on Ubuntu 14.04 and runs containers.

It's using roles
 * https://github.com/angstwad/docker.ubuntu
 * https://github.com/t0mk/dockerdemo

The roles are listed in requirements.yml, so to get them (do what puppet or chef librarians do), just run

```
sudo ansible-galaxy install -r requirements.yml
```

Once you have the roles installed, and the instance running, use the playbook as:

```
ansible-playbook -s d.yml -e h=your\_ubuntu\_host
```
