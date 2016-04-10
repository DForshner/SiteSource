---
title: Avoid tight testing tolerances for small capacitance values
date: 2008-04-30 00:00:00
tags:
---
I am having continual in-circuit test (ICT) failures measuring the capacitance of a set of decoupling capacitors on a customer board.  Since decoupling capacitors are connected in parallel and each capacitor's individual tolerance are combining to have a range much larger than the tolerances of the individual parts.  

Beyond that measuring the capacitance of assembled components doesn't work for small values.  Everything they are connected to (including the PCB itself) affects the measured capacitance.

We agreed to widen the test limits and accept the risk of having damaged or missing decoupling capacitors.