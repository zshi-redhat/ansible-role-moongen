# ansible-role-moongen

Role Name
=========

Install MoonGen on RedHat OS.

Requirements
------------

assume that user has already enabled repos for packages including dpdk, dpdk-tools, kernel-devel, gcc, gcc-c++, cmake etc

Role Variables
--------------

bind_nics: ""

bind_nics allows user to specify NIC PCI IDs which will be binded to dpdk during MoonGen build. by default, no NICs will be binded.

Dependencies
------------

None.

Example Playbook
----------------


    - hosts: servers
      roles:
         - { role: ansible-role-moongen }

License
-------

BSD

Author Information
------------------

This role was created in Aug 2016 by Zenghui Shi.
