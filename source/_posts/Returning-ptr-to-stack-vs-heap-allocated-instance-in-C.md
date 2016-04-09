---
title: Returning ptr to stack vs. heap allocated instance in C++
date: 2012-10-01 00:00:00
tags:
  - C++
---

{% codeblock lang:c %}
class Thingy;

Thingy* foo()
{
  int a; // Stack
  Thingy b; // Created on stack
  Thingy *ptr_to_b = &b;  // Points to address on stack
  Thingy *ptr_to_c = new Thingy(); // Points to address of thingy created on heap

  return pointer_to_c; // Safe - Thingy lives on heap and outlives foo().  Remember to delete.

  return pointer_to_b; // BOOM! Because b lives on stack and will be deleted when foo() returns.

{% endcodeblock %}