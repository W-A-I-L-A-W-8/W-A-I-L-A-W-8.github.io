---
layout: post
title: Starting a simple local server on MAC from any directory
published: true
categories: Might be Useful
---

So you want to test your static website on a local server? If you're a MAC owner there is only one command you need to start a server from any directory you wish to test. Before I continue, a thank you to an article I found on [Lifehacker](http://lifehacker.com/start-a-simple-web-server-from-any-directory-on-your-ma-496425450) for the reference.

### Here's the snippet
From Terminal simply navigate (CD) into any directory.  For example:

    $ CD mysitefortesting

Then enter this command. MAC already has Python built in.

    $ python -m SimpleHTTPServer 8000

You can use a port other than 8000 if you wish. Finally, open up a browser window and just type **localhost:8000** in the address bar and your site should start running in it's full glory.

To stop the server the command is as usual **ctrl C**

And that's it, a beauty of a snippet. It works too!
