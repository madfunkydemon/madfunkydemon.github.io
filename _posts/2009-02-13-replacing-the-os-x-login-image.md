---
layout: post
title: Replacing the OS X Login Image
created: 1234522124
categories:
- os x
permalink: /2009/february/5/replacing-os-x-login-image/
---
<p>If you need to replace the system default image in Leopard OS X 10.5. You can do this easily from the terminal:</p>
<pre>
sudo cp /System/Library/CoreServices/DefaultDesktop.jpg /System/Library/CoreServices/DefaultDesktop.jpg.bak

</pre>
<p>Then just copy in the image you want (you really want this to be the correct aspect ratio/resolution):</p>
<pre>
sudo cp ~/Pictures/filename.jpg /System/Library/CoreServices/DefaultDesktop.jpg

</pre>
<p><img alt="Custom Login Screen" src="/images/lock.jpg" /></p>
