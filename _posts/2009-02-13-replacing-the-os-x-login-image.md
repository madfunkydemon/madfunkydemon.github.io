---
layout: post
title: Replacing the OS X Login Image
created: 1234522124
categories:
- os x
---
<p>You need to replace the system default image. You can do this easily from the terminal:</p>
<pre>
sudo cp /System/Library/CoreServices/DefaultDesktop.jpg /System/Library/CoreServices/DefaultDesktop.jpg.bak

</pre>
<p>Then just copy in the image you want (you really want this to be the correct aspect ratio/resolution):</p>
<pre>
sudo cp ~/Pictures/filename.jpg /System/Library/CoreServices/DefaultDesktop.jpg

</pre>
<p><a href="/sites/default/files/lock.jpg"><img alt="Custom Login Screen" width="288" height="180" class="triggerclass" src="/sites/default/files/small_lock.jpg" /></a></p>
