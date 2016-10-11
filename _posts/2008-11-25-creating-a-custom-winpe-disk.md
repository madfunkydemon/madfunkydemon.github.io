---
layout: post
title: Creating A Custom WinPE Disk
created: 1227611615
categories:
- windows
permalink: /2008/november/2/creating-custom-winpe-disk/
---
<p>Currently I am using this to run Dell updates on non windows operating systems that are not directly supported.</p>
<pre>
imagex /mountrw c:\winpe_x86\winpe.wim 1 c:\winpe_x86\mount

imagex /unmount /commit c:\winpe_x86\mount

copy c:\winpe_x86\winpe.wim c:\winpe_x86\ISO\sources\boot.wim

oscdimg.exe -n -bc:\winpe_x86\etfsboot.com c:\winpe_x86\ISO c:\winpe_x86\dell.iso
</pre>
