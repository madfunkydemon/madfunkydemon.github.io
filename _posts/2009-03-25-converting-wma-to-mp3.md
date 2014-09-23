---
layout: post
title: Converting Wma to Mp3
created: 1238020273
categories:
- tools
---
<p>This is easy with ffmpeg:</p>
<pre>
ffmpeg -i source_file.wma -ab 128k output_filen.mp3

</pre>
<p>Where the -ab is the bitrate.</p>
