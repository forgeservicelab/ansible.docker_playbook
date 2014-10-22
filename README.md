# Demo Docker playbook

This playbook installs Docker on Ubuntu 14.04 and runs containers.

To use this, you must have instance of Ubuntu 14.04 running and you must be able to reach ports 22, 8001, 8002 and 8003.

**You must also have Ansible 1.8.**

It's using roles
 * https://github.com/angstwad/docker.ubuntu
 * https://github.com/t0mk/dockerdemo

The roles are listed in requirements.yml, so to get them (do what puppet or chef librarians do), just run

```
sudo ansible-galaxy install -r requirements.yml
```

Once you have the roles installed, and the instance running, use the playbook as:

```
ansible-playbook -s d.yml -e h=your_ubuntu_host
```

If the playbook succeeded, you can test that the containers are running:

```
for p in 800{1,2,3}; do curl host_ip_or_name:$p; done
```

Output should be

```
Hello world!Hello world!Hello world!
```

