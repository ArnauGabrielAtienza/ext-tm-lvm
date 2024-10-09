LVM Transfer Manager Extension
==============================

Overview
--------

This is an example of a southbound storage extension for OpenNebula. This extension adds the driver to enable the option of using LVM as a Transfer Manager. You may use this repository as a general guideline for developing you own extension.

## Development

To contribute bug patches or new features, you can use the github Pull Request model. It is assumed that code and documentation are contributed under the Apache License 2.0.

## Compatibility

This extension is compatible with OpenNebula >= 4.6.

Requirements
------------

### OpenNebula Front-End

-  Password-less ssh access to an OpenNebula LVM-enabled host.

### OpenNebula LVM Hosts

* LVM installed and enabled in the hosts.
* Password-lesss sudo permission for the following commands:
   * lvremove
   * lvcreate
   * lvs
   * vgdisplay
   * dd
* `oneadmin` needs to belong to the `disk` group.

Configuration
-------------

### OpenNebula Configuration

In order to have this driver available, in addition to running the `install.sh` script you will need to do the following in your `/etc/one/oned.conf`:

Append `fs_lvm` to the TM_MAD arguments:

~~~~
TM_MAD = [
    EXECUTABLE = "one_tm",
    ARGUMENTS = "-t 15 -d dummy,lvm,shared,qcow2,ssh,ceph,dev,vcenter,iscsi_libvirt,fs_lvm"
]
~~~~

Append the following at he end of the same file:

~~~~
TM_MAD_CONF = [
    NAME = "fs_lvm", LN_TARGET = "SYSTEM", CLONE_TARGET = "SYSTEM", SHARED="YES",
    DRIVER = "raw", DISK_TYPE = "BLOCK"
]
~~~~

Afterwards, you should restart OpenNebula for the changes to take effect.

### LVM Configuration

For information regarding how to setup the LVM storage, please refere [here](https://docs.opennebula.io/6.10/open_cluster_deployment/storage_setup/lvm_drivers.html)

Testing
-------

TODO: Add how to test this extension.

Known Issues
------------

List of known issues:
-  Issue 1
-  Issue 2

Contribution
------------

If you encounter any issue using this extension, feel free to open an issue in this repository and an administrator will review it as soon as posssible. If you want to contribute to the development of the extension, you may open a Pull Request with your proposed changes. 
