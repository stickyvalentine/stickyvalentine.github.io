---
layout: post
title: "Tags with Jekyll / GitHub Pages"
tags: tags Jekyll GitHub Pages Liquid Minima Theme
abstract: "Adding tags to GitHub Pages mage with Jekyll can be tricky. Here's how I did it."
---
For most of this guide I am going to defer to [Long Qian](http://longqian.me/) who's [awesome guide](http://longqian.me/2017/02/09/github-jekyll-tag/)
I followed to get this working here. The reason I am posting it here now is so that I can remember later what I did. There is
also an extra bit I had to do to get it working correctly with the Minima theme that I wanted to document for my future self.

#### **First**, follow Long Qian's guide
Go and follow this guide. The tag cloud is optional but I decided to use it an put it in the footer. If it gets too big,
I might have to rethink that. I also have been using his python script to generate tag pages. It has all worked flawlessly.

#### **Then**, come back here
When I finished with the guide above, the only problem I had was that my header menu suddenly listed all of the tag pages.
To fix it, this is what I came up with.

**Make sure** you have a copy of `_includes/header.html` in your site directory. If you aren't sure where to get it,
see [this post](/2018/11/17/remove-rss-link.html) for the general idea.

`header.html` is the file that controls how the header displays, which is where the menu is. Specifically, this is the code
that creates the menu:

{% raw %}
```liquid
{%- if my_page.title -%}
  <a class="page-link" href="{{ my_page.url | relative_url }}">{{ my_page.title | escape }}</a>
{%- endif -%}
```
{% endraw %}

This tells Jekyll to look at each page to see if it has a `.title` attribute. If it does, then do the
thing in the next line, which tells it to print the name of the page and make it a link to the page.

The thing that determines if a page has a `.title` attribute is the front matter of the page.

```
---
layout: page
title: "Page Title"
---
```

What I did was use the same idea to create a new attribute that tells Jekyll if it should include the page titke
in the menu or not.I called the attribute `.menu`. It can be set to true in the front matter if the post should
be included in the menu. If not it can be left out of the front matter all together.

Change the previous snippet from the `_includes/header.html` file to look like this:

{% raw %}
```liquid
{%- if my_page.title -%}
  {%- if my_page.menu -%}
    <a class="page-link" href="{{ my_page.url | relative_url }}">{{ my_page.title | escape }}</a>
  {%- endif -%}
{%- endif -%}
```
{% endraw %}

This will add an *if* statement that checks to see if a page has a `.menu` attribute and only then add it to the header menu.

Finally, if you want a page to be included in the menu add the menu attribute to the front matter like this:

```
---
layout: page
title: "Page Title"
menu: true
---
```