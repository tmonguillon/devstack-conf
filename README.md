# devstack_conf

Configuration file for Devstack Mitaka version with OpenContrail.

**Warning: Mitaka is now EOL**

Requirements
============

* Baremetal or VM with 8Gb RAM and 40Gb Disk (at least)
* Ubuntu 14.04
* Git installed


Installation & configuration
============================

Install a fresh environment according the choosen version.

    git clone https://github.com/openstack-dev/devstack.git -b mitaka-eol

Install the related configuration file.

    git clone https://github.com/tmonguillon/devstack-conf.git -b mitaka-eol-contrail
    ln -sf `pwd`/devstack-conf/local.conf `pwd`/devstack/local.conf

Now you can launch devstack.

    cd devstack
    ./stack.sh


Issues
======

With version mitaka-eol, the stack process can fail with an error like this one:

    2017-08-23 06:33:22.127 |   File "/usr/local/lib/python2.7/dist-packages/openstack/session.py", line 29, in <module>
    2017-08-23 06:33:22.127 |     DEFAULT_USER_AGENT = "openstacksdk/%s" % openstack.__version__
    2017-08-23 06:33:22.127 | AttributeError: 'module' object has no attribute '__version__'

To fix this, you need to edit the file "/usr/local/lib/python2.7/dist-packages/openstack/session.py" at the line 29 and remove ".__version__" to the string "openstack.__version__". Save the modification, unstask.sh and stack.sh.




