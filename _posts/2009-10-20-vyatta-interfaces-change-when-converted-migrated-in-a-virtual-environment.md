---
layout: post
title: Vyatta interfaces change when converted/migrated in a virtual environment
created: 1256055573
categories:
- virtualisation
permalink: /2013/may/6/excluding-or-including-networksubnet-wireshark-results
---
The virtual appliance you can download already has the correct udev rules which usually cause this situation (<a href="/2009/september/2/adding-udev-rule-ignore-vmware-mac-address-changes-ubuntu-guests">see  here</a>). There is a file in vyatta which has a record of the specific interface information. When you migrate the machine, this record causes the machine to think the adapters have changed. Edit the following file:

`nano /opt/vyatta/etc/config/config.boot`

You can either remove the interfaces section or edit the interfaces to suit i.e. change the MAC addresses etc.
