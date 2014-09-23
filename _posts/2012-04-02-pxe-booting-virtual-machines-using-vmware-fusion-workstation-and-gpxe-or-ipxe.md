---
layout: post
title: Pxe Booting Virtual Machines Using VMware Fusion/Workstation and gpxe or ipxe
created: 1333371442
categories:
- vmware
---
Vmware Fusion already includes a basic preboot execution environment (pxe) firmware. It is however possible to load other pxe firmwares into Fusion just like flashing ROMs into real network adapters. Two examples of pxe compliant boot loaders are gpxe and ipxe. Ipxe seems to be based on gpxe but they have generally similar features sets. These features include DNS, HTTP, iSCSI chainloading and more. To access these extra features we need to get hold of the ROM files which can be downloaded from here (right click and choose save as):

<a href="https://s3.amazonaws.com/twe-public-fs/gpxe-1.0.1%2B-8086100f.rom">gpxe e1000 | md5 = 281f4b835773983ce2ba78c3cfaf1d04</a>  
<a href="https://s3.amazonaws.com/twe-public-fs/8086100f.mrom">ipxe e1000 | md5 = f91d11735dab09bdac7d60ad9ad11504</a>  
<a href="https://s3.amazonaws.com/twe-public-fs/808610d3.mrom">ipxe e1000e | md5 = ec24813b8fbd0d3898b80d0e00e779b7</a>  
<a href="https://s3.amazonaws.com/twe-public-fs/15ad07b0.rom">ipxe vlance | md5 = 4b5070a8abd05388951724fc5f3c090c</a>  
<a href="https://s3.amazonaws.com/twe-public-fs/10222000.rom">ipxe vmxnet3 | md5 = 8e8e71f284f43a6641c0eb49ae30aa06</a>  

The gpxe was from <a href="http://etherboot.org/wiki/appnotes/gpxeonvmware">here</a>. The ipxe ROMs were compiled from <a href="http://ipxe.org/howto/vmware">here</a> on Ubuntu. I strongly suggest you go to the source links to get or create the files yourselves. I have included them here for my own purposes, but anyone is welcome to use them, <strong>at their own risk</strong>.
Once you have chosen the correct ROM file add it to your virtual machine folder. You need to edit the .vmx file of the virtual machine you are interested in. Choose from the paragraphs below, one which matches the ROM file you are using. <strong>Note</strong> the first line of each paragraph will already exist in the vmx file, so you will <strong>need</strong> to <strong>replace</strong> it. &nbsp;If you do not, you will get a message telling you 'Variable &quot;ethernet0.virtualDev&quot; is already defined' or perhaps 'Dictionary problem'. If you have multiple network adapters then the ethernet0 part may change. Just adjust it for the correct adapter i.e. ethernet1 or ethernet2 etc.

Add this paragraph for the e1000 Intel Driver and the gpxe bootloader:

    ethernet0.virtualDev = "e1000"
    bios.bootOrder = "ethernet0"
    e1000bios.filename = "gpxe-1.0.1+-8086100f.rom"
    ethernet0.opromsize = "71168"

Add this paragraph for the e1000 Intel Driver and the ipxe bootloader:

    ethernet0.virtualDev = "e1000"
    bios.bootOrder = "ethernet0"
    e1000bios.filename = "8086100f.mrom"
    ethernet0.opromsize = "69120"

Add this paragraph for the e1000e Intel Driver and the ipxe bootloader, note this is works only with virtual hardware 8:

    ethernet0.virtualDev = "e1000e"
    bios.bootOrder = "ethernet0"  
    e1000ebios.filename = "808610d3.mrom"
    ethernet0.opromsize = "70656"

Add this paragraph for an emulated AMD 79C970 PCnet32 Driver and the ipxe bootloader:

    ethernet0.virtualDev = "vlance"
    bios.bootOrder = "ethernet0"
    nbios.filename = "10222000.rom"
    ethernet0.opromsize = "62464"

Add this paragraph for a VMware paravirtualized NIC Driver and the ipxe bootloader:

    ethernet0.virtualDev = "vmxnet3"
    bios.bootOrder = "ethernet0"
    nx3bios.filename = "15ad07b0.rom"
    ethernet0.opromsize = "63488"

For anyone interested the ethernet0.opromsize parameter is actually the file size of the ROM file in bytes. If this value is wrong you can sometimes get the following error:

> BIOS gpxe-1.0.1+-8086100f.rom has unexpected file size 0x11600

For some reason this does not seem to affect the vmxnet3 or e1000e adapters but you should try to keep the values correct.
