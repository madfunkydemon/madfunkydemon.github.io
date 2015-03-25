---
layout: post
title: Finding Your External IP from Linux/BSD
created: 1273061287
categories:
- linux/unix
- os x
permalink: /2010/may/3/finding-your-external-ip-linuxbsd
---
<p>&nbsp;If you have curl installed:</p>
<pre>
echo &quot;External IP:&quot; `curl -s http://checkip.dyndns.org/ | awk '{print $6}' | cut -f 1 -d &quot;&lt;&quot;`
</pre>
<p>This comes in real handy if you move sites and have more than one route out. It also works rather well from OSX Geektool.</p>
