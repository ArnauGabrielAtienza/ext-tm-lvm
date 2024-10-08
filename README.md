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

-  LVM installed and enabled in the hosts.
-  Password-lesss sudo permission for the following commands:
-    lvremove
-    lvcreate
-    lvs
-    vgdisplay
-    dd
- `oneadmin` needs to belong to the `disk` group.

Configuration
-------------

TODO: Add configuration details here.

Testing
-------

TODO: Add how to test this extension.

Contribution
------------

TODO: Add how the community can contribute to this extension.
