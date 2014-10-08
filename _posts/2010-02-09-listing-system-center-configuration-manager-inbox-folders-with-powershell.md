---
layout: post
title: Listing System Center Configuration Manager Inbox Folders with Powershell
created: 1265705113
categories:
- powershell
- windows
---
It is a good idea to keep track of these folders as they can get out of control quite quickly. This powershell command quickly highlights if you have any build up going on. Look out for large numbers of files:
{% highlight powershell %}
Get-ChildItem “c:\Program Files\Microsoft Configuration Manager\inboxes” -recurse | Where {!$_.PSIsContainer} | Group Directory | Format-Table Name, Count -autosize
{% endhighlight %}
<img alt="SCCM" width="498" height="167" src="/images/sccm.gif" />
