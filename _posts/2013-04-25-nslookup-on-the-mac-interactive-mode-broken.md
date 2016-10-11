---
layout: post
title: Nslookup on The Mac, Interactive Mode Broken
created: 1366920674
categories:
- os x
permalink: /2013/april/4/nslookup-mac-interactive-mode-broken/
---
Nslookup under osx is tricky to use interactively as it doesn't support readline. When you try to use the command history you get the following:
{% highlight bash %}
> ^[[A
{% endhighlight %}
Argh! This means more typing. As far as I can remember it has always returned ^[[A or ^[[B depending on the arrow key used. After a bit of <a href="http://apple.stackexchange.com/questions/69612/how-can-i-make-the-up-arrow-work-in-terminals-nslookup-command">research</a> it seems you can fix it with rlwrap which you can install via mac ports. To use it just wrapper nslookup in rlwrap:

`rlwrap nslookup`

This should enable the history in nslookup and reduce the amount of typing, when you need to go back. For ease set up an alias in your .bash_profile:
{% highlight bash %}
alias ns="rlwrap nslookup"
{% endhighlight %}
Now typing ns gives you an interactive ready nslookup. Clearly, you could use dig or host but some habits are hard to shake.
