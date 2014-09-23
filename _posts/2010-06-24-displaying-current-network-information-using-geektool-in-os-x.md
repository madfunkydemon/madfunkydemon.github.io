---
layout: post
title: 'Displaying Current Network Information Using Geektool in OS X '
created: 1277396296
categories:
- os x
---
<p>&nbsp;I have put together a script from a variety of sources including some customisations which displays the following information in the form:</p>
<pre>
External : x.x.x.x
Ethernet : INACTIVE
SSL      : x.x.x.x
AirPort  : x.x.x.x SSID: name Channel: 4</pre>
<p>The External entry uses http://checkip.dyndns.org/ to get the current external IP address.<br />
Ethernet give you your local wired ipv4 address.<br />
SSL displays the current Juniper Network Connect assigned IP address.<br />
Airport shows the currently connected wireless network (SSID) and the associated channel.</p>
<p>It should detect if any of the connections are inactive. It has been tested on a Macbook Pro (17inch) Mac OS X 10.6.4. This may well be affected by updates to the OS as it is expecting specific output.</p>
<p>You can drop the script text directly into the Geektool script editor.</p>
<p><a href="/sites/default/files/myipinfo">myipinfo</a></p>
<p>I have made an executable version of the script so it can be called from a normal terminal.</p>
