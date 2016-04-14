---
title: Left Pad Liberation
date: 2016-03-23 00:00:00
tags:
- Web
---
It looks like npm removed a module to avoid possible brand infringement leading to the author removing all of his modules from npm.  Among the modules removed is a widely used module called 'left-pad' which triggered a cascade of build failures in some of the most popular projects on npm.

There was an interesting point made that this may be a consequence having a global namespace for package names instead of an origin.package style namespace.  The argument being it would make it more obvious that Azer.kik didn't come from Kik (the company) removing possible confusion and weakening any brand infringement claims.

[Author's Post](https://medium.com/@azerbike/i-ve-just-liberated-my-modules-9045c06be67c#.iosd48tfi)
[Register UK](http://www.theregister.co.uk/2016/03/23/npm_left_pad_chaos/)