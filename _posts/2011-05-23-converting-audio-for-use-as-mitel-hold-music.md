---
layout: post
title: Converting Audio for Use as Mitel Hold Music
created: 1306142407
categories:
- linux/unix
- phones
permalink: /2011/may/1/converting-audio-use-mitel-hold-music/
---
<p>The music file has to be A-law or U-law or G.711 at 8 khz, 8 Bits, Mono. To do this you can either use sox or ffmpeg. To use sox:</p>
<pre>
sox -V input_file.wav -A -c 1 -r 8k -1 output.wav<br /></pre>
<p><u>Update:</u> Seems some of these options are depreciated, if you run sox with the previous options you get:</p>
<pre>
sox WARN sox: Option `-A' is deprecated, use `-e a-law' instead.
sox WARN sox: Option `-1' is deprecated, use `-b 8' instead.
</pre>
<p>So as it says use:</p>
<pre>
sox -V input.mp3 -e a-law -c 1 -r 8k -b 8 output.wav<br /></pre>
<p>You can test this by using:</p>
<pre>
play output.wav</pre>
<p>Or by using ffmpeg:</p>
<pre>
ffmpeg -i input_file.wav -acodec pcm_alaw -ar 8000 -ab 8k -sample_fmt s8 -ac 1 output.wav</pre>
<p>This will show you infomation on the resulting file:</p>
<pre>
ffprobe -show_streams output.wav</pre>
