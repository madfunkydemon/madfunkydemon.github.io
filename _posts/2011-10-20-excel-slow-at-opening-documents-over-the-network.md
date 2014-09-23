---
layout: post
title: Excel Slow at Opening Documents over the Network
created: 1319116578
categories:
- windows
---
<p>&nbsp;Recently I have seen Microsoft Office 2003 taking an age to open Excel documents over the network. You can use Wireshark to see what is happening at the network level:</p>
<p><a href="/sites/default/files/ws.gif"><img alt="s l o w " width="647" height="299" class="triggerclass" src="/sites/default/files/ws-opt.gif" /></a></p>
<p>You can see that it is opening the file a teeny tiny piece at a time. This can cause quite a delay as the spreadsheet gets larger. It turns out that it had been caused by an update to Excel called 'Microsoft Office File Validation Add-in':</p>
<p><a href="/sites/default/files/mofvai.gif"><img alt="humm" width="603" height="98" class="triggerclass" src="/sites/default/files/mofvai.gif" /></a></p>
<p>It can also appear as <a href="http://support.microsoft.com/default.aspx?scid=kb;en-US;2501584">KB 2501584</a>. You can remove this add-in and the problem goes away. You can find more information <a href="http://support.microsoft.com/kb/2570623">here</a>. There are also details on that link which are easier to roll out to a large number of users, either the MSI or the registry change. The long term fix is&nbsp;to upgrade to Office 2007, apparently. Er...</p>
