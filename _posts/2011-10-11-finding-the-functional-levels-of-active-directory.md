---
layout: post
title: Finding the Functional Levels of Active Directory
created: 1318349919
categories:
- active directory
permalink: /2011/october/2/finding-functional-levels-active-directory/
---
<p>There a quite a few ways of finding the Fuctional levels of Active Directory. Dsquery is a good option as it usually is distributed with windows. &nbsp;This will give you the Domain Functional Level:</p>
<pre>
dsquery * &quot;DC=DOMAIN, DC=LOCAL&quot; -scope base -attr msDS-Behavior-Version ntMixedDomain
</pre>
<p>Replace DOMAIN and LOCAL with your directory details. You can check the result with the following table:</p>
<p>0, 0<span class="Apple-tab-span" style="white-space:pre">		</span>Windows 2000 Native domain Level<br />
0, 1<span class="Apple-tab-span" style="white-space:pre">		</span>Windows 2000 Mixed domain Level<br />
2, 0<span class="Apple-tab-span" style="white-space:pre">		</span>Windows 2003 Domain Level<br />
3, 0<span class="Apple-tab-span" style="white-space:pre">		</span>Windows 2008 Domain Level<br />
4, 0<span class="Apple-tab-span" style="white-space:pre">		</span>Windows 2008 R2 Domain Level&nbsp;</p>
<p>To find the Active Directory Schema Version:</p>
<pre>
dsquery * &quot;CN=Schema,CN=Configuration,DC=DOMAIN, DC=LOCAL&quot; -scope base -attr objectversion
</pre>
<p>Remember to replace DOMAIN and LOCAL with your AD details. Lookup the results with:</p>
<p>13<span class="Apple-tab-span" style="white-space:pre">			</span>Windows 2000<br />
30<span class="Apple-tab-span" style="white-space:pre">			</span>Windows 2003<br />
31<span class="Apple-tab-span" style="white-space:pre">			</span>Windows 2003 R2<br />
44<span class="Apple-tab-span" style="white-space:pre">			</span>Windows 2008<br />
47<span class="Apple-tab-span" style="white-space:pre">			</span>Windows 2008 R2</p>
<p>Probably the easiest option tool to use to find this information is <a href="http://www.joeware.net/freetools/tools/adfind/index.htm">Adfind</a>:</p>
<pre>
adfind -sc modes
</pre>
<p>This will will look something like this:</p>
<p>AdFind VJoe Richards (joe@joeware.net) February 2011<br />
Using server: DOMAIN.LOCAL:389<br />
Directory: Windows Server 2003</p>
<p>dn:<br />
&gt;domainControllerFunctionality: 2 [Windows Server 2003 Mode]<br />
&gt;domainFunctionality: 2 [Windows Server 2003 Domain Mode]<br />
&gt;forestFunctionality: 0 [Windows 2000 Forest Mode]</p>
<p>1 Objects returned</p>
<p>You can also use Adfind to show the schema version:</p>
<pre>
adfind -sc schver
</pre>
<p>&nbsp;</p>
