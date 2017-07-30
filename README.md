# Ansible Role Python

[![Build Status](https://travis-ci.org/labpositiva/ansible-role-python.svg)](https://travis-ci.org/labpositiva/ansible-role-python)
[![Stories in Ready](https://badge.waffle.io/labpositiva/ansible-role-python.svg?label=ready&title=Ready)](http://waffle.io/labpositiva/ansible-role-python)
[![GitHub issues](https://img.shields.io/github/issues/labpositiva/ansible-role-python.svg)](https://github.com/labpositiva/ansible-role-python/issues)
[![GitHub license](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square)](LICENSE)


Ansible Galaxy role for [pyenv](link-pyenv).

## Requirements

 - Linux
   - none
 - OSX
   - none


## Install

Install it with the following command:

```bash
$ ansible-galaxy install labpositiva.python
```

## Requirements

none

## Role Variables

The default role variables in `defaults/main.yml` are:

```yaml
    ---
    python_pyenv_path: "{{ ansible_env.HOME }}/pyenv"
    python_pyenv_owner: "{{ ansible_env.USER }}"
    python_pyenv_python_versions: ["3.6.0"]
    python_pyenv_delete_virtualenvs: [{ venv_name: "latest" }]
    python_pyenv_virtualenvs: [{ venv_name: "latest", py_version: "3.6.0" }]
    python_pyenv_update_git_install: no

```

## Dependencies

None


## Example Playbook

See the [examples](./examples/) directory.

To run this playbook with default settings, create a basic playbook like this:

```yaml
    - hosts: servers
      roles:
        - labpositiva.python
```


To install a specific version:

```yaml
  - hosts: servers
    roles:
      - { role: labpositiva.python }
```

```yaml
    - hosts: servers
      roles:
         - role: labpositiva.python
           python_pyenv_path: "{{ home }}/pyenv"
           python_pyenv_owner: "{{ instance_owner }}"
           python_pyenv_update_git_install: no
           python_pyenv_python_versions:
             - "3.5.1"
             - "2.7.9"
           python_pyenv_delete_virtualenvs:
             - venv_name: "delete_venv_name"
           python_pyenv_virtualenvs:
             - venv_name: "latest_v3"
               py_version: "3.5.1"

             - venv_name: "latest_v2"
               py_version: "2.7.9"
```

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Credits

Made with :heart: ️:coffee:️ and :pizza: by [labpositiva][link-company].

- [All Contributors][link-contributors]


<!-- Other -->

[link-pyenv]: https://github.com/yyuu/pyenv
[link-luis]: https://github.com/luismayta
[link-contributors]: AUTHORS
[link-company]: https://github.com/labpositiva
