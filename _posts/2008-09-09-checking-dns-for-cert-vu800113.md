---
layout: post
title: 'Checking DNS for CERT VU#800113 '
created: 1220983749
categories:
- networking
permalink: /2008/september/2/checking-dns-cert-vu800113/
---
<p>&nbsp;You can use the following web service to see if your DNS servers or resolvers need attention.&nbsp;</p>
<p>For Windows:</p>
<pre>
nslookup -querytype=TXT -timeout=10 porttest.dns-oarc.net.
nslookup -querytype=TXT -timeout=10 porttest.dns-oarc.net. <em>DnsServerName</em>
</pre>
<p>For *nix:</p>
<pre>
dig +short porttest.dns-oarc.net TXT 
dig @<em>DnsServerName&nbsp;</em>+short&nbsp;porttest.dns-oarc.net TXT</pre>
<p>Where&nbsp;DnsServerName is the name of the DNS server you want to check.</p>
<p>You are looking for&nbsp;GREAT, GOOD or POOR in the results.</p>
<p><a href="https://www.dns-oarc.net/oarc/services/porttest">Original Reference</a></p>
