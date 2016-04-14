---
title: First Look at React.js & Flux Pattern
date: 2015-03-13 00:00:00
tags:
- React
- ECMAScript
---
I took a crack at creating dashboards using Facebook's React & Flux libraries.

- It was easy to get something up working and then iterate on it.
- I found the functional concepts they are pushing a refreshing change from messing with jquery.  The code looks actually looks like code instead of a tangled rat's nest of callbacks and dom mutations.
- It's explicit about how state is stored and mutated.  People don't think enough about this stuff and haveing it front and center is nice.
- The flux pattern is interesting.  I like how it separates concerns but it seems like there is a lot of code duplication.
- The idea of updating state and re-rendering reminds me of a game loop.
- I'm not sure how the virtual DOM will perform for larger views but the "native calls are slow" argument makes sense.  I've had screens with bad jank when lots of Backbone sub-views are re-rendered at the same time.
- The jsx concept of combining template(html) and code is a bit strange but I think they are on to something.  With Backbone, you usually end up editing the template/model/view files for most changes so I agree that they aren't independent concerns.
- I also used Webstorm (support for jsx) for the first time and I'm not sure I can go back to using Visual Studio for JS.

[Prototype Code](https://github.com/DForshner/ReactFluxDashboardProto)