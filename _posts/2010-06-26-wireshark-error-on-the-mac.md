---
layout: post
title: Wireshark Error on the Mac
created: 1277545313
categories:
- os x
permalink: /2010/june/6/wireshark-error-mac/
---
<p>When you reboot and get this error after installing Wireshark on the mac:</p>
<p>&quot;Insecure startup item disabled chmodBPF&quot;</p>
<p>I always forget where the file is that needs the permissions change. So for my failing memory:</p>
<pre>
cd /Library/StartupItems
sudo chown -R root:wheel ChmodBPF
</pre>
