---
layout: post
title: Quick Method to List Disks in Windows
created: 1391720587
categories:
- windows
permalink: /2014/february/4/quick-method-list-disks-windows/
---
There are numerous ways to do this. However using the WMI from a command prompt does the job:

    wmic diskdrive list brief 

It is quick and easy to remember, having the benefit that it can be run remotely using a remote shell like Powershell or psexec.  Sample output:
{% highlight bash %}
C:\windows\system32>wmic diskdrive list brief
Caption              DeviceID            Model                Partitions  Size
LITEONIT LMT-128M3M  \\.\PHYSICALDRIVE0  LITEONIT LMT-128M3M  2           128034708480
{% endhighlight %}

Even though it is easy to remember, I'm putting it here as I'll forget.
