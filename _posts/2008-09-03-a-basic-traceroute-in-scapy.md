---
layout: post
title: A Basic Traceroute in Scapy
created: 1220450108
categories:
- networking
permalink: /2008/september/3/basic-traceroute-scapy
---
<pre>
ans,unans=traceroute(['www.google.co.uk','www.yahoo.com','www.microsoft.com'])
ans<br />ans.graph(target=&quot;> /tmp/graph.svg&quot;)</pre><p>&nbsp;<img alt="Traceroute" width="457" height="823" src="images/scapy.gif" /></p>
