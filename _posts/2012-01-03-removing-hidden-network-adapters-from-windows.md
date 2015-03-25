---
layout: post
title: 'Removing Hidden Network Adapters from Windows '
created: 1325612125
categories:
- windows
- vmware
permalink: /2012/january/2/removing-hidden-network-adapters-windows
---
Windows device manager does not always allow you to see old adapters once the hardware has been removed. You can enable it to do so but when you are dealing with large numbers of virtual machines you need another approach. Devcon can enable you to do this and can be found&nbsp;<a href="http://support.microsoft.com/kb/311272">here</a>&nbsp;if you are after the 32bit version. However there is no 64bit version (just the 32bit &amp; itanium version). To get the 64bit version you have to get hold of the Windows Device Driver kit <a href="http://www.microsoft.com/download/en/details.aspx?id=11800">here</a>. It is a 600Mb+ download which is large when you only want the one file. Once downloaded locate this file &quot;setuptools_x64fre.msi&quot;. You can find it in the WINDDK folder of the iso. Extract the msi out with the following:

`msiexec /a setuptools_x64fre.msi /qb TARGETDIR="C:\PATH_TO_FOLDER"`

You will find the 64bit version of devcon in the folder sturcture created e.g.:

WinDDK\7600.16385.win7_wdk.100208-1538\tools\devcon\amd64

Once you have the correct version of devcon you can use it to generate a full list of network adapters:

`devcon findall =net`

It will generate something like:

`PCI\VEN_15AD&DEV_07B0&SUBSYS_07B015AD&REV_01\FF290C008E0E28FE00: vmxnet3 Ethernet Adapter`  
`PCI\VEN_15AD&DEV_07B0&SUBSYS_07B015AD&REV_01\FF290C00F1B6A9FE00: vmxnet3 Ethernet Adapter #2`  
`PCI\VEN_8086&DEV_100F&SUBSYS_075015AD&REV_01\4&3AD87E0A&0&0888: Intel(R) PRO/1000 MT Network Connection`  
`ROOT\*ISATAP\0000                                         : Microsoft ISATAP Adapter`  
`ROOT\*TEREDO\0000                                       : Teredo Tunneling Pseudo-Interface`  
`ROOT\MS_AGILEVPNMINIPORT\0000                 : WAN Miniport (IKEv2)`  
`ROOT\MS_L2TPMINIPORT\0000                         : WAN Miniport (L2TP)`  
`ROOT\MS_NDISWANBH\0000                            : WAN Miniport (Network Monitor)`  
`ROOT\MS_NDISWANIP\0000                             : WAN Miniport (IP)`  
`ROOT\MS_NDISWANIPV6\0000                         : WAN Miniport (IPv6)`  
`ROOT\MS_PPPOEMINIPORT\0000                       : WAN Miniport (PPPOE)`  
`ROOT\MS_PPTPMINIPORT\0000                         : WAN Miniport (PPTP)`  
`ROOT\MS_SSTPMINIPORT\0000                         : WAN Miniport (SSTP)`  
`14 matching device(s) found.`  

Depending on what you are after you can limit the results e.g.:

`devcon findall =net *dev_*`

In my case I want to remove the old vmxnet3 adapters, so look up the id for that adapter from the results and:

`devcon -r remove "@PCI\VEN_15AD&DEV_07B0&SUBSYS_07B015AD&REV_01\FF290C008E0E28FE00"`

This removes the first of the vmxnet3 ghost network adapters. You need to take care as live adapters are listed as well.
