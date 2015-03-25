---
layout: post
title: 'Compiling Growl 1.3 for Lion '
created: 1329402783
categories:
- os x
permalink: /2012/february/4/compiling-growl-13-lion
---
<p>&nbsp;To begin, make sure you have removed any previous versions of Growl. Instructions <a href="http://growl.info/documentation/growl-package-removal.php">here</a>.</p>
<p>You will need to install Mercurial, which can be found <a href="http://mercurial.selenic.com/">here</a>.</p>
<p>Once installed input the following from a terminal:</p>
<pre>
mkdir ~/Desktop/tmp
cd ~/Desktop/tmp
hg clone https://code.google.com/p/growl/
cd growl
</pre>
<p>At this point you need to open Keychain Access as we have to self sign a certificate for xcode to use in building Growl. In Keychain Access, go to the application menu and choose:</p>
<p>Keychain Access &gt; Certificate Assistant &gt; Create a certificate</p>
<p>In the box that appears, change the name to:</p>
<p>3rd Party Mac Developer Application: The Growl Project, LLC&nbsp;</p>
<p>Select the Certificate Type 'Code Signing' and click create accepting the trust warnings. Go back to the terminal window and use the following to compile Growl:</p>
<pre>
xcodebuild -project Growl.xcodeproj -target Growl.app -configuration Release
</pre>
<p>As the program compiles a warning about the self signed certificate (previously created) will appear. Click 'Always Allow'. Using a self signed certificate is not ideal, if you rather, Growl can be purchased through the Apple App Store. Once compiled correctly with no errors, copy the program into your Applications folder. The path of the compiled program can be seen above the ** BUILD SUCCEEDED ** line. In this case:</p>
<p>~/Desktop/tmp/growl/build/Release/Growl.app</p>
<p>Finally use to following to move the program to the Applications folder:</p>
<pre>
mv ~/Desktop/tmp/growl/build/Release/Growl.app /Applications/
</pre>
<p>Then:</p>
<pre>
open /Applications/Growl.app/
</pre>
<p>This will run Growl. Select what options you like. Lastly clean up the tmp build folder unless you want to keep it for future builds. If not (always be careful when using rm for the terminal especially with the -r switch) then:</p>
<pre>
rm -r ~/Desktop/tmp/
</pre>
