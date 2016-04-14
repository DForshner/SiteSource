---
title: Google I/O Extended 2013
date: 2013-05-18 00:00:00
tags:
- Conferences
- Interviewing
---
Notes from the Google I/O Extended conference at Google's Kitchener location.  I went to the workshops on interviewing at Google, Google Fiber and multi-touch interfaces.

* In Canada - Ad words, Chromebook (Pixel), consumer commerce products, mobile Gmail (IOS app).
* Pixel Concept - A better touch based web experience.
* Building platforms to support the evolution from Desktop -> Laptops -> Smart Phones.
  * Android - Bring open standards to the mobile industry.
  * Chrome - Build web as a platform and provide simple safe browsing.
* Activity recognition - Accelerometer + machine learning
* Google Cloud Messaging - Push data to mobile apps, syncronize notification dismissal across devices, auto retry, etc.
* **App Developer Tools**
   * App translation service to match make with a translation company.
   * Google play store uses per user bubbling recommendations based on +1's and installed/purchased apps.
   * App store has beta testing and staged rollout (alpha->beta->prod) and you can roll out new versions to a portion of users.
* **Music App** - Guild you through exploring your music.  Tries to understand what you want to hear.
  * Pick a category and get expert powered recommendations.
  * Play radio is a never ending queue of related tracks.
  * My library - Personal music + online music collection blended together.
  * Listen Now - Machine learning your musical preferences
* **Chrome platform**
  * Do for mobile web what was done for desktop
  * Chromebooks are built for the web
  * Consistent user experience across web independent of device or browser.
* Browser is a means not an end
* **Google Play for Eduction**
  * Walled garden within a walled garden
  * Teachers pick and push to all student tablets at once.
* **Data Centers**
  * Peer with ISP to lower transit costs
  * Colossus to replace GFS - 100x bigger
  * Flume - Pipelines of map reduce
  * Spanner - Big data with transactional capability
  * Compute Engine (ISS)
    * 1-minute billing granularity
    * Small instances with predictable performance instead of best effort.
  * App Engine (PSS)
    * Android studio new comes with a mobile starter kit that integrates with App Engine.  Write the front-end and it creates the back-end for you.
  * App Engine And Compute Engine can access same data store (GCloud).  Do CPU and I/O intensive tasks in Compute Engine to save money.
    * Ex: Doing semantic analysis on Compute instance using Hadoop and serving results on App Engine.
* **Interviewing at Google**
  * Can you write code?  Can you think at scale?
  * Verbalize your thought process.  Talk about what you are thinking.
  * Start with the simple case and then work towards a general answer.
  * If you don't know something don't fake it.  Just move on to the next part.
  * Be confident about your skills.
  * Don't interrupt the interviewer.  How will you work with a team?
  * Don't say bad things about anything!!!  They are looking for positive, open and capable.
  * Interviewers create a packet containing the questions asked, how you answered, a copy of the code you wrote, and their opinion on you being a good fit.
  * Resume - Show progression and what you accomplished.
  * They are looking for generalists.
  * Build expertise - Answer questions on SO, start blog, work on open source, etc.
  * Practice coding in front of a whiteboard.
  * Read the Algorithm Design Manual.
* **Google Fiber**
  * Organize world's information and make it accessible to all.
  * Already a technology company but want to gain experience as a services company.
  * <u>Fiberhoods</u> - Find interested communities and build there.
    * Schools, libraries, emergency centers, community centers, etc. are connected for free.
    * Lots of municipal politics.
  * Search built into your TV
  * In Kitchener they do UX, product testing, and development.
  * Analytics says people watch 5hrs of TV per day???
  * Financial model is TV + internet
* **Multi-touch Interfaces**
  * Most H/W will support up to 10 touches at the same time.
  * Recommend touch surface is 9x9mm (~44pts).
  * CSS pixels vary in physical size!
  * Don't rely on hover!  Use tap event to fake hover effect.
  * Browsers will fake mouse events on touch so you may get two events if not careful.
  * Touch events will target the node where the touch started even if the node is moved/removed from the DOM.
  * It's hard to hit small targets
  * Initial tap is delayed.  There is a 300ms delay to figure out if you are double tapping or not.
  * Touch events can happen faster than you can render (> 60 Hz).  Use requestAnimationFrame() to register work for next vFrame.