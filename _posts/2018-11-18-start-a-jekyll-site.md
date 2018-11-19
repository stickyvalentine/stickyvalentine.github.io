---
layout: page
title: Start a Jekyll Site
tags: [Jekyll, GitHub, Ruby, Bundler, Markdown, Liquid]
---
<span style="color:#F778A1">Jekyll is a platform for quickly and easily creating static sites using Markdown and Liquid as well as HTML and CSS.
This guide will get you started.</span>

**There are a lot of reasons** to like Jekyll as a site building / blogging platform. Here are some of my favorites:

 * It supports Markdown and Liquid.
 * You can do most of your work with just Emacs and Git.
 * It has a low barrier to entry.
 * GitHub will host your site for free.
 * Static pages are cool.

#### **First**, install Jekyll

**Install Ruby**

This will be different depending on your OS but [this page](https://www.ruby-lang.org/en/documentation/installation/)
will get you set up.

**Install Bundler**

`gem install bundler`

**Install Jekyll**

`gem install jekyll`

#### **Next**, make a new Jekyll site.

Type this into a terminal, replacing *newsitename* with the a name of your choice. This command will create a new
folder in the current directory that contains all the files needed for your site.

`jekyll new newsitename`

Now, change directories to your new Jekyll site directory. 

`cd newsitename`

Poke around if you like. When you are ready to launch your site, go to the root of the new site directory and
type the following:

`bundle exec jekyll serve`

*Note: This command is only necessary the first time you launch the site. After that all you need is* `jekyll serve`
*from the site directory root.*

You can now see your new site by pointing a web browser to 127.0.0.1:4000

Your site is running locally on your computer. To stop it type `Ctrl-c` in the terminal.

#### **Finally**, Make a new post.

Posts go in the `_posts` directory. To add a new post, make a new markdown file there. Just
make sure your new file follows this naming convention:

`yyyy-mm-dd-name-of-the-post.md`

If you make a post using this convention, add some Markdown and run `jekyll serve`, you will see that the post you made
doesn't have the same formatting as the rest of the site. That's because you didn't include any *front matter*.

Front matter gives jekyll more information about your post. Add the following to the top of your new post and see how it changes:

```YAML
---
layout: page
title: Newest Post
---
```

To learn more about what you can do with *front matter* [read this](https://jekyllrb.com/docs/front-matter/).

For Jekyll tutorials [go here](https://jekyllrb.com/tutorials/home/).

To learn how to use GitHub pages to host your Jekyll site, check back later or [travel forward in time](https://www.news.com.au/technology/time-travel-possible-but-only-moving-forwards-says-stephen-hawking/news-story/07bb5bc3f786276c837ce99c7323583b) to my next post.
