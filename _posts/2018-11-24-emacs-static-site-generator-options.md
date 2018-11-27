---
layout: post
title: 'Emacs + Static Site Generator Options'
abstract: 'While Jekyll seems to suit my needs, It has made me curious about other publishing options that are available. Here, I look at a few that seem interesting.'
tags: Emacs static-site-generator RSS Marmalade Melpa Org-Mode HTML Markdown Lisp Python CSS GitHub Pages
---
#### Org-Static-Blog
[Org-Static-Blog](https://github.com/bastibe/org-static-blog/) is an Emacs package and can installed using Marmalade or Melpa-Stable. It converts Org-Mode files into HTML pages as well as making an index page, an archive page, RSS feed, and tag pages much like the ones on this site.

It sounds like it would be similar to my current Emacs/Jekyll work-flow except instead of running a python script to generate tag pages, Org-Static-Blog would do it automatically. Also, instead of Markdown, content would be made in Org-Mode.

As much as I like the idea of Org-Mode I am more comfortable with Markdown. On the other hand, it might be a good chance to get used to Org-Mode. This is probably the one I am the most interested in trying because more of the work-flow takes place inside Emacs. It's also cool that it's written in Emacs Lisp.

#### O-Blog
[O-Blog](http://renard.github.io/o-blog/index.html) is also an Org-Mode-based platform. It looks a bit more complicated and a bit more powerful when compared with Org-Static-Blog. Its focuses on the use of templates which are HTML-based but also support Emacs Lisp, possibly covering some of the same territory as Liquid does in Jekyll. I'm curious about how that works. 

#### Org-Page
[Org-Page](https://github.com/kelvinh/org-page) is yet another Org-Mode based static site generator and seems to have many of the same features as the others I have mentioned. The thing that stuck out to me when looking over it was [the example blog](http://kelvinh.github.io/). I love the layout and the fonts and even thought I think a lot was lost in the google translation, I really liked reading the posts. It looks like it might not be maintained anymore.

#### Lazyblorg
[Lazyblorg](https://github.com/novoid/lazyblorg) is written in Python and designed to have a very streamlined workflow. It's basically a parser for Org-Mode files. Every time you run it, all pages are rendered. I imagine Performance takes a hit but it probably doesn't add up to much unless you have a lot of pages. It doesn't support all Org-Mode syntax but I don't think that would be too much of an issue for my purposes. It uses HTML 5 and CSS 3 which is cool. Some setup is required but that is to be expected, maybe even fun.

It looks like this was designed to remove unnecessary steps in the process of publishing content. The thing is, I really don't mind the work involved in my workflow now. I think if I were blogging more seriously, I might think differently. But right now, I make Markdown files in Emacs, put them in the `_posts` directory, run a python script and push them to GitHub. Voila. Well, I guess it doesn't sound super quick but after the post is done, the rest only takes a few seconds.

#### Hugo
[Hugo](https://gohugo.io/) is probably the second most popular static site generator after Jekyll. It's written in Go, so it's fast. Like Jekyll, Hugo has a built in development server but unlike Jekyll the server offers a feature called LiveReload that watches for changes while it runs. Hugo also offers menus. In fact Hugo seems more developed than Jekyll in most ways.

What keeps me using Jekyll, at least for now, is the integration with GitHub Pages. And that really comes down to free hosting and integrated version control. And even though Hugo has more (really cool) features, they aren't really things that I feel like I'm missing. For example, the LiveReload is awesome, but because I use the same terminal session to write posts, start the development server and push to GitHub, it doesn't offer any advantages for me. If I were to use a graphical text editor I might feel differently. As it is, I really value the low-noise keyboard-based environment of a shell, even if it means a few extra steps or a few less features.

#### Conclusion
At least for now, I think I am going to stick with my Emacs > Jekyll > Git workflow. Even though there are some really cool options for static site generators, none of them seem to be a better fit for me than what I am using now. This is partly because of the Jekyll/GitHub integration and partly because of some of my personal (possibly idiosyncratic) preferences.