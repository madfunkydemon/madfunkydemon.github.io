---
layout: post
title: ' Exporting info from AD as CSV'
created: 1220398468
categories:
- active directory
permalink: /2008/september/3/exporting-info-ad-csv
---
<p>If you want to export AD info as CSV then csvde is the cmd for you, for example:</p><pre>
csvde -s clyde -f users.csv -r objectClass=user -l &quot;givenName, sn, name, sAMAccountName&quot;</pre>
