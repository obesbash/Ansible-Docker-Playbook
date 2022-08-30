# Ansible-Docker-Playbook

Ansible playbook do deploy docker engine on *nix systems.

You can use it like full playbook or just like role in your own playbook.

## OS Requirements
- **Debian** See [this blog](https://docs.docker.com/engine/install/debian/#os-requirements)
- **Ubuntu** See [this blog](https://docs.docker.com/engine/install/ubuntu/#os-requirements)
- **CentOS** See [this blog](https://docs.docker.com/engine/install/centos/#os-requirements)

## How to play
1) Edit ./hosts file. Add your hosts
2) Run next comman:

```bash
      ansible-playbook playbook.yaml -i hosts --extra-vars "docker-users=$your_user"
```
 - **--extra-vars "docker-users=$your_user"** this extra var allow you to considering user who whould run command "docker" without sudo. If this extra var omited, then ansibel fact "ansible_env.USER" will be used
 - **-skip-tags [tag3, tag4]** you can skip tasks that installing composer and add user to docker group like this:
 ```bash
      ansible-playbook playbook.yaml -i hosts --extra-vars "docker-users=$your_user" -skip-tags [composer, nonroot]
```

#To do
- [ ]  Add Debian tasks and var
- [ ]  Add CentOS tasks and var
