---
layout: post
title: Clearing Down Large Log Files in Linux Quickly
created: 1331559892
categories:
- linux/unix
---
You should use something like <a href="http://linuxcommand.org/man_pages/logrotate8.html">logrotate</a> to manage you log files however sometimes you are not interested in the log content and just want to clear them. Especially if you have multi GB files due to excessive errors. In this situation use:
{% highlight bash %}
> /var/log/logfile-name
{% endhighlight %}
This will clear the file but not remove it. It is possible that a process has locked the file, in which case track it down with:
{% highlight bash %}
lsof /var/log/logfile-name
{% endhighlight %}
Finding large files in Linux can be tricky especially if there is no X. This can help:
{% highlight bash %}
find /var/log/ -size +1000000k -print0 | xargs -0 ls -lh
{% endhighlight %}
Just change the path to the directory you are interested in, in this case where the logs are usually located.
