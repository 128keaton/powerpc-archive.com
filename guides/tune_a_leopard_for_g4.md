---
title: Make Leopard Faster On A G4
layout: guide
---
I purchased a 12 inch 867MHz PowerBook G4 to give to a friend moving to Florida.
After installing Leopard to it, performance was really bad. So I made this guide to share my tips and tricks to make Leopard a bit more usable! This guide was intended for a PowerBook G4 but was modified to refer to ALL G4 systems capable of running Leopard.

Leopard, although made to run on anything faster than a 867MHz, can be extremely slow with Leopard. Be sure to attempt maxing out the ram, and if possible installing an SSD will help greatly. These are just little tips to make a G4 a tad bit faster! Enjoy!

## So, Where Do We Start?

Well, first off make sure your G4 mac has a 867MHz or faster processor (there are ways to make it install on
almost any G4, stay tuned for that guide), and appropriate RAM. Then install Leopard to it. Upon running leopard for the first time it's extremely slow!

### 1. Install Software Updates

![](http://ppcarchive.dyniform.net/uploads/6/8/4/0/6840558/5840341.png?162)

Make sure you are up to date with the core of OS X. This would include all Java Updates, OS X Updates (10.5.x, make sure you run 10.5.8), QuickTime, Safari, iTunes, and so on. Keep installing these until everything is up to date.

This way if you have devices such as a magic mouse or wireless keyboard, it will download the latest software to enable scrolling, media keys, etc. This will also provide the latest security updates and patches that allow you to run iLife 09 or iWork 09.

### 2. Disable Spotlight, Dashboard

![](http://ppcarchive.dyniform.net/uploads/6/8/4/0/6840558/3198154.png?163)

So you have all the updates installed? Great! Next up is to disable some features inside Leopard that take up the most resources on your machine. Spotlight and Dashboard are the biggest contenders in this arena. On a G5 these are fine but for any G4 it's recommended to disable them!

Then also you can remove the Dashboard icon so it will no longer appear in the dock.
Disable Spotlight
This is not recommended if you have Time Machine enabled.Go to Applications, Utilities, then Terminal.  Paste this command:

{% highlight bash %}
sudo launchctl unload -w
/System/Library/LaunchDaemons/com.apple.metadata.mds.plist
sudo launchctl unload -w /System/Library/LaunchAgents/com.apple.Spotlight.plist
{% endhighlight %}

to disable Spotlight, to re-enable run this:
{% highlight bash %}
sudo launchctl load -w /System/Library/LaunchDaemons/com.apple.metadata.mds.plist
sudo launchctl load -w /System/Library/LaunchAgents/com.apple.Spotlight.plist
{% endhighlight %}
Restart your Mac to see changes.
Disable Dashboard
Go to Applications, Utilities, then Terminal.  Paste this command:
{% highlight bash %}
defaults write com.apple.dashboard mcx-disabled -boolean YES; killall Dock
{% endhighlight %}
Which will close dashboard and restart the Dock.


To re-enable spotlight, paste this into Terminal:
defaults write com.apple.dashboard mcx-disabled -boolean NO; killall Dock
Which will close dashboard and restart the Dock.

### 3. Animations And Effects In The GUI
![](http://ppcarchive.dyniform.net/uploads/6/8/4/0/6840558/1627635.png?1380266085)

Behind Spotlight and Dashboard, animations also can take a toll on performance. For example, minimizing a window uses quite a bit of your graphics resources. Disabling the "gloss" will make the window hide quicker and keep the GPU from stressing itself out and burning up. This "eye candy" (similar to Windows Vista's Aero) needs extreme amounts of horsepower to run correctly.

**Disable Dock Animations**

![](http://ppcarchive.dyniform.net/uploads/6/8/4/0/6840558/5763649_orig.png)

Windows will minimize faster and not take forever taking time to resize the window.
System Preferences -> Dock
Minimize Using: Scale Effect
Uncheck "Animate Opening Applications"


**Make Dock 2D**

 ![](http://ppcarchive.dyniform.net/uploads/6/8/4/0/6840558/9417746_orig.jpg)

Making the Dock 2D will greatly increase graphics performance and make the dock feel like Tiger.
Go to Terminal and Paste:
defaults write com.apple.dock no-glass -boolean YES; killall Dock
The dock will immediately change. To revert:
defaults write com.apple.dock no-glass -boolean NO; killall Dock

**Disable Transparent Menu Bar**
![](http://ppcarchive.dyniform.net/uploads/6/8/4/0/6840558/5168113_orig.png)

If your mac has Quartz Extreme, the
` File Edit View ` menu will be clear. Run this to make it matte-like.
Go to Terminal and Paste:
{% highlight bash %}
sudo defaults write /System/Library/LaunchDaemons/com.apple.WindowServer
'EnvironmentVariables' -dict 'CI_NO_BACKGROUND_IMAGE' 1
{% endhighlight %}
Then restart your computer.


### 4. Power & Performance

![](http://ppcarchive.dyniform.net/uploads/6/8/4/0/6840558/4963395.png)

You can specify if you want to be in a power saver mode or maximum performance. For Desktop G4s the Performance is recommended while a iBook/PowerBook G4 would be better with Power Saver (if you use the machine without a AC adapter). Enabling performance will make Leopard use more of the resources instead of locking itself out from them.

Go to System Preferences, Energy Saver. Then select your power options.

### 5. Install Modern Software

![](http://ppcarchive.dyniform.net/uploads/6/8/4/0/6840558/209119752.jpg)

Now that your Mac runs Leopard pretty well, it's time to go get some software to make using it a bit better. Such as TenFourFoxG4 or WebKit for modern web browsing or VLC to play 720p content. Check out our Essentials list and download what you like!
Extras
There are some people that want even more for their Mac speed or hard drive space. Check below for extras that will make your Mac even better!

### 6. Remove Extra Languages & Architecture Code (optional)
![](http://ppcarchive.dyniform.net/uploads/6/8/4/0/6840558/2916619.png)

This is a good idea if you need more space on your hard drive (if you have a small HDD in your Power/iBook G4) and need to save some space. Monolingual (you need a PPC version, check out Utilities) which will strip down extra languages (of your choice) from your applications. This will remove the Intel code and strip applications strictly for PowerPC.
