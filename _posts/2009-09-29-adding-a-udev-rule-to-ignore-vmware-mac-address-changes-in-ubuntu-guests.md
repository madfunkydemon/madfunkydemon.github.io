---
layout: post
title: Adding a udev rule to ignore Vmware MAC address changes in Ubuntu Guests
created: 1254234771
categories:
- linux/unix
---
<p>This is a bit of pain when you are using VMware and Ubuntu as every time there is a MAC address change udev will create another adapter i.e. eth0 will become eth1 and eth0 will seem to disappear.</p>
<p>To stop this behaviour add this:</p>
<pre>
ENV{MATCHADDR}==&quot;00:0c:29:*|00:50:56:*&quot;,&nbsp;ENV{MATCHADDR}=&quot;&quot;

</pre>
<p>To the following file /lib/udev/rules.d/75-persistent-net-generator.rules</p>
