# [azure_cli](#azure_cli)

Install and configure azure_cli on your system.

|Travis|GitHub|Quality|Downloads|Version|
|------|------|-------|---------|-------|
|[![travis](https://travis-ci.com/robertdebock/ansible-role-azure_cli.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-azure_cli)|[![github](https://github.com/robertdebock/ansible-role-azure_cli/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-azure_cli/actions)|[![quality](https://img.shields.io/ansible/quality/44611)](https://galaxy.ansible.com/robertdebock/azure_cli)|[![downloads](https://img.shields.io/ansible/role/d/44611)](https://galaxy.ansible.com/robertdebock/azure_cli)|[![Version](https://img.shields.io/github/release/robertdebock/ansible-role-azure_cli.svg)](https://github.com/robertdebock/ansible-role-azure_cli/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/resources/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: robertdebock.azure_cli
```

The machine needs to be prepared in CI this is done using `molecule/resources/prepare.yml`:
```yaml
---
- name: prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.epel
    - role: robertdebock.buildtools
    - role: robertdebock.python_pip
    - role: robertdebock.microsoft_repository_keys
```
```
Also see a [full explanation and example](https://robertdebock.nl/how-to-use-these-roles.html) on how to use these roles.


## [Requirements](#requirements)

- Access to a repository containing packages, likely on the internet.
- A recent version of Ansible. (Tests run on the current, previous and next release of Ansible.)

## [Status of requirements](#status-of-requirements)

| Requirement | Travis | GitHub |
|-------------|--------|--------|
| [robertdebock.bootstrap](https://galaxy.ansible.com/robertdebock/bootstrap) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-bootstrap.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-bootstrap) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-bootstrap/actions) |
| [robertdebock.buildtools](https://galaxy.ansible.com/robertdebock/buildtools) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-buildtools.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-buildtools) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-buildtools/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-buildtools/actions) |
| [robertdebock.epel](https://galaxy.ansible.com/robertdebock/epel) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-epel.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-epel) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-epel/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-epel/actions) |
| [robertdebock.microsoft_repository_keys](https://galaxy.ansible.com/robertdebock/microsoft_repository_keys) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-microsoft_repository_keys.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-microsoft_repository_keys) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-microsoft_repository_keys/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-microsoft_repository_keys/actions) |
| [robertdebock.python_pip](https://galaxy.ansible.com/robertdebock/python_pip) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-python_pip.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-python_pip) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-python_pip/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-python_pip/actions) |

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/drawings/artifacts/azure_cli.png "Dependency")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/robertdebock):

|container|tags|
|---------|----|
|alpine|all|
|el|7, 8|
|debian|buster|
|fedora|all|
|ubuntu|focal, bionic|

The minimum version of Ansible required is 2.9, tests have been done to:

- The previous version.
- The current version.
- The development version.

## [Exceptions](#exceptions)

Some variarations of the build matrix do not work. These are the variations and reasons why the build won't work:

| variation                 | reason                 |
|---------------------------|------------------------|
| Alpine | fatal error: Python.h: No such file or directory |
| centos:latest | Depsolve Error occured: Problem: cannot install the best candidate for the job - nothing provides python needed by azure-cli-2.0.76-1.el7.x86_64 |
| opensuse | Cannot uninstall 'six'. It is a distutils installed project |


## [Testing](#testing)

[Unit tests](https://travis-ci.com/robertdebock/ansible-role-azure_cli) are done on every commit, pull request, release and periodically.

If you find issues, please register them in [GitHub](https://github.com/robertdebock/ansible-role-azure_cli/issues)

Testing is done using [Tox](https://tox.readthedocs.io/en/latest/) and [Molecule](https://github.com/ansible/molecule):

[Tox](https://tox.readthedocs.io/en/latest/) tests multiple ansible versions.
[Molecule](https://github.com/ansible/molecule) tests multiple distributions.

To test using the defaults (any installed ansible version, namespace: `robertdebock`, image: `fedora`, tag: `latest`):

```
molecule test

# Or select a specific image:
image=ubuntu molecule test
# Or select a specific image and a specific tag:
image="debian" tag="stable" tox
```

Or you can test multiple versions of Ansible, and select images:
Tox allows multiple versions of Ansible to be tested. To run the default (namespace: `robertdebock`, image: `fedora`, tag: `latest`) tests:

```
tox

# To run CentOS (namespace: `robertdebock`, tag: `latest`)
image="centos" tox
# Or customize more:
image="debian" tag="stable" tox
```

## [License](#license)

Apache-2.0


## [Author Information](#author-information)

[Robert de Bock](https://robertdebock.nl/)

Please consider [sponsoring me](https://github.com/sponsors/robertdebock).
