---
layout: post
title: Setting up Framebuffer on Ubuntu for the EEE PC 901
created: 1220836239
categories:
- linux/unix
---
<p>If you haven't got hwinfo installed then:</p>
<pre>
sudo aptitude install hwinfo

</pre>
<p>Then put this in:</p>
<pre>
sudo hwinfo --framebuffer

</pre>
<p>Returns :</p>
<pre>
02: None 00.0: 11001 VESA Framebuffer
[Created at bios.447]
Unique ID: rdCR.il6towt04X5
Hardware Class: framebuffer<br />Model: &quot;Intel(r) 82945GM Chipset Family Graphics Chip Accelerated VGA BIOS Intel(r) 82945GM Chipset Family Graphics Controller&quot;<br />Vendor: &quot;Intel Corporation&quot;<br />Device: &quot;Intel(r) 82945GM Chipset Family Graphics Controller&quot;<br />SubVendor: &quot;Intel(r) 82945GM Chipset Family Graphics Chip Accelerated VGA BIOS&quot;<br />SubDevice:<br />Revision: &quot;Hardware Version 0.0&quot;<br />Memory Size: 7 MB + 704 kB<br />Memory Range: 0xd0000000-0xd07affff (rw)<br />Mode 0x0312: 640x480 (+2560), 24 bits<br />Mode 0x0314: 800x600 (+1600), 16 bits<br />Mode 0x0315: 800x600 (+3200), 24 bits<br />Mode 0x0301: 640x480 (+640), 8 bits<br />Mode 0x0303: 800x600 (+832), 8 bits<br />Mode 0x0311: 640x480 (+1280), 16 bits<br />Config Status: cfg=new, avail=yes, need=no, active=unknown</pre>
<div>Which seems to suggest the highest framebuffer resolution the 901 supports is 800x600, 24 bits. &nbsp;This translates to the&nbsp;VGA mode 789 which can be passed as a kernel parameter. &nbsp;Edit the following:</div>
<div>&nbsp;</div>
<pre>
sudo nano /boot/grub/menu.lst

</pre>
<div>Adding the following kernel parameter 'vga=789' your default kernel options. &nbsp;I tend to get rid of the 'splash' parameter as it does not play well with the framebuffer.</div>
<div>&nbsp;</div>
<div>Then reboot and log in to a terminal:</div>
<div>&nbsp;</div>
<div>&nbsp;<img alt="lap" width="478" height="314" src="/sites/default/files/cs_0.jpg" /></div>
<p>&nbsp;</p>
