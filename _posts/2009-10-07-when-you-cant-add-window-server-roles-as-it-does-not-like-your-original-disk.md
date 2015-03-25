---
layout: post
title: When you can't add window server roles as it does not like your original disk
created: 1254913797
categories:
- windows
permalink: /2009/october/3/when-you-cant-add-window-server-roles-it-does-not-your-original-disk
---
<p>&nbsp;Once you have run a service pack on a server and you try to add a server role, often it will not accept your original source disk. In this case you need to extract the service pack files. For example in the case of Windows 2003 Server SP2, use the command prompt with /x switch to extract the files:&nbsp;</p>
<pre>
WindowsServer2003-KB914961-SP2-x86-ENU.exe \x:c:\path-to-folder

</pre>
<p>Once it has extracted the files try to add the server role, this time hopefully with success.</p>
