---
layout: post
title: Converting an Ovf Template to run in VMware Fusion
created: 1303216417
categories:
- os x
- vmware
permalink: /2011/april/2/converting-ovf-template-run-vmware-fusion
---
<p>VMware has a tool called ovftool. You need to do a full, custom install of Fusion to get the ovf tool. It is located in:</p>
<pre>
/Library/Application Support/VMware Fusion/ovftool
</pre>
<p>Change to this directory and run the following to see examples:</p>
<pre>
./ovftool --help examples</pre>
<p>To run a basic conversion use:</p>
<pre>
./ovftool path_to_ovf_file.ovf /output_directory/
</pre>
<p>This will convert the ovf into a format that Fusion can try to boot. This will not enable a virtual machine with incompatable hardware to boot.</p>
<p>UPDATE<br />
<br />
As of VMware Fusion 4, the OVF tool is a seperate download and once installed it is located in:</p>
<pre>
/Applications/VMware OVF Tool
</pre>
<p>&nbsp;</p>
