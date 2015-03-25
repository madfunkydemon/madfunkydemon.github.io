---
layout: post
title: Running Network WMI Queries on the Command Line
created: 1269536662
categories:
- windows
permalink: /2010/march/4/running-network-wmi-queries-command-line
---
<p>&nbsp;Try:</p>
<pre>
wmic /node:machine_name product get name,version,vendor
<br type="_moz" /></pre>
<p>Where machine_name is the computer you are interested in. You will need the correct permissions to get to the remote machine. This example just returns installed software.</p>
<p>&nbsp;</p>
