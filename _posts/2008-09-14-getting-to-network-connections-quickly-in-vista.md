---
layout: post
title: Getting to Network Connections Quickly in Vista
created: 1221393367
categories:
- windows
permalink: /2008/september/7/getting-network-connections-quickly-vista/
---
<p>Pop this into the run dialog:</p>
<pre>
control ncpa.cpl

</pre>
<p>This will also work for the following:</p>
<p>control printers = Printers&nbsp;<br />
control sysdm.cpl = System Properties<br />
control appwiz.cpl = Programs &amp; Features (Add &amp; Remove)</p>
<p>This can also be coupled with 'Runas':</p>
<pre>
runas /user:computername\Administrator &quot;rundll32.exe shell32.dll,Control_RunDLL&nbsp;ncpa.cpl&quot;

</pre>
