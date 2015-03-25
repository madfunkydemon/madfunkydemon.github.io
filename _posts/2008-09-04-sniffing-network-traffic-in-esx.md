---
layout: post
title: 'Sniffing Network Traffic in ESX '
created: 1220540647
categories:
- esx
- virtualisation
- networking
permalink: /2008/september/4/sniffing-network-traffic-esx
---
<p>If you want to enable promiscuous network sniffing within a vSwitch the safest way to do it is to create a second port group.  Promiscuous mode can be enabled on an existing port group but once this has been done, any device connected to that port group has that ability.</p>
<p class="MsoNormal"><img alt="Port Group Summary" width="237" height="102" src="/sites/default/files/p.PNG" /></p>
<p class="MsoNormal">Once you have your second port group correctly configured you can attach a monitoring appliance. To do my monitoring I tend to use OpenBSD with tcpdump and then use Wireshark to analyse the data.  Log into your OpenBSD machine and bring up the NIC without allocating it an IP:</p>
<pre>
Ifconfig vic0 up

</pre>
<p>Once that is up you can start capturing data:</p>
<pre>
tcpdump -i vic0 -s 1500

</pre>
<p>When you have your data you can import it into Wireshark to filter out the uninteresting traffic. &nbsp;It seems that if you do not include a VLAN tag in your promiscuous mode port group you can capture the network traffic from your trunked VLAN port. &nbsp;You can use Wireshark to filter the VLAN you are interested in from your packet capture output:</p>
<p><img alt="Wireshark" width="430" height="115" src="/sites/default/files/c.PNG" /></p>
