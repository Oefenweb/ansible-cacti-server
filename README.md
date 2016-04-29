## cacti-server

[![Build Status](https://travis-ci.org/Oefenweb/ansible-cacti-server.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-cacti-server) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-cacti--server-blue.svg)](https://galaxy.ansible.com/list#/roles/6434)

Set up cacti in Debian-like systems (server side).

#### Requirements

None

#### Variables

* `cacti_server_root_dbpass`: [required]: Root user database password

* `cacti_server_install`: [default: `[]`]: Additional packages to install

* `cacti_server_server_dbuser`: [required]: Cacti user database username
* `cacti_server_server_dbpass`: [required]: Cacti user database password

## Dependencies

None

#### Example

```yaml
---
- hosts: all
  roles:
    - cacti-server
```

#### License

MIT

#### Author Information

* Mark van Driel
* Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-cacti-server/issues)!
