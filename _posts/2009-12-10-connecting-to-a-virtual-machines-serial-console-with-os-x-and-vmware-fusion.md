---
layout: post
title: Connecting to a Virtual Machine's Serial Console with OS X and VMware Fusion
created: 1260434834
categories:
- vmware
- os x
permalink: /2009/december/4/connecting-virtual-machines-serial-console-os-x-and-vmware-fusion/
---
Fusion does have many of the features of VMware workstation but they are not all available in the GUI. An example of this is when you need a VM which only has a serial console. Make sure you have added the virtual serial hardware from the 'other' section in the settings. Next you need to edit the vmx file to add the correct settings:

`serial0.fileType = "pipe"`  
`serial0.fileName = "/tmp/serial1"`  

Depending on how many serial devices you have the serial0 may change to serial1 etc. The path for the named pipe can be what ever you want. Next you will need to make sure you have installed socat from Mac Ports and run this from your mac terminal:

`socat -d -d /tmp/serial1 PTY:`

Part of the output from this will look like:

`2009/12/10 08:09:38 socat[8173] N PTY is /dev/ttys001`

From this we can see that it has taken the named pipe and set it as /dev/ttys001. So now all we need to do is connect to it:

`screen /dev/ttys001 9600`

The other option is to use a second VM set up as a client to the serial connection we edited before. Just add these settings to the second VM's vmx file:

`serial0.fileType = "pipe"`  
`serial0.pipe.endPoint = "client"`  
`serial0.fileName = "/tmp/serial1"`  

Using this method you need two machines running but in some situations it can be useful, like when you have a specific software requirement.
