---
layout: post
title: Listing System Center Configuration Manager Inbox Folders with Powershell
created: 1265705113
categories:
- powershell
- windows
---
<pre>
 Get-ChildItem &ldquo;c:\Program Files\Microsoft Configuration Manager\inboxes&rdquo; -recurse | Where {!$_.PSIsContainer} | Group Directory | Format-Table Name, Count -autosiz
</pre>
<p><img alt="SCCM" width="498" height="167" src="/sites/default/files/sccm.gif" /></p>
<p>&nbsp;</p>
