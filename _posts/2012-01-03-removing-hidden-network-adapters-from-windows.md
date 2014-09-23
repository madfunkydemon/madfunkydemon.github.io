---
layout: post
title: 'Removing Hidden Network Adapters from Windows '
created: 1325612125
categories:
- windows
- vmware
---
<p>&nbsp;Windows device manager does not always allow you to see old adapters once the hardware has been removed. You can enable it to do so but when you are dealing with large numbers of virtual machines you need another approach. Devcon can enable you to do this and can be found&nbsp;<a href="http://support.microsoft.com/kb/311272">here</a>&nbsp;if you are after the 32bit version. However there is no 64bit version (just the 32bit &amp; itanium version). To get the 64bit version you have to get hold of the Windows Device Driver kit <a href="http://www.microsoft.com/download/en/details.aspx?id=11800">here</a>. It is a 600Mb+ download which is large when you only want the one file. Once downloaded locate this file &quot;setuptools_x64fre.msi&quot;. You can find it in the WINDDK folder of the iso. Extract the msi out with the following:</p>
<pre>
msiexec /a setuptools_x64fre.msi /qb TARGETDIR=&quot;C:\PATH_TO_FOLDER&quot;
</pre>
<p>You will find the 64bit version of devcon in the folder sturcture created e.g.:</p>
<p>WinDDK\7600.16385.win7_wdk.100208-1538\tools\devcon\amd64</p>
<p>Once you have the correct version of devcon you can use it to generate a full list of network adapters:</p>
<pre>
devcon findall =net</pre>
<p>It will generate something like:</p>
<address>PCI\VEN_15AD&amp;DEV_07B0&amp;SUBSYS_07B015AD&amp;REV_01\FF290C008E0E28FE00: vmxnet3 Ethernet Adapter<br />
PCI\VEN_15AD&amp;DEV_07B0&amp;SUBSYS_07B015AD&amp;REV_01\FF290C00F1B6A9FE00: vmxnet3 Ethernet Adapter #2<br />
PCI\VEN_8086&amp;DEV_100F&amp;SUBSYS_075015AD&amp;REV_01\4&amp;3AD87E0A&amp;0&amp;0888: Intel(R) PRO/1000 MT Network Connection<br />
ROOT\*ISATAP\0000 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; : Microsoft ISATAP Adapter<br />
ROOT\*TEREDO\0000 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; : Teredo Tunneling Pseudo-Interface<br />
ROOT\MS_AGILEVPNMINIPORT\0000 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; : WAN Miniport (IKEv2)<br />
ROOT\MS_L2TPMINIPORT\0000 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; : WAN Miniport (L2TP)<br />
ROOT\MS_NDISWANBH\0000 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;: WAN Miniport (Network Monitor)<br />
ROOT\MS_NDISWANIP\0000 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; : WAN Miniport (IP)<br />
ROOT\MS_NDISWANIPV6\0000 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; : WAN Miniport (IPv6)<br />
ROOT\MS_PPPOEMINIPORT\0000 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; : WAN Miniport (PPPOE)<br />
ROOT\MS_PPTPMINIPORT\0000 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; : WAN Miniport (PPTP)<br />
ROOT\MS_SSTPMINIPORT\0000 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; : WAN Miniport (SSTP)<br />
14 matching device(s) found.</address>
<p></p>
<p>Depending on what you are after you can limit the results e.g.:</p>
<pre>
devcon findall =net *dev_*</pre>
<p>In my case I want to remove the old vmxnet3 adapters, so look up the id for that adapter from the results and:</p>
<pre>
devcon -r remove &quot;@PCI\VEN_15AD&amp;DEV_07B0&amp;SUBSYS_07B015AD&amp;REV_01\FF290C008E0E28FE00&quot;</pre>
<p>This removesthe first of the vmxnet3 ghost network adapters. You need to take care as live adapters are listed as well.</p>
<p>&nbsp;</p>
