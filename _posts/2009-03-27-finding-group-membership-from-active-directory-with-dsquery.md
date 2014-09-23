---
layout: post
title: Finding Group Membership from Active Directory with Dsquery
created: 1238146709
categories:
- active directory
---
<p>&nbsp;Use the following:</p>
<pre>
dsquery user -samid &quot;username&quot; | dsget user -memberof -expand

</pre>
<p>The -expand option will include nestled groups.</p>
