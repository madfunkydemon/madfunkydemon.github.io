---
layout: post
title: Installing OmniOS Under VMware Fusion/Workstation
created: 1340633556
categories:
- vmware
- linux/unix
permalink: /2012/june/1/installing-omnios-under-vmware-fusionworkstation
---
As of the 25/06/12 you need to use the <a href="http://omnios.omniti.com/wiki.php/Installation">bloody release</a> and will also need to have a floppy drive attached. You can add the floppy drive through the VMware gui or add the following to your vmx file:

    floppy0.fileType = "file"
    floppy0.fileName = "path_to_/floppy_image/Omni.flp"
    floppy0.clientDevice = "FALSE"
    floppy0.startConnected = "FALSE"

If you want to create a virtual floppy image then use the following on Os X:

`touch path_to_/floppy_image/Omni.flp`

I'm not sure you need to point to a real image, however if you are using the Fusion gui, it requires you to have one.
