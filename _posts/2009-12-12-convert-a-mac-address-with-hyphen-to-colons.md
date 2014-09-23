---
layout: post
title: Convert a MAC Address with Hyphen to Colons
created: 1260608114
categories:
- linux/unix
- networking
---
<p>&nbsp;If you have a MAC delimited with hyphens:</p>
<pre>
xx-xx-xx-xx-xx-xx
</pre>
<p>You can convert it to use colons using sed:</p>
<pre>
echo xx-xx-xx-xx-xx-xx | sed 's/-/:/g'
</pre>
<p>Which will output as:</p>
<pre>
xx:xx:xx:xx:xx:xx
</pre>
<p>Anything can be replaced:</p>
<pre>
echo xx-xx-xx-xx-xx-xx | sed 's/-/%/g' 
</pre>
<p>Would output:</p>
<pre>
xx%xx%xx%xx%xx%xx
</pre>
