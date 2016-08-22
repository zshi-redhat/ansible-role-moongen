
Ansible role: moongen
=========

Install & configure MoonGen on RedHat OS.

Requirements
------------

assume that user has already enabled repos for packages including kernel-devel, gcc, gcc-c++, cmake etc

Role Variables
--------------

    bind_nics: "0000:00:08.0, 0000:00:08.1"

bind_nics allows user to specify NIC PCI IDs which will be binded to dpdk during MoonGen build. by default, no NICs will be binded.

    dpdk_module: "vfio-pci"

bind nic to dpdk module after building MoonGen.

    cpu_cores: "0,1,3,4"

configure the cpu cores to use for dpdk ports, either as a bitmask or as a list.

    memoryChannels: 2

the number of memory channels (defaults to auto-detect).

    fileprefix: "m1"

A string to be the prefix, corresponding to EAL argument "--file-prefix".

    socketmem: "2048,2048"

A string to specify the socket memory allocation, corresponding to EAL argument "--socket-mem".

    pciblack: ' "0000:81:00.3","0000:81:00.1" '

PCI black list to avoid resetting PCI device assigned to other DPDK apps. Corresponding to ELA argument "--pci-blacklist".

    pciwhite: ' "0000:81:00.3","0000:81:00.1" '

PCI white list to specify devices allocated to MoonGen. Corresponding to ELA argument "--pci-whitelist" or "-w".

    noHugeTlbFs: true

disable hugetlb, see DPDK documentation for more information.

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
