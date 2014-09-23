---
layout: post
title: Listing the MAC Address for Adapters in Windows
created: 1244456209
categories:
- windows
- networking
---
<p>You can use this to list the MAC address on the current machine:</p>
<pre>
getmac

</pre>
<p>It also has remote options too:</p>
<pre>
getmac /S computer /U domain\user /P password

</pre>
<p>This is quite usefull when you do not have any protocols attached so the MAC will not show up in ipconfig. It saves you going through the GUI for each adapter you want to check. I'm not sure how I&nbsp;have missed this for so long...</p>
