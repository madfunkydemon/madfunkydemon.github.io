---
layout: post
title: Batch Convert Images
created: 1394184422
categories:
- tools
- os x
---
The quickest way of converting image formats is to use ImageMagick. There are binary releases for most popular operating systems, however in my case I'm using it on OS X. So to install using brew from a terminal use:
{% highlight bash %}
brew install imagemagick
{% endhighlight %}
Once that is installed then just move to the folder you are interested in and use the following:
{% highlight bash %}
mogrify -format png *.jpg
{% endhighlight %}
Once that is completed the folder of jpegs should now have some png friends to play with.
