---
title: Table Driven Design Example
date: 2016-03-23 00:00:00
tags:
  - ECMAScript
  - Reduction
---

{% codeblock %}
let result;
if (isBar) {
   if (isBaz) {
      result = 'foo truetrue';
   } else {
      result = 'foo truefalse';
   }
} else {
   if (isBaz) {
      result = 'foo falsetrue';
   } else {
      result = 'foo falsefalse';
   }
}
{% endcodeblock %}

Can be reduced to

{% codeblock %}
const fooByIsBarIsBaz = {};
fooByIsBarIsBaz[true] = {};
fooByIsBarIsBaz[true][true] = 'foo truetrue';
fooByIsBarIsBaz[true][false] = 'foo truefalse';
fooByIsBarIsBaz[false] = {};
fooByIsBarIsBaz[false][true] = 'foo falsetrue';
fooByIsBarIsBaz[false][false] = 'foo falsefalse';
const result = fooByIsBarIsBaz[isBar][isBaz];
{% endcodeblock %}

{% codeblock %}
console.log(fooByIsBarIsBaz); // { false: { false: "foo falsefalse", true: "foo falsetrue" ...
console.log(fooByIsBarIsBaz[true][false]); // foo truefalse
{% endcodeblock %}