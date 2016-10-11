---
layout: post
title: Finding and Listing Email Addresses from Active Directory Groups with Powershell
created: 1234359212
categories:
- active directory
permalink: /2009/february/3/finding-and-listing-email-addresses-active-directory-groups-powershell/
---
<p>Get hold of the excellent <a href="http://www.quest.com/powershell/activeroles-server.aspx">Quest Free PowerShell Commands for Active Directory</a>, then once installed use the following command from the powershell (Quest) console:</p>
<pre>
Get-QADGroupMember &quot;group name&quot;  -Indirect | select name, email

</pre>
<p>Change &quot;group name&quot; to the AD group you are interested in querying. Indirect will give you results from nestled grouping. This works for distribution groups as well as other types. Use the following to output the results to a csv file:</p>
<pre>
Get-QADGroupMember groupname -Indirect | select name, email | Export-Csv filename.csv

</pre>
