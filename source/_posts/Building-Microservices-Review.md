---
title: Building Microservices Review
date: 2016-02-04 00:00:00
tags:
- Books
- Reviews
- Software Architectures
- Distributed Systems
---
I thought I was getting a book on architecture patterns but I got a book on applying Conway's Law to an organization while migrating to microservices.  This book appears to be aimed at people working with a traditional n-tier architecture with a shared database who are having problems scaling both their application and organization.  The author gives a high-level overview of microservices and the patterns used but this book is about organizational change.

After reading this, I don't think microservices are a good fit for the products I work on.  I've been associating microservices with things like automated deployment, centralized logging and performance monitoring, etc. but these are actually prerequisites to get into microservices.  I don't think the additional complexity that a microservices architecture brings are going to be worth it in my case.

[Good Reads Link](https://www.goodreads.com/book/show/22512931-building-microservices?utm_medium=api&utm_source=blog_book)

**Chapter Notes**
1. *Microservices*
 * If shared libraries are specific to a business domain or talk to particular services they can limit the ability to independently scale and deploy different parts of the system.
2. *The Evolutionary Architect*
  * Helping people grow so they can understand the overall technical vision and can be active participants in shaping and implementing it.
  * Great software comes from great people. If you worry only about the technology side of the equation, you're missing the picture.
3. *How to Model Services*
  * By aligning services to the seams between bounded contexts we ensure the services are built around relatively stable boundaries.
4. *Integration*
  * <u>Expand Only Types</u> - Types sent over the wire using binary serialization can become a mass of fields, some of which are no longer used but can't be removed safely.
  * Don't violate DRY within a microservice, but be relaxed about violating DRY across services.  The evils of too much coupling between services are far worse than the problems caused by code duplication.
  * <u>The Strangler Pattern</u> - Capture and intercept calls to the old system and either route these calls the existing or new code.  This allows you to replace functionality over time instead of doing a re-write.
  * Database integration makes it very hard to avoid breaking changes.  Prefer REST because changes to internal implementation detail are less likely to result in a change to the service interface.
  * <u>Tolerant Reader</u> - A reader able to ignore changes we don't care about.
  * <u>Semantic Versioning</u> - Outlines the expectations of clients can have of changes to the API and simplifies the process of communicating about whether changes should impact consumers.
5. *Splitting the Monolith*
  * Bounded contexts make great seams because they represent cohesive  units that are the loosely coupled boundaries in an organization.
6. *Deployment*
  * Focus on the ability to release each service independently of each other.
  * One source control repository, one CI build, and one host/container per service.
  * Culture of automation is key to managing everything.
7. *Testing*
  * <u>Service Test</u> - Test a slice of functionality across the whole service but isolate yourself from other services by using stubbed collaborators.
  * <u>Normalization of deviance</u> - Over time we become accustomed to things being wrong and we start to accept that as being normal and not a problem.  Ex: flakey tests, alarms that should be warnings, etc.
  * Anything that causes multiple service versions to be deployed in a specific order will eventually destroy the ability to deploy one service by itself.
  * Focus on a small number of core journeys to test for the whole system when developing end-to-end tests.
  * <u>Consumer-Driven Tests</u> - Capture the expectations of how a consumer will use a service in tests to make sure that when new versions of the service go to production it won't break consumers.
  * <u>Smoke tests</u> - Set of tests designed to run against newly deployed software to confirm the deployment worked.
  * <u>Blue/Green Deployment</u> - Have two copies of software deployed at the same time, but only one version if receiving real requests.  Allows you to switch back quickly if something goes wrong.
  * <u>Canary Releasing</u> - Verify a deployment by directing small amounts of production traffic against to see if it performs as expected.  Can send either divert a portion of real traffic or can shadow production traffic and direct it to the canary.
  * <u>Optimizing mean time between failures (MTBF) vs. mean time to repair (MTTR)</u> - Expending the same effort into getting better at remediation of a release can be more beneficial than adding more automated tests.
8. *Monitoring*
  * <u>Service metrics</u> - Generate service specific events for monitoring. Examples: web requests, number of times customers view past orders, transactions per second, etc.
  * <u>Synthetic transaction</u> - A fake event inserted into the system to show the it is still working.  Like a heartbeat.
  * Correlation ids allow us to reconstruct the flow of calls in order to reproduce and fix a problem.  Allows us to trace inter-service calls.
  * At a minimum track inbound response time, error rates, and the response times of downstream calls.
9. *Security*
   * <u>Confused deputy problem</u> - A malicious party tricks a deputy service into making calls to a downstream service on their behalf.
  * Many high profile security breaches involve data at rest being acquired by an attacker and that data being readable by that attacker.
  * Prevent services from allowing bulk retrieval of customer data.
  * VPNs allow us to segregate the network by team and/or risk level.
  * If you don't store it, no one can steal it.
10. *Conway's Law and System Design*
  * A team owning a service is responsible for making changes to that service.  The team should feel free to restructure the code however it wants, as long as the change doesn't break consuming services.
  * Feature teams don't produce functioning custodians and technology oriented teams waste time coordinating changes.  Align teams along business domains.
  * Try to align service ownership to colocated teams, which themselves are aligned around the bounded contexts of the organization.
11. *Microservices at Scale*
12. *Bringing It All Together*
  * Avoid orchestration systems (ex: enterprise service bus) which lead to centralization of business logic and dumb services.  Instead, prefer choreography over orchestration and dumb middleware, with smart endpoints.
  * The less you understand a domain, the harder it will be to find proper bounded contexts for your services.  Identify clean boundaries prior to splitting out services or you will have to make lots of expensive changes to service-to-service collaborators.
  * Consider starting green-field projects as a monolith and breaking them up once they are stable.