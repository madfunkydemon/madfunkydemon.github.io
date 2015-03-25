---
layout: post
title: Flushing the DNS Cache in OS X and Linux
created: 1236763669
categories:
- linux/unix
- os x
permalink: /2009/march/3/flushing-dns-cache-os-x-and-linux
---
In Leopard do:
<pre>
sudo dscacheutil -flushcache
</pre>
In Linux (Ubuntu):
<pre>
sudo /etc/init.d/nscd restart
</pre>

Update:

In OS X Yosemite:
<pre>
sudo discoveryutil mdnsflushcache
<pre>

In OS X Mavericks, Lion, Mountain Lion:

<pre>
sudo killall -HUP mDNSResponder
<pre>
