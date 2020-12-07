## cacti-server

[![Build Status](https://travis-ci.org/Oefenweb/ansible-cacti-server.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-cacti-server)
[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-cacti--server-blue.svg)](https://galaxy.ansible.com/Oefenweb/cacti-server/)

Set up cacti in Debian-like systems (server side).

#### Requirements

[See](https://github.com/Cacti/documentation/blob/develop/Installing-Under-Ubuntu-Debian.md) and `tests/pre.yml`.

#### Variables

* `cacti_server_checkout_repo`: [default: `https://github.com/Cacti/cacti.git`]: Cacti git repo
* `cacti_server_version`: [default: `1.2.16`]: Only used in `{{ cacti_server_git_version }}`
* `cacti_server_git_version`: [default: `"release/{{ cacti_server_version }}"`]: What version of Cacti to check out (set up). This can be the full 40-character SHA-1 hash, the literal string HEAD, a branch name, or a tag name

* `cacti_server_config_database_default`: [default: `cacti`]: Database name
* `cacti_server_config_database_hostname`: [default: `localhost`]: Database host
* `cacti_server_config_database_username`: [default: `cacti`]: Database username
* `cacti_server_config_database_password`: [default: `cacti`]: Database password
* `cacti_server_config_database_port`: [default: `3306`]: Database port

* `cacti_server_config_url_path`: [default: `/cacti/`]: The (default) path of your cacti install

* `cacti_server_use_poller_php`: [default: `true`]: Whether or not to install a crontab for the poller

* `cacti_server_install`: [default: `[]`]: Additional packages to install

* `cacti_server_install_path`: [default: `{}`]: Install declaration
* `cacti_server_install_path.src`: [required]: Path of Cacti checkout (e.g. `"{{ cacti_server_checkout_path }}"`)
* `cacti_server_install_path.dest`: [required]: Path of Cacti install (where it will be symlinked to, e.g. `/var/www/example.com/cacti/public_html/cacti`)

## Dependencies

None

## Recommended

* `cacti-client` ([see](https://github.com/Oefenweb/ansible-cacti-client))
* `cacti-plugin-percona` ([see](https://github.com/Oefenweb/ansible-cacti-plugin-percona))
* `cacti-spine` ([see](https://github.com/Oefenweb/ansible-cacti-spine))

#### Example

```yaml
---
- hosts: all
  roles:
    - cacti-server
  vars:
    cacti_server_install_path:
      src: "{{ cacti_server_checkout_path }}"
      dest: /var/www/example.com/cacti/public_html/cacti
```

#### License

MIT

#### Author Information

Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-cacti-server/issues)!
