---
title: Installing Leopard On Machines Under 867MHz
layout: guide
---

Without Using LeopardAssist
Have you ever tried using LeopardAssist but for whatever reason it won't work? Or you don't have an OS on your computer?
Today, I'll show you how to install Leopard 10.5 on a machine under 867MHz using Open Firmware.

What you will need:
Leopard Installation Media
A G4+ machine with a supported graphics card and 512MB+ RAM

Note: Before attempting to install Leopard, make sure your firmware is up-to-date. On most PowerPC machines,
firmware updates must be native in Mac OS 9. Check here to see if one is available.

Also, if you are using an external Hard Drive or thumb drive, make sure to select that as your boot drive before starting Open Firmware.
Remember, playing around with Open Firmware is not recommended.

Todays Test Machine:
Titanium PowerBook G4
Late 2001
550MHz PowerPC G4
768MB of RAM
60GB Hard Drive
ATi Radeon Mobility 16MB
 Picture
 Picture
Insert or Plug in your installation media and power up the computer holding down Command-Option-O-F
Release the keys when prompted to.
Type in dev /cpus/PowerPC,G4@0 and press return
Type in d# 867000000 encode-int " clock-frequency" property and press return (for dual processor machines, repeat steps 3 and 4 replacing the @0 in step 3 with @1
If booting from a CD, type boot cd:,\\:tbxi. If you selected your boot media from the Startup Disk menu, simply type mac-boot to go to the installer.
