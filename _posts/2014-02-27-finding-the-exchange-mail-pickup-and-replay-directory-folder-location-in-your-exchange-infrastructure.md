---
layout: post
title: 'Finding the Exchange Mail Pickup and Replay Directory Folder Location in Your
  Exchange Infrastructure '
created: 1393494285
categories:
- powershell
permalink: /2014/february/4/finding-exchange-mail-pickup-and-replay-directory-folder-location-your-exchange-infr
---
Use the following powershell command to return the mail pickup folder location from all your Edge and Hub Transport servers.
{% highlight powershell %}
Get-TransportServer | Fl name, *PickupDirectoryPath*
{% endhighlight %}
If you are interested in a single server add -Identity:
{% highlight powershell %}
Get-TransportServer -Identity "Server Name" | Fl name, *PickupDirectoryPath*
{% endhighlight %}
Where "Server Name" is the Exchange box you are interested in.
