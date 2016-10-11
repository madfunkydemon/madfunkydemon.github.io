---
layout: post
title: Finding Group Membership from Active Directory with Dsquery
created: 1238146709
categories:
- active directory
permalink: /2009/march/5/finding-group-membership-active-directory-dsquery/
---
Use the following:

`dsquery user -samid "username" | dsget user -memberof -expand`

The -expand option will include nestled groups.
