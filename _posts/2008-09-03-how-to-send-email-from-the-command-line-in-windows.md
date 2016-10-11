---
layout: post
title: How to Send Email from the Command Line in Windows
created: 1220455345
categories:
- tools
- windows
permalink: /2008/september/3/how-send-email-command-line-windows/
---
<p>&nbsp;Blat is the way forward. Blat is a small, efficent SMTP command line mailer for Windows. It is the SMTP *sending* part of an eMail User Agent (MUA) or eMail client. As such, Blat sends eMail via SMTP (or internet eMail) from the command line, or CGI, ...</p>
<pre>
blat 1.txt -t Email@address.com -attach 1.bmp -base64 -html
<br type="_moz" /></pre>
<p>This will include the contents of 1.txt in the body of the email and attach the file 1.bmp. -attach is used for binary files and -attacht for txt files. &nbsp;You will need to configure a SMTP server.</p>
