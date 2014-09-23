---
layout: post
title: Unable to use Wireless and Wired Connections In Windows 8
created: 1391722930
categories:
- windows
---
I needed to do this recently and had a few issues. I guess it is not often required to have multiple connections but every now and then it crops up. Historically drivers sometimes caused issues and usually down to power options, understandability to reduce load on batteries. However this time it turned out to be windows that is effecting things. Cutting a long story short, to find the culprit setting run:
{% highlight bash %}
 gpedit.msc
{% endhighlight %}
Then navigate to: Local Computer Policy &gt; Computer Configuration &gt; Administrative Templates &gt; Network &gt; Windows Connection Manager. Once there, look for the policy &quot;Minimise the number of connections to the Internet or a Windows Domain&quot;. This needs to be set to disabled. Looking at the policy description this may cause issues with multiple wired network connections. Here is a snippet from the policy so you can see the expected behavior:

>If this policy setting is enabled, when the computer has at least one active connection to the Internet, a new automatic connection attempt to the Internet is blocked. When the computer has at least one active connection to a Windows domain, a new automatic connection to the same Windows domain is also blocked. Additional manual connection attempts by users to the Internet or to a Windows domain are not blocked by this policy setting.
In circumstances where there are multiple simultaneous connections to either the Internet or to a Windows domain, Windows disconnects the less preferred connection when the amount of network traffic over the less preferred connection drops below a certain threshold. For example, when a computer is connected to Internet using a Wi-Fi connection and the user plugs in to an Ethernet network, network traffic is routed through the faster Ethernet connection, and the Wi-Fi traffic diminishes. Windows detects this circumstance and responds by disconnecting the Wi-Fi connection.
If this policy setting is disabled, multiple simultaneous connections to the Internet, to a Windows domain, or to both are allowed.
