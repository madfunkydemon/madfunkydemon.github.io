---
layout: post
title: Create an virtual network interface in an ESX windows guest using VGT (Virtual
  Guest Tagging)
created: 1258631591
categories:
- virtualisation
- networking
- esx
permalink: /2009/november/4/create-virtual-network-interface-esx-windows-guest-using-vgt-virtual-guest-tagging
---
<p>&nbsp;Get the intel drivers from&nbsp;<a href="http://www.intel.com/support/network/sb/cs-006120.htm">e1000 NIC</a>&nbsp;(32bit) and install them in your vm. Once installed make sure you configure the network card properties with the correct VLAN tag. Then make sure that you assign the VLAN tag 4095 to the virtual machine's portgroup.</p>
