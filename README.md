# Overview

This charm provides opencart from http://www.opencart.org. Opencart is an award-winning content management system (CMS), which enables you to build Web sites and powerful online applications.

# Installation

To install this charm you should create a config.yaml file that suites your needs and schedule the following juju actions:

    juju deploy mysql
    juju deploy opencart

Before you add a relation to mysql you need to provide a valid config.yaml to the charm that contains the admin_password. Please, refer to the juju documentation on instructions on how to set and use charm configuration files;

Once the configuration is in place you can then add a relation between opencart and mysql with:

    juju add-relation opencart mysql

Finally you need to expose your opencart instance:

    juju expose opencart

Note that the mysql reation addition will create the database and populated it with the admin user set at config.yaml.

To access your exposed opencart unit you just have to open the unit's public IP address with your browser. The default user is admin and the password should be set to whatever you defined on config.yaml

You may change the admin password and perform other administrative functions at the exposed service URL http://public-ip-address/administrator

# Configuration

admin_password sets the admin password for the opencart unit

# Contact Information

Author: Helio L Mota
Report bugs at: http://bugs.launchpad.net/charms/+source/opencart
Location: http://jujucharms.com/charms/precise/opencart
