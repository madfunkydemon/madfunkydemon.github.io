---
layout: post
title: Using an External Floppy Drive to Add Storage Drivers to a Windows Install
created: 1242219982
categories:
- windows
permalink: /2009/may/3/using-external-floppy-drive-add-storage-drivers-windows-install/
---
<p>When you add your third party storage drivers to a windows install (F6 if you catch it) using a USB floppy sometimes the install will fail after the format stage. At this point it is unable to communicate with the USB floppy even though it initially could. You can help it by adding the following to your 'textsetup.oem':</p>
<pre>
id = &quot;USB\VID_03F0&amp;PID_2001&quot;, &quot;usbstor&quot; #--HP<br />id = &quot;USB\VID_054C&amp;PID_002C&quot;, &quot;usbstor&quot; #--Sony<br />id = &quot;USB\VID_057B&amp;PID_0001&quot;, &quot;usbstor&quot; #--Y-E Data<br />id = &quot;USB\VID_0409&amp;PID_0040&quot;, &quot;usbstor&quot; #--NEC<br />id = &quot;USB\VID_0424&amp;PID_0FDC&quot;, &quot;usbstor&quot; #--SMSC<br />id = &quot;USB\VID_08BD&amp;PID_1100&quot;, &quot;usbstor&quot; #--Iomega<br />id = &quot;USB\VID_055D&amp;PID_2020&quot;, &quot;usbstor&quot; #--Samsung</pre>
<p>This will give windows a nudge in the right direction. In my case I only needed the <strong><em>Sony</em></strong> line for my <strong><em>Dell</em></strong> external floppy drive...</p>
<p>&nbsp;</p>
