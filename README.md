## autossh-tunnel-server

[![CI](https://github.com/Oefenweb/ansible-autossh-tunnel-server/workflows/CI/badge.svg)](https://github.com/Oefenweb/ansible-autossh-tunnel-server/actions?query=workflow%3ACI)
[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-autossh--tunnel--server-blue.svg)](https://galaxy.ansible.com/Oefenweb/autossh-tunnel-server)

Set up a persistent tunnel (using `autossh`) in Debian-like systems (server side).

#### Requirements

None

#### Variables

* `autossh_tunnel_server_user`: [default: `autossh`]: The user that will accept the `autossh` connection
* `autossh_tunnel_server_group`: [default: `autossh`]: The primary group of the `autossh` user
* `autossh_tunnel_server_groups`: [default: `[ssh_users]`]: The secondary groups of the `autossh` user
* `autossh_tunnel_server_shell`: [default: `/bin/false`]: The shell of the `autossh` user

* `autossh_tunnel_server_authorized_keys`: [default: `[]`]: Authorized key declarations
* `autossh_tunnel_server_authorized_keys.{n}.src`: [required]: The local path of the key
* `autossh_tunnel_server_authorized_keys.{n}.state`: [optional, default: `present`]: State

## Dependencies

None

## Recommended

* `ansible-autossh-tunnel-client` ([see](https://github.com/Oefenweb/ansible-autossh-tunnel-client))

#### Example

```yaml
---
- hosts: all
  roles:
    - autossh-tunnel-server
  vars:
    autossh_tunnel_server_groups:
      - ssh_users
    autossh_tunnel_server_authorized_keys:
      - src: ../../../files/autossh-tunnel/etc/autossh/id_rsa.pub
```

#### License

MIT

#### Author Information

Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-autossh-tunnel-server/issues)!
