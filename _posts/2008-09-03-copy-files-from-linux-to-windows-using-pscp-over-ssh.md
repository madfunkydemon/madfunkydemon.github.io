---
layout: post
title: ' Copy Files from Linux to Windows using pscp Over SSH'
created: 1220452638
categories:
- windows
permalink: /2008/september/3/copy-files-linux-windows-using-pscp-over-ssh/
---
<p>Use the following program that comes with putty to copy files from *nix machine to a windows machine.</p>
<pre>
pscp -r -C User@Machine:/var/log/httpd/* c:\weblog\
<br /></pre>
<p>-C Enables compression, which sounds like a good shout accross slow links.</p>
