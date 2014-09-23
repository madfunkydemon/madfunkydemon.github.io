---
layout: post
title: Playing WAV Files from Witness ContactStore
created: 1326819967
categories:
- phones
---
<p>These days most computers struggle to play WAV files recorded by the Witness Contactsotore. Probably the easiest way to make these files play is to use ffmpeg to convert them as follows:</p>
<pre>
ffmpeg -acodec g726 -i original_file.wav -f wav out_file.wav
</pre>
<p>The converted WAV should play fine now on most operating systems.</p>
