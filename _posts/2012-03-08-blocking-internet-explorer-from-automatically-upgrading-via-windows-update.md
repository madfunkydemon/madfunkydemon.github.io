---
layout: post
title: Blocking Internet Explorer from Automatically Upgrading Via Windows Update
created: 1331207242
categories:
- windows
- active directory
permalink: /2012/march/4/blocking-internet-explorer-automatically-upgrading-windows-update/
---
You have a few options for doing this especially if you are using something like WSUS. However if you aren't, then a registry change via group policy or logon script is probably the best option. Here is a a registry file that will block automatic upgrade to internet explorer 8 and 9:

`Windows Registry Editor Version 5.00`
   
`[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Internet Explorer\Setup]`

`[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Internet Explorer\Setup\8.0]`
`"DoNotAllowIE80"=dword:00000001`

`[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Internet Explorer\Setup\9.0]`
`"DoNotAllowIE90"=dword:00000001`

If you are only interested in blocking one version of internet explorer then just remove the appropriate lines. To use group policy to deploy the registry settings you need a method to apply the reg file. I tend to use the following VBS script:
{% highlight vbnet %}
Set oShell = CreateObject("Wscript.Shell") 
'The .Reg file path goes here
sRegFile = "\\path_to_reg_file\file.reg" 
'Regedit in silent mode
oShell.Run "regedit.exe /s " & Chr(34) & sRegFile & Chr(34), 0, True
Set oShell = NOTHING
{% endhighlight %}
Copy the text into a text file with the extension .vbs and attach this to a logon group policy in the usual way.
