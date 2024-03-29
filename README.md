# Ansible role [ntp](https://galaxy.ansible.com/ui/standalone/roles/buluma/ntp/documentation)

Install and configure ntp on your system.

|GitHub|Version|Issues|Pull Requests|Downloads|
|------|-------|------|-------------|---------|
|[![github](https://github.com/buluma/ansible-role-ntp/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-ntp/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-ntp.svg)](https://github.com/buluma/ansible-role-ntp/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-ntp.svg)](https://github.com/buluma/ansible-role-ntp/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-ntp.svg)](https://github.com/buluma/ansible-role-ntp/pulls/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/ntp)](https://galaxy.ansible.com/ui/standalone/roles/buluma/ntp/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-ntp/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true

  roles:
    - role: buluma.cron
    - role: buluma.ntp
      ntp_state: stopped
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-ntp/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  become: true
  gather_facts: false

  roles:
    - role: buluma.bootstrap
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-ntp/blob/master/defaults/main.yml):

```yaml
---
# defaults file for ntp

# The state of the NTP service.
ntp_state: started

# The state of the NTP service at boot.
ntp_enabled: true

# A list of IP addresses to listen on.
ntp_interfaces:
  - address: "127.0.0.1"

# A list of NTP pools and their options.
ntp_pool:
  - name: "0.pool.ntp.org iburst"
  - name: "1.pool.ntp.org iburst"
  - name: "2.pool.ntp.org iburst"
  - name: "3.pool.ntp.org iburst"

# A list of NTP servers and their options.
# ntp_server:
#   - name: ntp.example.com
#     options:
#       - iburst

# The timezone.
ntp_timezone: Etc/UTC
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-ntp/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.cron](https://galaxy.ansible.com/buluma/cron)|[![Ansible Molecule](https://github.com/buluma/ansible-role-cron/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-cron/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-cron.svg)](https://github.com/shadowwalker/ansible-role-cron)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-ntp/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Amazon](https://hub.docker.com/r/buluma/amazonlinux)|Candidate|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|8|
|[Debian](https://hub.docker.com/r/buluma/debian)|all|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|all|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-ntp/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-ntp/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-ntp/blob/master/LICENSE)

## [Author Information](#author-information)

[Shadow Walker](https://buluma.github.io/)
