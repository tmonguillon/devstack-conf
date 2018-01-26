# devstack-conf

Configuration file for Devstack Pike version with Neutron + networking-sfc.

Requirements
============

* Baremetal or VM with 8Gb RAM and 40Gb Disk (at least)
* Ubuntu 16.04
* Git installed


Installation & configuration
============================

Install a fresh environment according the choosen version.

    git clone https://github.com/openstack-dev/devstack.git -b stable/pike

Install the related configuration file.

    git clone https://github.com/tmonguillon/devstack-conf.git -b pike-sfc
    ln -sf `pwd`/devstack-conf/local.conf `pwd`/devstack/local.conf

Now you can launch devstack.

    cd devstack
    ./stack.sh


Issues
======

None