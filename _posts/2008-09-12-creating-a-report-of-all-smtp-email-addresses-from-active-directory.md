---
layout: post
title: Creating a Report of ALL SMTP email addresses from Active Directory
created: 1221228351
categories:
- active directory
- windows
permalink: /2008/september/5/creating-report-all-smtp-email-addresses-active-directory
---
<pre>
&nbsp;Ldifde -d &quot;DC=domain,DC=co,DC=uk&quot; -r &quot;(&amp;(mailnickname=*))&quot; -l proxyAddresses -f Report.txt

</pre>
