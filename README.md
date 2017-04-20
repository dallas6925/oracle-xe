# oracle-xe
Vagrant setup for an Oracle XE installation

## Pre-requisites

### Download the Oracle XE 11gR2 installation
See http://www.oracle.com/technetwork/products/express-edition/overview/index.html

Requires an Oracle account and acceptance of the license terms.
The Linux RPM file is required:

``oracle-xe-11.2.0-1.0.x86_64.rpm.zip``

Make this available to the project's oracle folder, for example:

```cp ~/Downloads/oracle-xe-11.2.0-1.0.x86_64.rpm.zip oracle/```

### Install Vagrant
TODO: Document here a quick-guide?

This installation is using the official Vagrant images of CentOS Linux 6.8
which does not pre-install the VirtualBox Guest Additions.
When running with the VirtualBox provider, install the [vagrant-vbguest](https://github.com/dotless-de/vagrant-vbguest) plugin.

    vagrant plugin install vagrant-vbguest

## Usage
To provision/start the Oracle XE instance:

```vagrant up```

Connect to the running database via the XE listener on localhost port 1521.
JDBC connection string is "jdbc:oracle:thin:@localhost:1521:XE"

You can also connect to the web console via http://localhost:8080/apex/f?p=4950:1

To stop the Oracle XE instance:

```vagrant halt```

To remove the Oracle XE instance:

```vagrant destroy```
