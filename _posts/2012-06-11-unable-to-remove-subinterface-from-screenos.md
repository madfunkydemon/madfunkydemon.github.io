---
layout: post
title: Unable to Remove Subinterface from ScreenOS
created: 1339382687
categories:
- networking
permalink: /2012/june/1/unable-remove-subinterface-screenos
---
When removing subinterfaces from a SSG550 we were getting the following error:

> Unable to remove interface, interface ethernet0/0.1:1 is in use the interface cannot be set

Where ethernet0/01:1 is the interface you are trying to remove. After some experimentation we found that you have to make sure you have removed the check box under the NTP server service option. If the subinterface is still running NTP you will be unable to remove the subinterface.
