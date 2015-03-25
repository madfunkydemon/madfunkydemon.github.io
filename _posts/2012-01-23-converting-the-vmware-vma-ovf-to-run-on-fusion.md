---
layout: post
title: Converting the VMware VMA Ovf to run on Fusion
created: 1327310399
categories:
- vsphere
permalink: /2012/january/1/converting-vmware-vma-ovf-run-fusion
---
<p>&nbsp;To get the vSphere Management Assistant appliance to run under VMware Fusion use the ovftool. You will need to download the VMA appliance from VMware, extract it and then cd to that directory. You will have to include the full path to the ovftool or include it in your classpath. Then:</p>
<pre>
ovftool vMA-5.0.0.0-472630_OVF10.ovf folder_name/
</pre>
<p>Where folder_name is a subdirectory in your extracted directory. When you run that command you will will have to accept the license agreement first. It may take a little while for the files to be created in your subdirectory. Once that has finished you should have a virtual machine you can open in Fusion. See here for more info on <a href="http://thewayeye.net/2011/april/2/converting-ovf-template-run-vmware-fusion">ovftool</a>&nbsp;on the Mac.</p>
