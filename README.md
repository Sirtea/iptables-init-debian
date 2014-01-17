iptables-init-debian
====================

Init script for controlling iptables as a service in a Debian box.
Tested in Debian Squeeze, Wheezy and Sid.

## How to install iptables-init-debian
Download the script and place it in /etc/init.d/ with execution permissions, and use.
I you want this script to be recognized as a service and autostart in debian, you must issue the following command:

```bash
update-rc.d iptables defaults
```

## How to use the script
This script relies on iptables-save and iptables-restore commands, to save and read the rules in /etc/iptables.rules.
Once installed, this file must be created, by saving current rules (save command).

Available command are:

* start: loads /etc/iptables.rules
* stop: flushes iptables completely, and enforces ACCEPT policy
* restart: convenience start & stop command
* save: saves the current rules to /etc/iptables.rules

Example:

```bash
service iptables start
service iptables stop
service iptables restart
service iptables status
```
