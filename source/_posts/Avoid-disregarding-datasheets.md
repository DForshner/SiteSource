---
title: Avoid disregarding data sheets
date: 2009-03-09 00:00:00
tags:
 - Electronics
---

There is a problem with high-efficiency LED drivers used for a lighting product.  One of the final steps in the build is to reduce the current to a set point, but this is causing the units to start strobing on/off.

After testing the possible combinations of power supplies and product boards I was able to make the high-efficiency power supplies consistently to fail which pointed towards the power supply being the culprit.

The high-efficiency power supply stabilized when the current was raised above the desired set point of 1.08A to 1.29A.  After the fixture & electronics warmed up, it would start to strobe on/off again unless the current was again raised to 1.40A.  The power waveform on the oscilloscope showed the unit powering up, holding steady for a moment, dropping down and then powering back up again in a cyclic pattern.  The puzzling part was that performing the same test with a 48V standard efficiency version of the driver didn't cause strobing.

It turns out that that the design was under driving the supplies by providing only 36V when the data sheet required between 40V-50V.  This was tripping the short circuit protection on the driver causing the unit to reboot.

While I suspect that component vendors add slack to their data sheet tolerances you are asking for trouble when you disregard them.