---
layout: post
title: Stopping MIB Module Errors When Starting Wireshark in os x
created: 1238592549
categories:
- os x
permalink: /2009/april/3/stopping-mib-module-errors-when-starting-wireshark-os-x/
---
<p>&nbsp;If you get the following error on&nbsp;startup&nbsp;in wireshark:</p>
<pre>
The following errors were found while loading the MIBS ........

</pre>
<p>Then add this path to the 'name resolution' setting under edit &gt; preferences:</p>
<pre>
/usr/share/snmp/mibs/

</pre>
<p>Make sure to apply the change before you exit.</p>
