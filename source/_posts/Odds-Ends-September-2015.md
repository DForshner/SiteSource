---
title: Odds & Ends - September 2015
date: 2015-09-01 00:00:00
tags:
  - Random
  - Odds & Ends
---
Thoughts, terms, and ideas I've come across over the last few months.

* Mobile experiences fill gaps while we wait.  Nobody wants to wait while they wait.
  * Preform actions optimistically
    * Show +1/Like/Comment before the request is even sent.  Show an error if it fails.
  * Adaptively pre-load content
    * Load data before it's needed.
    * Re-prioritize what to load based on user interest.
  * Move bits when no one is watching
    * Send contact list while signing in.
    * Start uploading files while they are filling out the details.
    * Send data as soon as part of it is ready to go and match it up on the server later.
* Code reviews are like having a shared brain.
* Shed load on social media sites by having shorter feeds.
* Achieve loose coupling using notifications, events, signals, etc.
* Project scaling
  * Code standards so everything looks the same
  * Unit tests and design documents so it's easy to switch implementations and modify.
  * All you need a work priority queue with ideas and bugs.
  * Be transparent.
  * Don't be date focused!  It's too idealistic.
  * Have short cycles, quick deliverables, and frequent estimates and re-estimates.
* Web crawling techniques
  * Start at seed page and recursively follow all/subset of links.
  * Identify a pattern in the URL for pages you want.  Ex: resource/id/ and check every valid id in range.
  * Read the sitemap and choose which links to follow.
* Append only event store
  * Observations about the world are recorded for perpetuity and the results of observations are calculated on demand.
  * Example: Changes -> Append to transaction log -> DB is a roll-up view of the changes captured in the transaction log.
  * Don't delete or update anything.  Just accrete new knowledge and distil new implications based upon your increasing knowledge.
  * It's like a warehouse.  Shipments come in, shipments go out, and at any point, we can check the current inventory levels.