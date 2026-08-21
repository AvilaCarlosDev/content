---
title: "JavaScript Empty Array"
subtitle: "Learn how to check whether a JavaScript array is empty and how to clear an existing array using common JavaScript patterns."
tags: ["JavaScript", "arrays"]
authors: ["DF27ARTS"]
---

## Empty Array in JavaScript

An empty array in JavaScript is an array with no elements. You can confirm that a value is an array and that it is empty by combining `Array.isArray()` with the `length` property.

```js
const values = [];

if (Array.isArray(values) && values.length === 0) {
  console.log("The array is empty");
}
```

To clear an existing array while keeping the same reference, set its `length` to `0`.

```js
const values = [1, 2, 3];

values.length = 0;

console.log(values); // []
```

You can also assign a new empty array when the variable was declared with `let`, or use methods such as `splice()` and `pop()` depending on the behavior you need.
