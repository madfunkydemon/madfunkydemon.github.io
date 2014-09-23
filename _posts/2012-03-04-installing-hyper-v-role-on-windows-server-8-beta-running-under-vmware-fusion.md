---
layout: post
title: Installing Hyper-V Role on Windows Server 8 Beta Running Under VMware Fusion
created: 1330899431
categories:
- os x
- vmware
- hyper-v
---
<p>&nbsp;This is a catchy title, but if you are interested in playing with Hyper-V 3 then add the following to your virtual machine vmx file:</p>
<p class="p1">vhv.enable = &quot;TRUE&quot;<br />
hypervisor.cpuid.v0 = &quot;FALSE&quot;<br />
mce.enable = &quot;TRUE&quot;</p>
<p>Once you have added these lines you are good to install the Beta and add the Hyper-V 3 Role. If you miss out the 'mce.enable' line, when you reboot after adding the Hyper-V role you get a blue screen with an error complaining about&nbsp;hal_initialization_failed, so make sure you include it.</p>
