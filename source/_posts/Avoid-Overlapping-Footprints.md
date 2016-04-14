---
title: Avoid Overlapping Footprints
date: 2009-03-03 00:00:00
tags:
- Electronics
---
I'm having problems while trying to do a power test for customer's board.  The voltage measurements I'm reading on the +5VDC test point is too high (5.43VDC) and the current draw during start-up was 49.2ma when it should have been around 30ma.

I removed the driver and wired it directly into the power supply by soldering some jumper wires to vias in an attempt to narrow the problem down to the component or the PCB itself.  After doing this is started working normally.

The customer put down two overlapping sets of component footprints so they could build the board with two different driver components and the driver's metal case is shorting on the unused pads :-/.

Today's corrective action = add tape.