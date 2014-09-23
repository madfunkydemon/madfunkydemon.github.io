---
layout: post
title: Flushing the DNS Cache in OS X and Linux
created: 1236763669
categories:
- linux/unix
- os x
---
<p>In Leopard do:</p>
<pre>
dscacheutil -flushcache
</pre>
<p>In Linux (Ubuntu):</p>
<pre>
sudo /etc/init.d/nscd restart
</pre>
