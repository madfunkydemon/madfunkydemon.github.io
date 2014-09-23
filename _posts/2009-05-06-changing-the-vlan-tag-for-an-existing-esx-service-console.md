---
layout: post
title: Changing the VLAN Tag for an Existing ESX Service Console
created: 1241613330
categories:
- virtualisation
- esx
---
<p>Once you have made network changes (802.1Q)&nbsp;and you have lost&nbsp;(oops)&nbsp;connectivity to your service console, use the following to change the VLAN&nbsp;tag:</p>
<pre>
esxcfg-vswitch vSwitch0 -v N -p &quot;Service Console&quot;
</pre>
<p>Where N is the VLAN&nbsp;tag you want to use. In this case it was vSwitch with the portgroup name &quot;Service Console&quot;.</p>
<p>To list the current configuration use:</p>
<pre>
esxcfg-vswitch -l
</pre>
