---
layout: post
title: Report a Dell Service Tag Remotely
created: 1231330047
categories:
- windows
---
<p>Create a text file with the following:&nbsp;</p>
<pre>
ComputerName = InputBox(&quot;Computer Name&quot;)<br />strComputer = ComputerName<br />Set objWMIService = GetObject(&quot;winmgmts:&quot; _<br />&amp; &quot;{impersonationLevel=impersonate}!\\&quot; &amp; strComputer &amp; &quot;\root\cimv2&quot;)<br />Set colSMBIOS = objWMIService.ExecQuery _<br />(&quot;Select * from Win32_SystemEnclosure&quot;)<br />For Each objSMBIOS in colSMBIOS<br />Wscript.Echo &quot;Service Tag: &quot; &amp; objSMBIOS.SerialNumber<br />Next</pre>
<p>Save it as a vbs then run:</p>
<pre>
cscript filename.vbs

</pre>
<p>You will need to run the script with the correct permissons to WMI.</p>
