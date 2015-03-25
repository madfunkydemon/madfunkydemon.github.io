---
layout: post
title: Enable Non-Root Network Traffic Capture in Wireshark in Linux
created: 1307367251
categories:
- linux/unix
permalink: /2011/june/1/enable-non-root-network-traffic-capture-wireshark-linux
---
<p>&nbsp;Install wireshark as normal then run:</p>
<pre>
sudo setcap 'CAP_NET_RAW+eip CAP_NET_ADMIN+eip' /usr/bin/dumpcap
</pre>
<p>Then run wireshark and check that you can see your local interfaces.&nbsp;This has been tested in Ubuntu 11.04</p>
