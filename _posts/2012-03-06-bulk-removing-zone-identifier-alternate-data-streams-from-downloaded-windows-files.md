---
layout: post
title: Bulk Removing Zone.Identifier Alternate Data Streams From Downloaded Windows
  Files
created: 1331035065
categories:
- windows
- powershell
permalink: /2012/march/2/bulk-removing-zoneidentifier-alternate-data-streams-downloaded-windows-files/
---
Alternate Data Streams (ADS) are used by Windows to add an identifier describing the 'internet explorer zone' the file was downloaded from. If the zone was not trusted you may have to unblock the file. Certain file types are more at risky and therefore are automatically blocked (<a href="http://support.microsoft.com/kb/883260">see here</a>). To manually unblock the file go to explorer and right click the file, select properties and click unblock. This is somewhat cumbersome for large numbers of files. Using the Sysinternals <a href="http://technet.microsoft.com/en-us/sysinternals/bb897440">streams</a> tool you can manage this for far larger numbers of files. To view files to see if they have any ADS you can use:
```
dir /R c:\path_to_folder
```
This example is from a folder containing some powershell scripts downloaded from the excellent <a href="http://www.virtu-al.net/featured-scripts/vcheck/">vCheck</a> daily report:

```
06/03/2012  09:53             1,698 Changelog.txt  
                                 26 Changelog.txt:Zone.Identifier:$DATA  
06/03/2012  09:53                62 EndScript.ps1  
                                 26 EndScript.ps1:Zone.Identifier:$DATA  
06/03/2012  10:16             2,932 GlobalVariables.ps1  
06/03/2012  09:53            16,847 Header.jpg  
                                 26 Header.jpg:Zone.Identifier:$DATA  
06/03/2012  09:53    <DIR>          Headers  
06/03/2012  09:53    <DIR>          Plugins  
06/03/2012  09:53            12,092 vCheck.ps1  
06/03/2012  09:53            18,554 vCheckUtils.ps1  
                                 26 vCheckUtils.ps1:Zone.Identifier:$DATA
```

You can see from the listing each file has a separate zone identifier. This causes issues with Powershell 2.0 as it will warn you every time you run scripts which have been downloaded from an untrusted internet explorer zone e.g.:

Security Warning
Run only scripts that you trust. While scripts from the Internet can be useful, this script can potentially harm your computer. Do you want to run script_name.ps1?
[D] Do not run  [R] Run once  [S] Suspend  [?] Help (default is "D"):

This is a right royal pain, so to remove the ADS from the files with a zone identifier use:
```
streams -s -d c:\path_to_folder
```
Note, this will remove all alternate data streams so use this with care and only on the files you are interested in. The -s will recuse to subfolders. Running dir /R again on the same folder shows:
```
06/03/2012  09:53             1,698 Changelog.txt
06/03/2012  09:53                62 EndScript.ps1
06/03/2012  10:16             2,932 GlobalVariables.ps1
06/03/2012  09:53            16,847 Header.jpg
06/03/2012  09:53    <DIR>          Headers
06/03/2012  09:53    <DIR>          Plugins
06/03/2012  09:53            12,092 vCheck.ps1
06/03/2012  09:53            18,554 vCheckUtils.ps1
```
We have no more alternate data streams in that listing and when we run the powershell scripts we have no more nasty prompts. If you are interested in looking at the Zone.Identifier ADS use:
```
More < "C:\path_to_folder_and_file:Zone.Identifier"
```
A sample output from the internet zone is:
```
[ZoneTransfer]
ZoneId=3
```