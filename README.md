DOMStorage
===

An inefficient, but as W3C-compliant as possible using only pure JavaScript, `DOMStorage` implementation.

Purpose
----

This is meant for the purpose of being able to run unit-tests and such for browser-y modules in node.

Usage
----

    var Storage = require('dom-storage')
      , localStorage = new Storage('./db.json') // in-file
      , sessionStorage = new Storage()                // in-memory
      , myValue = { foo: 'bar', baz: 'quux' }
      ;

    localStorage.setItem('myKey', JSON.stringify(myValue));
    myValue = localStorage.getItem('myKey');

API
---

  * getItem(key)
  * setItem(key, value)
  * removeItem(key)
  * clear()
  * key(n)
  * length

Tests
---

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

Notes
---

  * db is read in synchronously
  * No callback when db is saved
  * Doesn't not emit `Storage` events (not sure how to do)
