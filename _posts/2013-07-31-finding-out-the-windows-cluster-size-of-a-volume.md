---
layout: post
title: Finding out the Windows Cluster Size of a Volume
created: 1375266979
categories:
- storage
- windows
permalink: /2013/july/3/finding-out-windows-cluster-size-volume/
---
From an administrative command prompt type:

`fsutil fsinfo ntfsinfo d:`

The output will include:
{% highlight bash %}
Bytes Per Cluster :               4096
{% endhighlight %}
In this case Bytes Per Cluster is 4096.
