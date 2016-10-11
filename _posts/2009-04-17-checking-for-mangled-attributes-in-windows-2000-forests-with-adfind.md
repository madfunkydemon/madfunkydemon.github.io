---
layout: post
title: Checking for Mangled Attributes in Windows 2000 Forests with Adfind
created: 1239966850
categories:
- active directory
permalink: /2009/april/5/checking-mangled-attributes-windows-2000-forests-adfind/
---
<p>&nbsp;From <a href="http://support.microsoft.com/kb/314649">link</a>:</p>
<p><strong>&quot;</strong>The Microsoft Exchange 2000 schema defines three non-Request for Comments (RFC)-compliant attributes: houseIdentifier, Secretary, and labeledURI. The Microsoft Windows 2000 InetOrgPerson Kit redefines the Secretary attribute and the labeledURI attribute. The adprep /forestprep command in Microsoft Windows Server 2003 has redefined all three attributes as described in Request for Comments (RFC) 2798.</p>
<p>If Exchange 2000 created these three attributes before you ran the Windows 2000 InetOrgPerson Kit, the LdapDisplayName attribute for the houseIdentifier attribute becomes conflicted or &quot;mangled&quot; after the new RFC-compliant definitions are added by Windows Server 2003 adprep /forestprep replication. If Exchange 2000 created these three attributes before you ran the Windows Server 2003 adprep /forestprep command, all three attributes become mangled. These conflicts do not occur if the Windows Server 2003 adprep /forestprep command creates these attributes before you install Exchange 2000.<strong>&quot;</strong></p>
<p>To find out what your current&nbsp;lDAPDisplayName&nbsp;values are use using <a href="http://www.joeware.net/freetools/tools/adfind/index.htm">Adfind</a>:</p>
<pre>
AdFind -b CN=ms-Exch-House-Identifier,CN=Schema,CN=Configuration,DC=letchworth,DC=local ldapdisplayname -list

AdFind -b CN=ms-Exch-LabeledURI,CN=Schema,CN=Configuration,DC=letchworth,DC=local ldapdisplayname -list

AdFind -b CN=ms-Exch-House-Identifier,CN=Schema,CN=Configuration,DC=letchworth,DC=local ldapdisplayname -list</pre>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
