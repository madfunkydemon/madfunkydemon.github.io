---
layout: post
title: Converting Wma to Mp3
created: 1238020273
categories:
- tools
permalink: /2009/march/3/converting-wma-mp3
---
<p>This is easy with ffmpeg:</p>
<pre>
ffmpeg -i source_file.wma -ab 128k output_filen.mp3

</pre>
<p>Where the -ab is the bitrate.</p>
