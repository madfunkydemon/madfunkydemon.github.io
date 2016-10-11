---
layout: post
title: Find out the OS Architecture of Windows Quickly
created: 1343223873
categories:
- windows
permalink: /2012/july/3/find-out-os-architecture-windows-quickly/
---
Sometimes you need to find out if you are running a 32bit or a 63bit Windows operating system. You can do this quickly from the command line using WMI:

`wmic os get osarchitecture`

Another option is using the following environmental variable:

`echo %PROCESSOR_ARCHITECTURE%`

Short and sweet.
