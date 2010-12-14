jquery-xpath-ify
==================================


My Need
----------------------------------

I'm on a web project where we have a lot of Javascript+jQuery, and I enjoy using Firebug to debug or interactively test out that JavaScript.

The JavaScript uses jQuery heavily. Most of the time I can grab the ID of the element I want to interact with, do `$('#id)` in Firebug's console, and I'm happy.

Sometimes I can't get the ID of the element. Maybe it doesn't have a name, just a CSS class... but I want to talk to that item specifically.

I know what element I want - look, I'm pointing at it with Firebug's Inspection tool.

Firebug has a "Copy XPath" feature in it, which would give me **exactly** what I want...

Except it's an XPath expression, and [I can't feed that into jQuery post 1.2](http://www.learningjquery.com/2007/09/upgrading-to-jquery-12)


To sum it up in a user story:

User Story
-----------------------------------
"As a user I should be able to easily use Firebug and get the jQuery object of (an item I can select) so I can test some jQuery code interactively"

Implementation
----------------------------------

I found [jQuery-xpath](https://github.com/jfirebaugh/jquery-xpath), and thought about incorporating it into my current project. That has two issues:

  * I should only use this in development mode, not in anything else
  * I hate to clog up the project with tools only I will use

I checked with my coworkers, and found there was no real excitement over this tool in the project. Yes, this is sad.

**So I went and built a bookmarklet**

[Visit the bookmarklet's page and install it](http://rwilcox.github.com/jquery-xpath-ify/). When you need a jQuery object from an XPath expression, click the bookmarklet. Now you have jquery-xpath loaded into your page (just like the [jQuery-ify Bookmarklet](http://www.learningjquery.com/2006/12/jquerify-bookmarklet)).

Now you can:

    $.xpath("expression")
    
And you're done.