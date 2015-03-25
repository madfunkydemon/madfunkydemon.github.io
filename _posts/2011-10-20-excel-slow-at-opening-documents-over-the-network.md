---
layout: post
title: Excel Slow at Opening Documents over the Network
created: 1319116578
categories:
- windows
permalink: /2011/october/4/excel-slow-opening-documents-over-network
---
Recently I have seen Microsoft Office 2003 taking an age to open Excel documents over the network. You can use Wireshark to see what is happening at the network level:

<img alt="s l o w " src="/images/ws.gif" />

You can see that it is opening the file a teeny tiny piece at a time. This can cause quite a delay as the spreadsheet gets larger. It turns out that it had been caused by an update to Excel called 'Microsoft Office File Validation Add-in':

<img alt="humm" src="/images/mofvai.gif" />

It can also appear as <a href="http://support.microsoft.com/default.aspx?scid=kb;en-US;2501584">KB 2501584</a>. You can remove this add-in and the problem goes away. You can find more information <a href="http://support.microsoft.com/kb/2570623">here</a>. There are also details on that link which are easier to roll out to a large number of users, either the MSI or the registry change. The long term fix is&nbsp;to upgrade to Office 2007, apparently. Er...
