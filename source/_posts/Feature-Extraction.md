---
title: Feature Extraction
date: 2015-12-10 18:00:00
tags:
  - Data Science
  - Meetup
---
Talk about how to turn raw data into features to use in learning and modelling and a short presentation on linear modelling.
- Adding new features that describe how the data changes over time (ex: position/velocity/acceleration/jerk).
- Figure out what variables are important to deduce dimensions.  Fewer dimensions reduce error.
- PCA - capture variance in a new vector that maximizes variance.
- Choose components based on proportion of variance (How much variance does this data account for?)
- PCA may make things worse!  There may be too many relationships between variables and we don't want to lose any.
- Over-fitting - Using too much local data that doesn't account for variance.  The model becomes fitted to the data you are seeing instead of the relationships between variables.
- The log function can be used to separate data.
- Linear modelling - Fit a line to minimize the amount of error.  Best if the error is normally distributed (most errors are zero).

[Meetup Event](http://www.meetup.com/Waterloo-Data-Science/events/227172091/)