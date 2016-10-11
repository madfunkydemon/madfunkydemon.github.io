---
layout: post
title: How to Install Software in the VMware VMA
created: 1327310655
categories:
- vsphere
permalink: /2012/january/1/how-install-software-vmware-vma/
---
<p>&nbsp;I am sure this is not supported and therefore not recommended but installing software in the vSphere Management Assistant is possible as it is just a SUSE Linux Enterprise Server 11 virtual machine. You can use the following to search for software:</p>
<pre>
sudo zypper search nano
</pre>
<p>This will search for nano. Once you have found the package you want to install then use the following to install it:</p>
<pre>
sudo zypper install nano
</pre>
<p>Note the first time you run this you are prompted to accept the openSUSE package signing key. This is up to you and no one else...</p>
