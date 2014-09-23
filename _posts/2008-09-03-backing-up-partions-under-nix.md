---
layout: post
title: Backing up partions under *nix
created: 1220453885
categories:
- os x
- linux/unix
---
<p>dd is your man here. Replace /dev/disk for the disk you are interested in i.e. sda, sdb :</p>
<pre>
dd if=/dev/disk of=/path/backup<br />
</pre>
<p>This will create a full backup of your partition i.e. /dev/sda1:</p>
<pre>
dd if=/dev/disk_partition of=/dev/backup

</pre>
<p>You can compress the backup using gzip:</p>
<pre>
dd if=/dev/disk | gzip -c9 &gt; /path/backup.gz<br />
</pre>
<p>And to restore it:</p>
<pre>
gunzip -c /path/backup.gz | dd of=/dev/disk

</pre>
<p>&nbsp;</p>
