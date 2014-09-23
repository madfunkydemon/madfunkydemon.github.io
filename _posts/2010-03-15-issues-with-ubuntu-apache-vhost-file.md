---
layout: post
title: Issues with Ubuntu Apache Vhost File
created: 1268659242
categories:
- linux/unix
---
<p>In Ubuntu server after an upgrade to apache, the process can copy your 000-default file and leave it with the name 000-default.save. This can cause issues with your vhost config and lead to unpredictable results. If you do have strange vhost issues, check in&nbsp;/etc/apache/sites-enabled and make sure that there is no duplication and all the files there are required. In my case it was causing the error:</p>
<p>[warn] NameVirtualHost *:80 has no VirtualHosts</p>
<p>&nbsp;</p>
