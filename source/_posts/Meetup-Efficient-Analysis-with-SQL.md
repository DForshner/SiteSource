---
title: Efficient Analysis with SQL
date: 2016-03-31 00:00:00
tags:
  - Meetup
  - Data Science
---
The main part of the meetup was a presentation on tally tables, cross apply and normalization in SQL.  
- Talley tables are used to replace while loops and fill in missing data.  Examples are shift tables, fiscal day tables, and holiday tables.
- When creating tally tables set fill-rate to 100% as you won't be adding/removing from them.
- Examples of using cross apply to pivot and unpivot (fold) data.
- Activity-based costing (task/material column/labor column/burden column) is denormalized whereas a debit-credit view is normalized (separate material row/labor row/ burden row).
- Interesting idea that normalization is about 'fidelity' and accurately modeling the real world.  I've always felt normalization was more a way of storing data in a general application-agnostic way so it didn't need to change as the application evolves.

This was followed by a short talk on scaling.
- Scaling is changing all the weights by the same factor so the ratio between weights remains unchanged.
- Scaling weights help pull them towards the unit circle.  If all the points are large values the get reduced and if they are all small they get increased.  Prevents numerical stability problems.
- If one axis has a small scale and the there large it can cause clustering algorithms to accidently combine clusters along the small scale axis.
- Other benefits of scaling are that gradient descent and learning rates will be faster.  It's easier to find the minimum error of a circular cone.
- When scaling the mean and variance can be approximated by using a random sample of the data points.
- Interesting idea on finding anomalous events by treating them like n-grams and finding improbable chains of events.  For example, if event C has a high probability given event A and B then it not occurring could be considered anomalous.

[Meetup Event](http://www.meetup.com/Waterloo-Data-Science/events/229944024/)