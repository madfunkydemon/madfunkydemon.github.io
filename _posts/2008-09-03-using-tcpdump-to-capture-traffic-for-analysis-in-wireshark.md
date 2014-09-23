---
layout: post
title: Using tcpdump to Capture Traffic for Analysis in Wireshark
created: 1220469497
categories:
- networking
---
<p>&nbsp;Use the following:</p> <pre>
tcpdump -i &lt;interface> -s 1500 -w &lt;some-file>

</pre><p>tcpdump will only cature the first 68 bytes so you need to change the value to your packet size.</p>
