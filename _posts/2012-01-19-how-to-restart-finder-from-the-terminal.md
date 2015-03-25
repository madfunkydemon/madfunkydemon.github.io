---
layout: post
title: How to Restart Finder from the Terminal
created: 1326993767
categories:
- os x
permalink: /2012/january/4/how-restart-finder-terminal
---
Some times it is necessary to force finder to restart. You can do this from the GUI using the 'Force Quit' menu item, however sometimes it can be quicker to use the Mac terminal:

`sudo killall Finder`

You may need to manually start finder if it doesn't automatically:

`open /System/Library/CoreServices/Finder.app`

Sometimes you can't beat a good old fashioned reboot:

`reboot`

This is rather a harsh way of rebooting as it just sends out a sigterm and subsequently a sigkill. You could also use:

`shutdown -r`
