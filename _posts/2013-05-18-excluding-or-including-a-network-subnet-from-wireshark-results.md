---
layout: post
title: Excluding or Including a Network/Subnet from Wireshark Results
created: 1368916948
categories:
- wireshark
permalink: 2013-05-18-excluding-or-including-a-network-subnet-from-wireshark-results.md
---
You can use this wireshark filter to restrict results to the network you are interested in:

`ip.addr == 10.10.0.0/16`

Since we are not specifying a source or destination (i.e. ip.src or ip.dst), the filter will match both. If you want to reverse it then:

`!(ip.addr == 10.10.0.0/16)`

I'll often use the same method to filter the results on a specific IP address, preserving both ends of the conversation:

`ip.addr == 10.10.10.50`
