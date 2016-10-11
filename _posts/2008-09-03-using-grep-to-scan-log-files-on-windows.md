---
layout: post
title: Using Grep to Scan Log Files on Windows
created: 1220451805
categories:
- windows
permalink: /2008/september/3/using-grep-scan-log-files-windows/
---
<p>Use the following to find&nbsp;Forbidden errors from web server logs:</p>
<pre>
grep &quot;403&quot; \\machine\i$\LogFiles\W3SVC1\ex0*
<br type="_moz" /></pre>
<p>You can get GNU utilities for Windows which includes grep.</p>
<p>Microsoft has its own version of grep called QGREP which is part of the 2003 resource kit.</p>
