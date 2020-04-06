==========
ROLE GRUB
==========

.. image:: https://img.shields.io/github/license/adfinis-sygroup/ansible-role-grub.svg?style=flat-square
  :target: https://github.com/adfinis-sygroup/ansible-role-grub/blob/master/LICENSE

.. image:: https://img.shields.io/travis/adfinis-sygroup/ansible-role-grub.svg?style=flat-square
  :target: https://github.com/adfinis-sygroup/ansible-role-grub

.. image:: https://img.shields.io/badge/galaxy-adfinis--sygroup.grub-660198.svg?style=flat-square
  :target: https://galaxy.ansible.com/adfinis-sygroup/grub

A brief description of the role goes here.


Requirements
=============

Any pre-requisites that may not be covered by Ansible itself or the role
should be mentioned here. For instance, if the role uses the EC2 module, it
may be a good idea to mention in this section that the boto package is required.


Role Variables
===============

start grub and linux on these consoles

.. code-block:: YAML

   grub_consoles:
     - tty0
     - 'ttyS0,{{ grub_serial.speed }}'

grub serial command settings

.. code-block:: YAML

   grub_serial:
     speed: 115200
     unit: 0
     word: 8
     parity: 0
     stop: 1

grub timeout (in seconds)

.. code-block:: YAML

   grub_timeout: 5

disable predictable network interface names

.. code-block:: YAML

   grub_disable_network_predictable_interface_names: True

additional cmdline arguments
type: list

.. code-block:: YAML

   grub_cmdline_linux_list: []

additional cmdline default arguemnts
type: list

.. code-block:: YAML

   grub_cmdline_linux_default_list: [ ]

An example how to add additional parameters to the kernel:

.. code-block:: YAML

  grub_cmdline_linux_list:
    - ip=192.0.2.2::192.0.2.1:255.255.255.0:host.example.com:eth0:off
    - vnc
    - vncpassword=password

  grub_cmdline_linux_default_list:
    - transparent_hugepage=never
    - numa=off


Dependencies
=============

A list of other roles hosted on Galaxy should go here, plus any details in
regards to parameters that may need to be set for other roles, or variables
that are used from other roles.


Example Playbook
=================

Including an example of how to use your role (for instance, with variables
passed in as parameters) is always nice for users too:

.. code-block:: yaml

  - hosts: servers
    roles:
       - { role: adfinis-sygroup.grub }


License
========

`GPL-3.0 <https://github.com/adfinis-sygroup/ansible-role-grub/blob/master/LICENSE>`_


Author Information
===================

grub role was written by:

* Adfinis SyGroup AG | `Website <https://www.adfinis-sygroup.ch/>`_ | `Twitter <https://twitter.com/adfinissygroup>`_ | `GitHub <https://github.com/adfinis-sygroup>`_

