Ansible Role: Visual Studio Code
================================

[![Build Status](https://travis-ci.org/gantsign/ansible-role-visual-studio-code.svg?branch=master)](https://travis-ci.org/gantsign/ansible-role-visual-studio-code)

Role to install the [Visual Studio Code](https://code.visualstudio.com) IDE / text editor.

Requirements
------------

* Ubuntu

Role Variables
--------------

The following variables will change the behavior of this role (default values
are shown below):

```yaml
# Visual Studio Code version number
visual_studio_code_version: '1.4'

# Directory to store files downloaded for Visual Studio Code installation
visual_studio_code_download_dir: "{{ x_ansible_download_dir | default('~/.ansible/tmp/downloads') }}"

# SHA256 sum for the redistributable package
visual_studio_code_redis_sha256sum: 53eb2cd235b395a28e7fda6f50f904fd5665877e354609f836a6b60a1592c9c9

# The download URL for the redistributable package
visual_studio_code_redis_url: https://az764295.vo.msecnd.net/stable/e724f269ded347b49fcf1657fc576399354e6703/code_1.3.0-1467909982_amd64.deb
```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: gantsign.visual-studio-code }
```

Development & Testing
---------------------

This project uses [Molecule](http://molecule.readthedocs.io/) to aid in the
development and testing; the role is unit tested using
[Testinfra](http://testinfra.readthedocs.io/) and
[pytest](http://docs.pytest.org/).

To develop or test you'll need to have installed the following:

* Linux (e.g. [Ubuntu](http://www.ubuntu.com/))
* [Docker](https://www.docker.com/)
* [Python](https://www.python.org/) (including python-pip)
* [Ansible](https://www.ansible.com/)
* [Molecule](http://molecule.readthedocs.io/)

To run the role (i.e. the `tests/test.yml` playbook), and test the results
(`tests/test_role.py`), execute the following command from the project root
(i.e. the directory with `molecule.yml` in it):

```bash
molecule test
```

License
-------

MIT

Author Information
------------------

John Freeman

GantSign Ltd.
Company No. 06109112 (registered in England)
