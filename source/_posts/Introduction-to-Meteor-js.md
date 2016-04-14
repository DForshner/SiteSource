---
title: Introduction to Meteor.js
date: 2013-03-16 00:00:00
tags:
- Meetup
- ECMAScript
---
Notes from a presentation on Meteor.js.  I'm dubious about this one.  History hasn't been kind to technologies that promise to hide/erase the boundaries between client and server.

* A platform (client/server code are the same) as opposed to a framework (Angular/Backbone).
* Data is stored on both client and server.
* Publish/Subscribe model is used to move data between client and server.
* Reactive Variables - Data binding technique.
  * Reactive computations re-run when they change.
  * Will re-render templates tied to the changed variable.
  * Multiple widgets can react to variable change.
* Latency Compensation - Mock server response while waiting for real one.
  * If you know it will be OK 99% why not simulate that while you wait?
  * Doesn't re-render when the real response arrives (provided success).
* Node Fibers - Simulates multiple event loops on node's single event loop.
* Folder structure matters: (/client/) to client, (/server/) to server, (/other/) sent to both, (/test/) only tests, (/public/) static assets, and (/private/) server only static assets.
* Variable scope is per JS file if declared with var and entire application (both client and server) without var.  `What could go wrong??? :-/`
  * This can cause compatibility issues with other libraries.