---
layout: post
title: Disable Disk Signature Writing in Windows
created: 1269625402
categories:
- storage
- windows
permalink: /2010/march/5/disable-disk-signature-writing-windows/
---
<p>&nbsp;Windows default behaviour is to write to the disk signature of basic disks when they are attached/detected by windows. This can cause merry hell with iscsi volumes, especially those with existing setups. Start diskpart interactively and put in the following:</p>
<pre>
automount disable
<br type="_moz" /></pre>
<p>Then:</p>
<pre>
automount scrub
<br type="_moz" /></pre>
<p>The first setting disables automounting and the second resets any past configs for disks that have been previously attached.&nbsp;</p>
