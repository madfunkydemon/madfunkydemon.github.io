---
layout: post
title: Ubuntu Wireless with BCM4322
created: 1269088328
categories:
- networking
- linux/unix
permalink: /2010/march/6/ubuntu-wireless-bcm4322
---
<p>I have been having issues with the BCM4322 wireless card on my macbook pro under ubuntu. As it turns out after some digging&nbsp; the BCM4322 driver only supports the 'Rest of World' locale which does not include wireless channels 12 &amp; 13. You can test this by trying:</p>
<pre>
sudo iwlist eth2 channel
</pre>
<p>Which on the macbook pro returns:</p>
<h6><em>eth2&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 20 channels in total; available frequencies :<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 01 : 2.412 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 02 : 2.417 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 03 : 2.422 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 04 : 2.427 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 05 : 2.432 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 06 : 2.437 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 07 : 2.442 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 08 : 2.447 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 09 : 2.452 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 10 : 2.457 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 11 : 2.462 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 36 : 5.18 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 40 : 5.2 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 44 : 5.22 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 48 : 5.24 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 149 : 5.745 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 153 : 5.765 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 157 : 5.785 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 161 : 5.805 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Channel 165 : 5.825 GHz<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Current Channel:1<br />
<br type="_moz" />
</em></h6>
<p>As you can see, no channels 12 &amp; 13. Since my router had been set to 13 (it was less popular in my area) this resulted in no wireless for ubuntu. After a quick change to the channel setting on the router, ubuntu can see my wireless network. To find a channel which is not too crowded try using nm-tool or perhaps:</p>
<pre>
sudo iwlist eth2 scan | grep Channel
</pre>
<p>&nbsp;</p>
