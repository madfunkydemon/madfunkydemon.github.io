---
layout: post
title: Searching Active Directory
created: 1220397572
categories:
- active directory
permalink: /2008/september/3/searching-active-directory/
---
<p>This is a quick way to search Active Directory from the cmd line:</p><pre>
dsquery user -name * -limit 0</pre><p>Just pop the name or name + wildcard where the * is. &nbsp;If you want to reduce the output to the relative distinguished name then just add:</p><pre>
dsquery user -name * -limit 0 -o rdn</pre>
