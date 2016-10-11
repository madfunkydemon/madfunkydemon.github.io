---
layout: post
title: Getting the Size of a File in Bytes in Unix/Linux
created: 1339383713
categories:
- os x
- linux/unix
permalink: /2012/june/1/getting-size-file-bytes-unixlinux/
---
Use the following from a terminal to get the file size in bytes:

`wc -c ~/screenlog.0`

Which in this case will output:
{% highlight bash %}
76974 /Users/edward/screenlog.0
{% endhighlight %}
Showing my screenlog.0 is 76974 bytes.
