localStorage
===

An inefficient, but as W3C-compliant as possible using only pure JavaScript, `localStorage` implementation.

    var localStorage = require('localStorage');

API

  * getItem(key)
  * setItem(key, value)
  * removeItem(key)
  * clear()
  * key(n)
  * length

Tests

    0 === localStorage.length;
    null === localStorage.getItem('doesn't exist');
    undefined === localStorage['doesn't exist'];

    localStorage.setItem('myItem');
    "undefined" === localStorage.getItem('myItem');
    1 === localStorage.length;

    localStorage.setItem('myItem', 0);
    "0" === localStorage.getItem('myItem');

    localStorage.removeItem('myItem', 0);
    0 === localStorage.length;

    localStorage.clear();
    0 === localStorage.length;

TODO / Bugs
---

  Does not persist.
  Doesn't not emit `Storage` events
