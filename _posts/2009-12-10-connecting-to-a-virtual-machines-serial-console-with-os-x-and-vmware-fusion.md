---
layout: post
title: Connecting to a Virtual Machine's Serial Console with OS X and VMware Fusion
created: 1260434834
categories:
- vmware
- os x
---
<p>&nbsp;Fusion does have many of the features of VMware workstation but they are not all available in the GUI. An example of this is when you need a VM which only has a serial console. Make sure you have added the virtual serial hardware from the 'other' section in the settings. Next you need to edit the vmx file to add the correct settings:</p>
<pre>
serial0.fileType = &quot;pipe&quot;<br />serial0.fileName = &quot;/tmp/serial1&quot;</pre>
<p>Depending on how many serial devices you have the serial0 may change to serial1 etc. The path for the named pipe can be what ever you want. Next you will need to make sure you have installed socat from Mac Ports and run this from your mac terminal:</p>
<pre>
socat -d -d /tmp/serial1 PTY:
</pre>
<p>Part of the output from this will look like:</p>
<p>2009/12/10 08:09:38 socat[8173] N PTY is /dev/ttys001</p>
<p>From this we can see that it has taken the named pipe and set it as /dev/ttys001. So now all we need to do is connect to it:</p>
<pre>
screen /dev/ttys001 9600</pre>
<p>The other option is to use a second VM set up as a client to the serial connection we edited before. Just add these settings to the second VM's vmx file:</p>
<pre>
serial0.fileType = &quot;pipe&quot;<br />serial0.pipe.endPoint = &quot;client&quot;<br />serial0.fileName = &quot;/tmp/serial1&quot;</pre>
<p>Using this method you need two machines running but in some situations it can be useful, like when you have a specific software requirement.</p>
<p>&nbsp;</p>
