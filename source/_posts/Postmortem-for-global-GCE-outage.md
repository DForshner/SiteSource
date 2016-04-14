---
title: Postmortem of a Global GCE Outage
date: 2016-04-14 10:23:48
tags:
- Distributed Systems
---
Google compute engine (GCE) was down globally for 18 minutes on the 11th.  The usual culprit of configuration error was present but there was also a series of bugs that combined together to propagate a bad configuration into production.

It's fascinating how small things combine to wreak havoc on large scale systems.  Google is constantly testing so I imagine theses bugs have been quietly waiting in edge case land until random chance brings them together.  With enough scale and complexity, the improbable becomes probable.

[Incident Report](https://status.cloud.google.com/incident/compute/16007)