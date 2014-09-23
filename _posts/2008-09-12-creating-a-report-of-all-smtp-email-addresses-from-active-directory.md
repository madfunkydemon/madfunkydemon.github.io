---
layout: post
title: Creating a Report of ALL SMTP email addresses from Active Directory
created: 1221228351
categories:
- active directory
- windows
---
<pre>
&nbsp;Ldifde -d &quot;DC=domain,DC=co,DC=uk&quot; -r &quot;(&amp;(mailnickname=*))&quot; -l proxyAddresses -f Report.txt

</pre>
