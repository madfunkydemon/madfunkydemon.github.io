---
layout: post
title: Active Directory Forest Wide User Search
created: 1393593590
categories:
- active directory
permalink: /2014/february/5/active-directory-forest-wide-user-search/
---
I always have to look this up, I'm not sure what is going on with my memory:
{% highlight bash %}
dsquery user forestroot -name search
{% endhighlight %}
When you are working on large Active Directories this is somewhat handy. Just replace search with the name you are after, helpfully it supports wildcard.
