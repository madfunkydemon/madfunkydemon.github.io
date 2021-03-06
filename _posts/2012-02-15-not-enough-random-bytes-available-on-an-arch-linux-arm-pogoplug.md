---
layout: post
title: Not Enough Random Bytes Available on an Arch Linux ARM Pogoplug
created: 1329308416
categories:
- linux/unix
permalink: /2012/february/3/not-enough-random-bytes-available-arch-linux-arm-pogoplug/
---
If you get the following error when generating a pacman keychain master key:

pacman-key --init
gpg: Generating pacman keychain master key...
Not enough random bytes available.  Please do some other work to give
the OS a chance to collect more entropy! (Need 288 more bytes)

It can be quite tricky to introduce entropy into this low powered headless system. I tried various methods all of which failed. You can monitor the available system entropy here:

`watch cat /proc/sys/kernel/random/entropy_avail`

In the end I used this program to externally introduce entropy, <a href="http://vladz.devzero.fr/soft/GUChaos.c.html">here.</a>&nbsp;The file is well commented and there is a key value that needs changing.&nbsp;Save the code into a file called GUChaos.c then compile it using gcc:

`cc GUChaos.c -o GUChaos`

Execute the resulting file as root:

`./GUChaos`

You will need to make sure you have gcc installed, if you haven't you can install it with the following:

`pacman -S gcc`
