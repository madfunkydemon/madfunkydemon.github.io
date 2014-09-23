---
layout: post
title: Adding a Port Group and Setting the VLAN tag from the Service Console in ESX
created: 1241618180
categories:
- virtualisation
- esx
---
<p>&nbsp;Use the following:</p>
<p>esxcfg-vswitch -A &quot;Port Group Name&quot; vSwitch2 &amp;&amp; esxcfg-vswitch -v N -p &quot;Port Group Name&quot; vSwitch2</p>
<p>Where N is the VLAN&nbsp;tag.</p>
