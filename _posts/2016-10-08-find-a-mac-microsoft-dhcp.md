---
layout: post
title: 'Searching for a DHCP Lease by MAC Address'
categories:
- windows
- powershell

---
Sometimes in a large infrastructure it can be hard to find new devices added to the network. Being able to search on MAC address across all DHCP scopes comes in handy. With powershell and windows DHCP server this is easy to do. You can use the RSAT tools or directly on the DHCP server. The only difference being with the RSAT tools you need to add the DHCP server name via the -ComputerName switch. To begin you can list all the leases on the current server with:
{% highlight powershell %}
Get-DhcpServerv4Scope | Get-DhcpServerv4Lease
{% endhighlight %}
Which should give you the following output:

<p><img alt="Powershell DHCP Lease Search" width="720" height="118" src="/images/ps-search.png" /></p>

That should be a full list of active leases, to narrow the results down by MAC address use:
{% highlight powershell %}
Get-DhcpServerv4Scope | Get-DhcpServerv4Lease -EA SilentlyContinue -ClientId 00-0c-29-dc-a5-3b
{% endhighlight %}
Resulting in:

<p><img alt="Powershell DHCP Lease Search Filter" width="720" height="137" src="/images/ps-search-filter.gif" /></p>

The -EA blocks any failures from scopes that do not have any matches so makes the output nicer. Another handy tip is a quick way to find a free IP in a defined DHCP scope:
{% highlight powershell %}
PS C:\Users\Administrator> Get-DhcpServerv4FreeIPAddress -ScopeId 10.10.100.0
10.10.100.53
{% endhighlight %}