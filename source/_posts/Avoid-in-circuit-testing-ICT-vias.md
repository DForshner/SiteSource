---
title: Avoid in-circuit testing (ICT) vias
date: 2009-01-09 00:00:00
tags:
 - Electronics
---
I've been stuck on a problem with a tester for a digital signal processor board we build for a customer.

The failing test isn't even one of the complicated ones.  It's just looking for the proper voltage on a control line.  For the test, the DUT is re-booted to manufacturing mode, sent a control signal on the RS232 port which raises this control line to ~12 volts.  On boards that were failing the DAQ card was reading low voltages and sometimes no voltage.

The puzzling part is that when I re-test the same boards they will start passing.  On multiple occasions, people set aside stacks of failing boards and when I come over to look at them they pass.

By accident, I noticed that test set (customer supplied) is probing a via on the board instead of a proper test pad.  Normally that wouldn't be the end of the world but we started solder tenting vias near the power supply to prevent flux from coming up through them during wave soldering process and being left on the top of the board.  The tenting is preventing the probes from making contact during the initial test but scraping off enough material that when I come over to re-test them they start passing :-/.

I'm not sure exactly how much time was wasted between myself and the customer on this one but it was more than they saved by cutting corners by probing a via instead of designing a proper test pad.