---
title: Left Pad Liberation
date: 2016-03-23 00:00:00
tags:
  - Web
---
Apparently npm removed one of an author's modules to avoid possible brand infringement and in response, he removed his other ~250 modules.  Unfortunately, one of these modules called 'left-pad' was widely used which caused a cascade of build failures in some of the most popular projects on npm.

There was an interesting point made that this may be a consequence having a global namespace for package names instead of an origin.package style namespace.  The argument being it would sufficiently obvious that Azer.kik did not come from Kik the company thus weakening any brand infringement claims.

[Author's Post](https://medium.com/@azerbike/i-ve-just-liberated-my-modules-9045c06be67c#.iosd48tfi)
[Register UK](http://www.theregister.co.uk/2016/03/23/npm_left_pad_chaos/)