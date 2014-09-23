---
layout: post
title: Exif from a Terminal
created: 1277469704
categories:
- linux/unix
- os x
- photography
---
<p>&nbsp;It is sometimes useful to see exif information in image files. If you want to examine exif information for an image then <a href="http://www.sno.phy.queensu.ca/~phil/exiftool/">exiftool</a> by Phil Harvey is excellent at doing this from the commandline. If you want to quickly examine exif from the internet then I have put together a small shell script which you can pass a url i.e.</p>
<pre>
get_exif_info http://path/to/image.jpg
</pre>
<p>That will pass the file direct to exiftool without saving it. You will need exiftool and wget installed and working to use getexifinfo. Wget and exiftool are available through macports. To use the shell script you will have to do the normal things like make it executable and in your class path variable.</p>
<p><a href="/sites/default/files/get_exif_info.">get_exif_info</a></p>
<p>As wget and exiftool are available on Windows I'm sure this can be modified to work with Windows.</p>
