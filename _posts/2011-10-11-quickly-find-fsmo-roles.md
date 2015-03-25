---
layout: post
title: 'Quickly find FSMO Roles '
created: 1318333234
categories:
- active directory
permalink: /2011/october/2/quickly-find-fsmo-roles
---
<p>&nbsp;Use netdom to find where the current FSMO roles are assigned in Active Directory:</p>
<pre>
netdom query fsmo</pre>
<p>This will return something like:</p>
<pre>
Schema master               <span class="Apple-tab-span" style="white-space:pre"> </span>DC01.local
Domain naming master        <span class="Apple-tab-span" style="white-space:pre"> </span>DC02.local
PDC                         <span class="Apple-tab-span" style="white-space:pre"> </span>DC01.local
RID pool manager            <span class="Apple-tab-span" style="white-space:pre"> </span>DC02.local
Infrastructure master       <span class="Apple-tab-span" style="white-space:pre"> </span>DC01.local
The command completed successfully.</pre>
<p>The 'netdom query' command can also return other useful information. Valid types include:</p>
<p>Server,&nbsp;Workstation,&nbsp;DC,&nbsp;OU and&nbsp;Trust</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
