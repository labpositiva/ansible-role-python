Ansible Role Python
###################

|Build Status| |Ansible Galaxy| |GitHub issues| |Average time to resolve an issue| |Percentage of issues still open| |GitHub license|

:Version: 0.1.0
:Web: https://github.com/labpositiva/ansible-role-python
:Download: http://github.com/labpositiva/ansible-role-python
:Source: http://github.com/labpositiva/ansible-role-python
:Keywords: ansible-role-python

.. contents:: Table of Contents:
    :local:

Ansible Galaxy role for `python`_.

Requirements:
=============

List of applications:

- `Python 3.6.1`_
- `Docker`_
- `Docker Compose`_

Install
=======

Install it with the following command:

.. code:: bash

    $ ansible-galaxy install labpositiva.python

Role Variables
==============

The default role variables in ``defaults/main.yml`` are:

.. code:: yaml

        python_pyenv_path: "{{ ansible_env.HOME }}/pyenv"
        python_pyenv_owner: "{{ ansible_env.USER }}"
        python_pyenv_python_versions: ["3.6.0"]
        python_pyenv_delete_virtualenvs: [{ venv_name: "latest" }]
        python_pyenv_virtualenvs: [{ venv_name: "latest", py_version: "3.6.0" }]
        python_pyenv_update_git_install: no

Dependencies
============

None

Example Playbook
================

See the `examples <./examples/>`__ directory.

To run this playbook with default settings, create a basic playbook like
this:

.. code:: yaml

        - hosts: servers
          roles:
            - labpositiva.python

To install a specific version:

.. code:: yaml

      - hosts: servers
        roles:
          - { role: labpositiva.python }

.. code:: yaml

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

License
=======

MIT

Changelog
=========

Please see `CHANGELOG`_ for more information what
has changed recently.

Contributing
============

Please see `CONTRIBUTING`_ for details.

Credits
=======

-  `author`_
-  `contributors`_

Made with :heart: :coffee: and :pizza: by `author`_ and `company`_.

.. Badges:

.. |Build Status| image:: https://travis-ci.org/labpositiva/ansible-role-python.svg
   :target: https://travis-ci.org/labpositiva/ansible-role-python
.. |Ansible Galaxy| image:: https://img.shields.io/badge/galaxy-labpositiva.redis-blue.svg
   :target: https://galaxy.ansible.com/labpositiva/redis/
.. |GitHub issues| image:: https://img.shields.io/github/issues/labpositiva/ansible-role-python.svg
   :target: https://github.com/labpositiva/ansible-role-python/issues
.. |Average time to resolve an issue| image:: http://isitmaintained.com/badge/resolution/labpositiva/ansible-role-python.svg
   :target: http://isitmaintained.com/project/labpositiva/ansible-role-python
.. |Percentage of issues still open| image:: http://isitmaintained.com/badge/open/labpositiva/ansible-role-python.svg
   :target: http://isitmaintained.com/project/labpositiva/ansible-role-python
.. |GitHub license| image:: https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square
   :target: LICENSE

.. Links
.. _`changelog`: CHANGELOG.rst
.. _`contributors`: AUTHORS
.. _`contributing`: CONTRIBUTING.rst

.. _`company`: https://github.com/labpositiva
.. _`author`: https://github.com/luismayta

.. dependences
.. _Python 3.6.1: https://www.python.org/downloads/release/python-361
.. _Docker: https://www.docker.com/
.. _Docker Compose: https://docs.docker.com/compose/