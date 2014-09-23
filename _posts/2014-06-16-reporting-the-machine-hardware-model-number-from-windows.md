---
layout: post
title: 'Reporting the Machine Hardware Model Number from Windows '
created: 1402927792
categories:
- windows
---
You can pull this information from wmi. This method is useful when you are on the other side of the world to the machine you are working on. All you need is a local or remote shell via psexec or powershell, and type the following:

`wmic csproduct get name`

Here are some sample results:
{% highlight bash %}
Name
HP Z420 Workstation

Name
PRIMERGY BX924 S4

Name
ProLiant DL380 G7
{% endhighlight %}
