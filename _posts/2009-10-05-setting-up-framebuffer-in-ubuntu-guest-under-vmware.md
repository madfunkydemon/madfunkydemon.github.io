---
layout: post
title: Setting up framebuffer in Ubuntu guest under vmware
created: 1254751497
categories:
- linux/unix
---
Log into the linux guest and make sure you have hwlist installed. If you haven't you can install it with:

`sudo aptitude install hwinfo`

Once that is installed run the following:

`sudo hwinfo --framebuffer`

This returns all the compatible modes:
{% highlight bash %}
02: None 00.0: 11001 VESA Framebuffer
[Created at bios.450]
Unique ID: rdCR.O3PgoQaqFo1
Hardware Class: framebuffer
Model: "VMware virtual machine"
Vendor: "VMware, Inc"
Device: "VMware virtual machine"
SubVendor: "V M ware, Inc. VBE support 2.0"
SubDevice:
Revision: "2.0"
Memory Size: 62 MB + 512 kB
Memory Range: 0xd0000000-0xd3e7ffff (rw)

Mode 0x0362: 1280x720 (+1280), 8 bits
Mode 0x0363: 1280x720 (+2560), 16 bits
Mode 0x0364: 1280x720 (+5120), 24 bits
Mode 0x0365: 1920x1080 (+1920), 8 bits
Mode 0x0366: 1920x1080 (+3840), 16 bits
Mode 0x0367: 1920x1080 (+7680), 24 bits
{% endhighlight %}
<strong> Many more entries here, too many to post</strong>

Pick the mode that you want to use, in my case '0379' (1280x768). This translates to the VGA mode 889 (convert from hex to decimal). You can test these modes out safely by pressing escape at the grub boot menu and manually adding the kernel parameter. Once you are happy that it works as expected, add the change to your grub menu.lst

<img src="/images/sc.jpg" />
