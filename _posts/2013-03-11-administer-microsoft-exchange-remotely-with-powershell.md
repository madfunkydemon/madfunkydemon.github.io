---
layout: post
title: Administer Microsoft Exchange Remotely with Powershell
created: 1362997832
categories:
- windows
permalink: /2013/march/1/administer-microsoft-exchange-remotely-powershell
---
Rather than installing the remote exchange management tools and the pain that can cause, you can use powershell remoting. To setup powershell to connect to the exchange server pop the following into a powershell prompt on your client machine:
{% highlight powershell %}
$cred = get-credential
$myremote = New-PSSession -configurationname Microsoft.Exchange -connectionURI http://mail_server_name/Powershell -credential $cred
Import-PSSession $myremote
{% endhighlight %}
The first line prompts you for the account details to connect/manage exchange. Once you've entered the next two lines you should be able to run remote powershell commands. Once you have finished, just enter the following:
{% highlight powershell %}
Remove-PSSession $myremote
{% endhighlight %}
