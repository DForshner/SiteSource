---
title: Postmortem for a global GCE outage
date: 2016-04-14 10:23:48
tags:
- Distributed Systems
---
Google computer engine was down globally for 18 minutes.  The usual culprit of configuration error was present but there was also a series of bugs that combined together to propagate a bad configuration into production.

It's fascinating how small things combine to wreak havoc on large scale systems.  Google is constantly testing so I imagine theses bugs have been quietly waiting in edge case land for a while until random chance brings them together.  With enough scale and complexity, the improbable becomes probable.

[Incident Report](https://status.cloud.google.com/incident/compute/16007)