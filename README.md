Q.js
====

Q.js helps you build modern web apps.
It was developed by Qbix, Inc. as part of the larger Q framework that powers social apps.
Documentation will eventually become available at http://framework.qbix.com 
Until then, look through the file and use what you like.
Works on all modern browsers and IE6+.

Some notable features:

WEB RELATED
===========
Q.addScript, Q.addStylesheet, Q.cookie - loading scripts and stylesheets in ways that don't break your app
Q.Event - represents events, used for adding/removing handlers and triggering them
Q.handle - takes pretty much anything and executes it, whether a callback, an event, a URL, etc.
Q.page - create virtual "pages" that automatically manage loading / unloading and unhooking events
Q.activate - simply place a bunch of "tools" on a "page" and call this function

MIDDLEWARE
==========
Q.Pipe - an all-in-one way to structure your code flow, in a way that works with existing libraries through callbacks
Q.Cache - for caching stuff in the page, sessionStorage or localStorage, throws out least recently used, etc.
Q.getter - wrapper which makes any getter function smarter, using caching, waiting, throttling, without worrying about 
Q.batcher - wrapper for replacing one-by-one requests with batch requests that get auto-sent after a timeout or quota is filled

UTILITIES
=========
Q.copy - an easy way to clone objects, recursively if necessary
Q.extend - an easy way to extend objects, recursively/with prototypes if necessary
Q.mixin - a way to do class inheritance the Javascript way
Q.getObject, Q.setObject - easy way to get and set deeply nested properties
Q.md5 - to one-way-encode passwords etc. in insecure websites before sending to the server
String.prototype.queryField - used for getting/setting queryfields easily from location.hash etc.
String.prototype.htmlentities - encode HTML entities
etc.

To use Q.js, simply include it in your page. It has a lot of helpful Javascript functions, and works well with other libraries such as jQuery and Cordova/Phonegap.
    

Minimal example if you want to use Q.js as a front-end framework:
=================================================================
    Q.setObject({
        "Q.info.url": "http://example.com/MyApp/foo.html", // current url
        "Q.info.baseUrl": "http://example.com/MyApp", // base url of your app
        "Q.info.socketUrl": "http://example.com:3001", // if you have socket.io
        "Q.info.uri": {"module":"Example","action":"welcome"},
        "Q.info.uriString": "Example/welcome", 
        "Q.info.sessionName": "session_id", // name of session cookie
        "Q.info.slotNames": ["content","dashboard","title","notices"], // slots on the page
        "Q.app": "Example"
    });
    Q.handle.loadUsingAjax = true; // turns your app into an AJAX app automatically!
    Q.init();