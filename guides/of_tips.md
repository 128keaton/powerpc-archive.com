---
title: OpenFirmware Tips n' Tricks
layout: guide
---
We figured these may be of some use too! OF is useful for a handful of things, take a look!
To access Open Firmware, immediately after pressing the power button, hold down Command+Option+O+F


## Eject A CD
This one's easy, and we found it useful with a stubborn iMac G4!

`eject cd`



## Boot Off A CD

Sometimes holding alt down to select a startup item fails, when in doubt, use this!

`boot cd:,\\:tbxi`

## Boot Mac Normally

Sometimes you may be defaulted to boot into OF, use this to boot up!

`mac-boot`

## Boot Off A USB Flash Drive

You'll need to make sure your flash drive is good to go, with the APM (Apple Partition Map) and is restored properly. To do this, read our guide (coming soon!).

## Find Boot Rom Version
This is useful if you need to quickly find the Boot Rom version if you are most likely doing a CPU swap in a G5.

When you access OF, look at the top and you'll see the version!

## Enable/Disable OF

This is a good know-how, as it allows you to set a password so that someone can't mess with your OF!

**Enable:**

   1. type `password`
      You'll be prompted to create a password.
      Type it in, and again to verify.
   2. type `setenv security-mode full`
   3. type `reset-all` to reboot the mac

**Disable:**

  1. type `setenv security-mode` none
   enter your old password
  2. type `reset-all` to reboot the mac
