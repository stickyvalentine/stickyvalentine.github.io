---
layout: post
title: "Tags with Jekyll / GitHub Pages"
tags: tags Jekyll GitHub Pages Liquid Minima themes
abstract: "Adding tags to GitHub Pages mage with Jekyll can be tricky. Here's how I did it."
---
For most of this guide I am going to defer to [Long Qian](http://longqian.me/) who's [awesome guide](http://longqian.me/2017/02/09/github-jekyll-tag/)
I followed to get this working. I'm posting it here so later I can remember what I did. There is
also an extra bit to get it working correctly with the Minima theme that I don't want to forget.

#### **First**, follow Long Qian's guide
Go and follow this guide. The tag cloud is optional but I decided to put it in the footer. If it gets too big,
I might have to rethink that. I have also been using Long Qian's python script to generate tag pages which works flawlessly.

#### **Then**, come back here
When I followed the guide, everything went smoothly and the tag system worked great. However, I did have one problem.
The menu section in the header started showing all of the `tag:` pages that were being generated by the python script.

I fixed it by making a `.menu` attribute for pages. Now a page will only show up in the menu if the the `.menu` attribute
is set to `true` in the front matter. Here's how it set that up:

**Make sure** you have a copy of `_includes/header.html` in your site directory. If you aren't sure where to get it, [this post](/2018/11/22/changing-gem-based-jekyll-themes.html) will help.

`header.html` is the file that controls how the header displays, which is where the menu is. Specifically, this is the code
that creates the menu:

{% raw %}
```liquid
{%- if my_page.title -%}
  <a class="page-link" href="{{ my_page.url | relative_url }}">{{ my_page.title | escape }}</a>
{%- endif -%}
```
{% endraw %}

This tells Jekyll to look at each page to see if it has a `.title` attribute. If it does, it says to do the
thing in the next line, which is to print the name of the page in the menu section and link it to its page.

The thing that determines if a page has a `.title` attribute is the front matter of the page.

```
---
layout: page
title: "Page Title"
---
```

I use the same idea and made a new attribute that tells Jekyll if the page should be included
in the menu or not. I called the attribute `.menu`. If it is set to true in the front matter, the page will
be included in the menu. If it is left out of the front matter completely, the page won't be in the menu.

I changed the previous snippet from the `_includes/header.html` file to look like this:

{% raw %}
```liquid
{%- if my_page.title -%}
  {%- if my_page.menu -%}
    <a class="page-link" href="{{ my_page.url | relative_url }}">{{ my_page.title | escape }}</a>
  {%- endif -%}
{%- endif -%}
```
{% endraw %}

This added an *if* statement that checks each page to see if it has a `.menu` attribute. If it does, it
continues to the line that adds it to the menu. Otherwise it skips it and moves to the next. 

Finally, if you want a page to be included in the menu, add the menu attribute to the front matter like this:

```
---
layout: page
title: "Page Title"
menu: true
---
```

Because none of the `tag:` pages have the `.menu` attribute, none of them will be included in the menu.