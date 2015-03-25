---
layout: post
title: Hibernation File in Windows 2008
created: 1242283276
categories:
- windows
permalink: /2009/may/4/hibernation-file-windows-2008
---
<p>&nbsp;I'm not sure the reason the hibernation file (hiberfil.sys) being enabled in a default Windows 2008 Server install, but use this to remove it:</p>
<pre>
powercfg.exe /hibernate off

</pre>
<p>If for some reason you need to put it back, use:</p>
<pre>
powercfg.exe /hibernate on

</pre>
<p>You need to use this command, as this setting is unavailable in the GUI. This also can apply to Windows 7 especially after a P2V.</p>
