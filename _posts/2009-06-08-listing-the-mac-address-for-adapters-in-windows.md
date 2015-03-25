---
layout: post
title: Listing the MAC Address for Adapters in Windows
created: 1244456209
categories:
- windows
- networking
permalink: /2009/june/1/listing-mac-address-adapters-windows
---
<p>You can use this to list the MAC address on the current machine:</p>
<pre>
getmac /V

</pre>
<p>It also has remote options too:</p>
<pre>
getmac /S computer /U domain\user /P password

</pre>
<p>This is quite usefull when you do not have any protocols attached so the MAC will not show up in ipconfig. It saves you going through the GUI for each adapter you want to check. I'm not sure how I have missed this for so long...</p>

Update: This actually works on Windows 7 as well and probably 8. It is one of the quickest ways to find out MAC addreses, if I could ever remember it...
