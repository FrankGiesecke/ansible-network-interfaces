Ansible network interface configuration
=======================================
[![Ansible Galaxy](https://img.shields.io/badge/Ansible%20Galaxy-dresden--weekly.network--interfaces-blue.svg)](https://galaxy.ansible.com/list#/roles/2766)

This is an Ansible role that manages network interface configuration as it is found on Debian/Ubuntu servers

Requirements
------------

Ubuntu 12.04 (Precise) or Ubuntu 14.04 (Trusty)

May work with other versions, but has never been tested.

Dependencies
------------

none

Example Playbook
----------------

```yml
- hosts: all
  sudo: true
  sudo_user: root

  roles:
  - dresden-weekly.network-interfaces
  vars:
    network_interfaces_manage_devices: yes
    network_interfaces_interfaces:
    - device: eth0
      auto: true
      family: inet
      method: static
      address: 192.168.1.11
      netmask: 255.255.255.0
      network: 193.168.1.0
      gateway: 192.168.1.1
      nameservers:
      - 8.8.8.8
      - 8.8.4.4
      subnets:
      - 192.168.1.12/32
    - device: eth1
      auto: true
      family: inet
      method: dhcp
```

Changelog
---------

**0.2** *TODO*

* [ ] open for your ideas, fixes and pull requests

**0.1** (first release) 01.02.2015

* [✓] ipv6 & ipv4 support
* [✓] support for multiple network devices
* [✓] dhcp and static configuration
* [✓] support for bridges
* [✓] additional subnets and ips
* [✓] custom hook scripts
* [✓] remove old interfaces

License
-------

The MIT License (MIT)

Copyright (c) 2015 dresden-weekly

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
