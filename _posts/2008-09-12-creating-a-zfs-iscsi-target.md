---
layout: post
title: Creating a ZFS iSCSI Target
created: 1221179706
categories:
- storage
- linux/unix
permalink: /2008/september/5/creating-zfs-iscsi-target
---
<p>Using a Nexenta VM it is possible to create a 500 TB thin provisioned iSCSI target in three lines:</p>
<pre>
zpool create zfspool01 raidz c2t0d0 c2t1d0 c2t2d0
zfs create -s -V 500TB zfspool01/share01
zfs set shareiscsi=on zfspool01/share01</pre>
<div>In this case the disks c2t0d0,&nbsp;c2t1d0 and&nbsp;c2t2d0 are all dynamic 10 GB virtual disks. &nbsp;This can easily be mounted with the Microsoft iSCSI Initiator for testing; it will be interesting to see how well this plays with ESX. .. .</div>
<p>&nbsp;</p>
