---
layout: post
title:  "Remove Link to RSS Feed in Minima"
tags: [Jekyll, RSS, Gems, Themes, Minima]
---
*Minima, the default Jekyll theme comes with a RSS feed link. This is how to get rid of it*

Its worth noting that the default *Minima* theme is Gem-based. That means that some of the theme files are stored somewhere other than your main site directory. When your site is built, Jekyll looks them up and uses them to build the site. But you can override them by putting an updated copy in your main directory. Then Jekyll will use thoses versions of the files instead. Then you can make changes to these copies and Jekyll with use them instead. 

#### **First**, find the theme files
You can find the theme files by typing `bundle show minima` into a termial window. Bundler will tell you where the files are on your system. In my case, bundler said this:

`/usr/local/lib/ruby/gems/2.3.0/gems/minima-2.1.0`

If you go there and poke around a little, you will see some files and directories. These will probably see directories called *_includes, _layouts, _sass,* and *assets*. The file we are looking for is *home.html* and it's in *_layouts*. 

#### **Then**, make a copy of *_layouts > home.html*
When you bring over a copy of this file, you want to keep the directory structure. That means that it should still be in a folder called *_layouts* which should be in the main site folder. You can make the folder and copy the html file using Finder or the command line. Just make sure everything has the same names.

#### **Finally**, edit the new copy of *_layouts > home.html*
Using your favorite text editor (mine is emacs), open *_layouts > home.html* and find the offending line. It should looks something like this:

`<p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | relative_url }}">via RSS</a></p>`

You can comment it out by wrapping it in some of these: `<!-- -->` All together it should look like this:

`<!--<p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | relative_url }}">via RSS</a></p>-->`

**Now**, save the changes check to make sure you don't see the RSS link anymore. 
