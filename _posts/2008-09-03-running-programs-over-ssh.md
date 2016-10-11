---
layout: post
title: Running Programs over SSH
created: 1220454698
categories:
- os x
- linux/unix
permalink: /2008/september/3/running-programs-over-ssh/
---
<p>This is by far the best thing to use when you are running programs that take a while to complete. The danger is that you lose your SSH connection and your program along with it. Use the following to start a screen session:</p>
<pre>
screen

</pre>
<p>This generates a screen session that can be detached from by pressing:</p>
<pre>
ctrl + a d

</pre>
<p>At this point you can safely close down the SSH session. &nbsp;To reconnect to the screen session use:</p>
<pre>
screen -r

</pre>
<p>Fantastic, no more interruptions from unplanned connection problems which can come in handy when you emerging X11 under Gentoo. . .</p>
