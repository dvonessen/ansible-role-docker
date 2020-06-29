# ansible-role-docker

This role installs and configures docker daemon or only the cli tools with docker-compose.

## Description

It as possible to install docker daemon, docker cli tools or docker-compose.
The CLI tools are installed regardless which option you will set.

## Role Variables

| Name                            | Default | Description                                                                                                                     |
| :------------------------------ | :-----: | ------------------------------------------------------------------------------------------------------------------------------- |
| `docker_install_daemon`         |  True   | Enable Docker daemon installation. If `false` only the cli tools will be installed.                                             |
| `docker_install_docker_compose` |  False  | Install docker-compose client tool on system. Installation via pip.                                                             |
| `docker_compose_version`        | 1.26.0  | `docker-compose` version to install on remote system.                                                                           |
| `docker_configuration_options`  | Complex | Variable to set docker daemon configuration options in `/etc/docker/daemon.json`. See: [defaults/main.yml](./defaults/main.yml) |

## Role Tags

| Name              | Description                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| docker_all        | Run all tasks of this role.                                              |
| docker_repository | Run only tasks that installs the docker registry.                        |
| docker_client     | Run only tasks that will install the client tools and/or docker-compose. |
| docker_daemon     | Run only tasks that will install the docker daemon.                      |
| docker_configure  | Run only tasks to configure the docker daemon.                           |

## Dependencies

**None**

## Example Playbook


```yaml
- name: All
  hosts: all
  debugger: on_failed
  roles:
    - role: ansible-role-docker
```

## License

MIT License

## Contributors

Daniel von Eßen
