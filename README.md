# Introduction

Penguin is a minimal, responsive blog theme for [Pelican](http://docs.getpelican.com/) that does not implement all Pelican theme features in-full which is why I've created this separate project from the official [Pelican themes](https://github.com/getpelican/pelican-themes) repository.

A friend asked to reuse the theme so here is an introduction to the theme and some quick tips on getting started. To learn more on complete Pelican theme development please read their [documentation](http://docs.getpelican.com/en/3.1.1/themes.html). If I missed anything and you have a question open an issue.

## Overview

The goal behind Penguin was to create an extremely minimal, responsive theme offering authors a basis to begin publishing, and for those willing to further customize... a starting point.  It's not complete but it functions well for its current needs.

This Penguin blog theme is currently employed on the not-updated-frequently-enough [Montylounge](http://blog.montylounge.com/) blog.

Pengiun also includes [PrismJS](http://prismjs.com/) for all your code highligthing needs.

Additionally, Penguin does offers one unique feature — post Types, supporting additional displays for posts of a specific Type beyond generic Article posts.

The custom Types supported are:

* Screencast
* Quote
* Bookmark

Here's [an example](http://blog.montylounge.com/2010/02/11/integrating-mongodb-and-django/) of a Screencast Type post.

Here's [an example](http://blog.montylounge.com/2010/01/08/the-truest-sentence-you-know/) of a Quote Type post.

Here's [an example](http://blog.montylounge.com/2011/08/07/beginners-guide-pip-and-virtualenv/) of a Bookmark Type post.

Here's [an example](http://blog.montylounge.com/2011/08/04/in-review-of-sass/) of an Article post including code snippets.

This feature is supported by setting the 'Type' value of the post's metadata. Here is an example of a post with 'Type' Bookmark.

```
Title: Example Bog Post
Date: 2014-05-24
Tags: tutorial, pelican
Type: Bookmark
Category: Code
Author: Jane Smith
Link: https://github.com/getpelican/pelican

Here is where you write the content of your post.
```

Each Post has an optional `Photo` meta attribute. Any Article with `photo` specified will display the photo as the first content element below the Article Date and Article Title. The attribute 'PhotoColor' is a horrible name because it actually sets the background-color of the element container for the photo. Example Article post with Photo and PhotoColor specified.

```
Title: Coding on the beach
Date: 2014-05-24
Tags: claire
Category: Beach
Author: Joe Smith
Photo: foo.jpg
PhotoColor: #f7f7f7

Here is where you write the content of your post.
```

On the default list view (aka homepage, aka index.<html>
<head>
	<title></title>
</head>
<body>

</body>
</html>) if the most recent post contains a Photo then the photo will display, otherwise no other items in the archive list will display a photo. Take a look at `article.html` to view the conditional logic. 

I have provided a `pelicanconf.py.example` file to get your configuration settings started. In this file there is one section you should pay specific attention to. These settings are custom Penguin theme values used to set values dynamically in the `base.html` template.

```
# BEGIN CUSTOM PENGUIN SETTINGS
COMPANY_NAME = u'YOUR COMPANY NAME'
COMPANY_URL = 'YOUR COMPANY URL'
LOGO_SRC = 'YOUR LOGO URL'
LOGO_URL = "/"
TWITTER_URL = 'YOUR TWITTER URL'
BASE_META_DESCRIPTION = u'ACME SITE - Your description here.'
# END CUSTOM PENGUIN SETTINGS
```

There is also a `publishconf.py.example` file provided. If you use `make publish` to generate and publish your site these settings will be used. 

## Included Components

* Bootstrap 2.3.1
* Font-Awesome 3.1.0
* [PrismJS](http://prismjs.com/) for code highlighting.
* Fonts rendered via Google Web Fonts

## Developing Locally Tip

When testing locally use pelicanconf.py settings for generic, non-production values. Keep settings for production in publishconf.py (SITEURL, GOOGlE_ANALYTICS, etc).


