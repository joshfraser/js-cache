js-cache
========

JS-Cache is a browser extension that adds a local JavaScript Cache to your browser to make the websites you visit load faster.

The goal of this project is to develop Chrome & Firefox plugins that automatically detects when popular AJAX libraries are included on a webpage and serve them from a local cache instead of fetching the requested file from the remote server. Since these JavaScript libraries tend to be quite large (50k or more), this plugin could shave a second or two off your load time, especially if you are visiting a website for the first time.

Initial library support (basically everything that is available in [Google's AJAX libraries API](https://developers.google.com/speed/libraries/)):

* AngularJS
* Chrome Frame
* Dojo
* Ext Core
* jQuery
* jQuery UI
* MooTools
* Prototype
* script.aculo.us
* SWFObject
* WebFont Loader

Questions:
=========

Q: Doesn't the Google AJAX libraries API solve this?

A: Not all developers use the AJAX libraries from Google.  Identical files are downloaded over and over again.

Q: How does it detect which AJAX library a website is using?

A: We detect the library and version # using a simple regexp on the filename.

Q: What happens if someone modifies the library code but saves it with the same filename?

A: After the page has loaded, we download the original file and check the hash of the content.  If it's different, we'll swap in the original file.

Q: Shouldn't this just be built into browsers?

A: Yep.  Someday!
