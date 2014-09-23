---
layout: post
title: USB Network Interface Missing from Wireshark Interface List
created: 1391720139
categories:
- wireshark
---
I needed to do some packet capturing in windows, so I added a USB network interface to an ultra-book. Upon running wireshark the USB network adapter was conspicuous by its absence from the interface list. After a bit of mulling over I wondered if WinPCap was not aware of the adapter; as these days WinPCap runs as a service. The service is called NPF (NetGroup Packet Filter). So:
{% highlight bash %}
net stop npf
{% endhighlight %}
and
{% highlight bash %}
net Start npf
{% endhighlight %}
Low and behold, after starting wireshark a full list of network adapters was presented. Game on, bring me the packets.
