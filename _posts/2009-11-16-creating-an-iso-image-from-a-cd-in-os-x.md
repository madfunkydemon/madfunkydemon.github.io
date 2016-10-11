---
layout: post
title: Creating an ISO image from a CD in OS X
created: 1258374371
categories:
- os x
permalink: /2009/november/1/creating-iso-image-cd-os-x/
---
<p>&nbsp;You need to find the device path of your CD drive.:</p>
<pre>
drutil status
</pre>
<p>Look through the status info for the CD dvice path. It will look like /dev/disk3 or /dev/disk1 depending on your hardware. You then need to unmount the disk:</p>
<pre>
diskutil unmountDisk /dev/disk3 
</pre>
<p>Now you can use use dd to make an image:</p>
<pre>
dd if=/dev/disk3s0 of=file_name.iso
</pre>
<p>To mount the image you created:</p>
<pre>
hdiutil mount file_name.iso
</pre>
<p>&nbsp;</p>
