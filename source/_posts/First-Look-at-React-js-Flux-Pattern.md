---
title: First Look at React.js & Flux Pattern
date: 2015-03-13 00:00:00
tags:
  - React
---
I took a crack at creating some dashboards using Facebook's React & Flux libraries.  Overall I think they are on to something.

- It was surprisingly easy to get something up working and then iterate on it.
- I found the functional concepts they are pushing a refreshing change from messing with jquery.  The code looks actually looks like code instead of a tangled rat's nest of callbacks and dom mutations.
- It's very explicit about how state is stored and mutated.  People don't think enough about this stuff and haveing it front and center like this is nice.
- The flux pattern is interesting.  I like how it separates concerns but it seems like there is a lot of code duplication.
- The idea of updating state and re-rendering reminds me of a game loop.
- I'm not sure how the virtual DOM is going to perform but the "native calls are slow" argument makes sense.  I've run into some bad jank when lots of backbone sub-views get re-rendered at the same time.
- The jsx concept of combining template(html) and code is a bit strange at first but I think they are on to something.  Using backbone you pretty much end up editing the template/model/view files for most changes so I can see the argument that they aren't independent concerns.
- I also used Webstorm (support for jsx) for the first time and I never knew what I was missing.  Visual Studio doesn't even come close.

[Prototype Code](https://github.com/DForshner/ReactFluxDashboardProto)