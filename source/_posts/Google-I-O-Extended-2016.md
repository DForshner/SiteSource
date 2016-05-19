---
title: Google I/O Extended 2016
date: 2016-05-19 00:00:00
tags:
  - Conferences
---
Yesterday I attended the Google I/O Extended conference at their KW office.  This year the focus seemed to be on using AI and machine learning to improve user experiences.

*Event Notes*
1. **Welcome Remarks**
  * The KW office has teams working on Chrome, Ads, Fiber and OnHub.
  * Gmail has 1 billion users worldwide.
2. **Startup Panel**
  * Hiring for startups is hard.  Need to be more aggressive to find the right people.
  * Startup leadership can go on too long.  If things haven't been working there is a point when leadership needs to change.
  * When you take every deal that gets offered, you end doing a lot of custom/one-off work that consumes time.  It's hard to turn down new opportunities even when they are more work then they are worth in the long run.
  * When you work for a small company it's easier to have a unified view of what your product is and what the company represents.  There are a lot of passionate people at Google, and their passion is equally as capable as yours.
  * When you have a large existing customer base you can't just roll changes that affect user experience.  You have to run experiments.
  * Don't cast a wide net when asking for help.  Target specific people who may be able to help you.
  * Don't buy into the message that says Canadian's don't make good entrepreneurs and don't aim high enough.  Be serious about being bold.
3. **Genomics & Cloud Platform**
  * Medical breakthroughs will come from the intersection of life science and data science.
  * Genomics API gives you higher level computational primitives and build applications that are infrastructure agnostic.
  * Instead of turtles, it's pipelines all the way down.
  * It's hard to link genome differences to phenotype differences.  Instead, people are linking genome differences to differences in how proteins are expressed and then linking the protein differences to phenotype.
4. **Keynote (Streamed)**
  * Search needs to be assistive it's not enough to show people links when they search anymore.  
  * <u>Google Assistant</u> - Give each user their own personal Google.
  * Use natural language processing to give a conversational understanding.  The goal is to understand the context and turn isolated questions into a conversation.
  * Every conversation is different = every context is different.
  * Computing is an *ambient experience* that spans car, phone, watch, home, tv, etc.
  * Google home is possible because of Google's leadership in far-field voice recognition.
  * Approach and existing area from a machine learning perspective.  Use AI and machine learning to make smarter more assistive applications.
  * Photo + machine learning = automatically applying labels to photos.
  * Mobile + machine learning = the "Allo" smart messaging app which suggests replies as you go based on your previous behavior.
  * <u>Quick Protocol</u> - Establish E2E encrypted connection in one round trip.
  * Proactively monitor bandwidth on wifi/mobile, so video chats are the right quality before you even make a call.
  * <u>Safty Net</u> - Use machine learning to monitor application behavior to spot malicious or misbehaving applications.
  * VR requires low latency between your head moving and the display updating to provide an immersive experience.
  * Android studio test recording allows you to turn your navigation through an application into an automated expresso test.  You can then run this on the cloud test platform to test on multiple devices at once.
  * <u>Cross network attribution</u> - Figuring out where users are coming from.
  * Cloud messaging service allows 1 million apps to send 170 million messages every day.
  * <u>Instant Apps</u> - Breaking applications into modules that can be download and run without installing the application.  Showed an example of using an NFC-enabled phone to tap a car parking meter to pay.
  * Can humans achieve more with machine learning and AI assisting them?
5. **Mobile Fireside**
  * Firebase is a set of complimentary SDKs to help your mobile application develop, grow, and earn.
  * Analytics only shows aggregates.  To protect privacy a minimum number of users is required to see certain metrics.  Example: 1000 to see gender distribution of users.
6. **Google Stack Driver**
  * DevOps information: logging, monitoring, latency reporting, etc.
  * Allows centralized DevOps for hybrid Google Cloud & AWS deployments.
  * Gather stats from applications, systems, servers to allow visualization, analysis, and notifications.
  * <u>Probing infrastructure</u> - Assess application health using ping or synthetic transactions.
7. **Chrome Input Performance**
  * Local team works on input, graphics, performance, physical web, media, UI, Android port, virtual reality.
  * Goal is to reduce the friction between a web app and native app.
  * How long is an event queued before browser handles it?
  * <u>Passive event listener</u> - Doesn't block while handling events.
8. **How the Web Platform Evolves**
  * Process to add new APIs: Identify problem -> build coalition -> design in public -> grow the circle -> implements and iterate -> ship -> standardize.
  * It's critical to get web developers (the users) involved in the early stages.  It should be a collaborative process between browser developers and users.
  * Advancing the web while not breaking stuff is hard.  You have to weigh each features improvement to the web against the risk of breaking existing behavior.
  * Use a feature's rank (how often it's used) to figure out when it's safe to deprecate it.
9. **Fiber Phone**
  * Call a place, not a person
  * <u>TR-69</u> - Device and retrieve it's own config from the system when plugged in.
  * We aren't going to blame the user for having a bad experience.  We are going to focus on fixing it.
10. **OnHub**
  * Everyone loves wifi but are frustrated and mystified when it doesn't work.
  * Power cycle is the only hammer they can use to fix the internet.
  * Make pretty to encourage better placement and performance.  Wifi works best with line-of-sight, so we don't want user's hiding it in the closet.
  * <u>UX centric design</u> - Put most useful things out in front.  The goal is to delight and inform the users and let them feel like they know what is going on.
  * Can run a speed test to validate you are getting the speed your ISP promises.
  * Hub + machine learning = make everything get better over time by training models (in the cloud) to help predict and optimize radio settings.  The product has a passive antenna that looks at what channels are in use at what time of day.
  * Provide the user with troubleshooting workflows and insights into problems.