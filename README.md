# Ansible Role: terraria_server

An ansible role to automate deployment of Terraria on linux hosts

Configures:
* a service user
* start scripts (executed in a screen session)
* save scripts (executed every 30 minutes)
* backups (rotated every 720 minutes by default)

<p align="center">
  <img width="800" src="tree.png">
</p>

## Requirements
------------

* Linux target (this has been tested against Ubuntu 16.04 LTS)
* Ansible version 2.4.2.0 (others may work, but this version was used for testing)

## Role Variables

### Minimum Required Variables

You must define the version to deploy as this will obtained from the server file mirror.

```yaml
terraria_version: 1353
```

### Common Variables

```yaml
# name used for your world (string)
world_name:

# motd used for your world (string)
world_motd:

# auto-create the world, for new worlds (boolean)
world_autocreate: 

# world seed (string)
world_seed: 

# difficulty (string - options: normal, expert)
world_difficulty:

# size (string - options: small, medium, large)
world_size:

# player cap for your world (int)
world_max_players:

# If you want a password protected server (string)
server_password:

# language (string - see options: https://terraria.gamepedia.com/Server)
server_lang:

# banned players (list)
banned_players:

# enable UPNP (boolean)
server_upnp_enabled:
```

### All Variables

Work-In-Progress

## Example Playbook

Calling the role with minimum required `terraria_version` and a few configured values, relying on defaults for everything else.

```yaml
---
- hosts: servers
  roles:
  - role: terraria_server
    terraria_version: 1353
    world_name: "Iceland"
    server_port: 7878
```
