---
layout: post
title: Changing the postfix banner
created: 1256837012
categories:
- linux/unix
permalink: /2009/october/4/changing-postfix-banner
---
Make sure that when you send mail from web hosts you have a reverse lookup name that matches your postfix banner. Otherwise you can sometimes get marked as spam by some providers. Use the following to set the postfix name:

`postconf -e myhostname=servername`

Where 'servername' is the name of your PTR record. Remember to restart postfix once you have made this change. You can check this with netcat or telnet:

`nc machine 25`

Where 'machine' is the address or name of the machine you want to test. The reply from this should be something like:

`220 mail.something.com ESMTP Postfix (Ubuntu)`

Depending on what you are running. This can be a problem when the web server has been cloned or renamed.
