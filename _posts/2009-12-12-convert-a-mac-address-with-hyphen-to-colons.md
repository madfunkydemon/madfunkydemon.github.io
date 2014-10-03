---
layout: post
title: Convert a MAC Address with Hyphen to Colons
created: 1260608114
categories:
- linux/unix
- networking
---
If you have a MAC delimited with hyphens:

`xx-xx-xx-xx-xx-xx`

You can convert it to use colons using sed:

`echo xx-xx-xx-xx-xx-xx | sed 's/-/:/g'`

Which will output as:

`xx:xx:xx:xx:xx:xx`

Anything can be replaced:

`echo xx-xx-xx-xx-xx-xx | sed 's/-/%/g'`

Would output:

`xx%xx%xx%xx%xx%xx`
