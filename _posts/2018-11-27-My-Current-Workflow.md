---
layout: post
title: 'My Current Workflow + Priorities'
abstract: 'This is my current workflow for this blog but it's also somewhat representitive of the way I work generally, at least when I have my way.'
tags: Emacs Lisp C editor Git Jekyll keybindings Python
---
#### Emacs
[Emacs](https://www.gnu.org/software/emacs/) is a 42 year old text editor developed by the MIT AI Lab, written in [Lisp](https://en.wikipedia.org/wiki/Lisp_(programming_language)). In fact, at its core it's a small Lisp interpreter written in C with the rest of the editor written in a dialect of Lisp specifically designed for Emacs called [Elisp](https://en.wikipedia.org/wiki/Emacs_Lisp). Emacs was based on [E](https://en.wikipedia.org/wiki/E_(text_editor)) which was the etitor that was used by Stanford's AI lab. The name Emacs stands for 'E with Macros'. The name refers the incredible extensibility of the editor which is often used to make [macros](https://en.wikipedia.org/wiki/Macro_(computer_science)).

While I don't nearly use Emacs to its full potential, I am quite comfortable with it. In this case I use it to create and edit the Markdown post files as well as all of the Jekyll configuration and layout files. It probably isn't as quick as VIM or as intuitive as a graphical editor, but I enjoy using it.

#### Jekyll
Besides the initial setup and occational settings and layouts tweaks, I really only use Jekyll for the production server to make sure everything looks alright before I push it to GitHub. This just involves typing `jekyll serve` in the site root directory and then pointing a browser to 127.0.0.1:4000. 

#### Python
Before pushing changes to GitHub, I run a [python script](https://github.com/qian256/qian256.github.io/blob/master/tag_generator.py) written by [Long Qian](http://longqian.me/). It reads the tags in the posts and creates a page for each tag that lists all of the posts that include that tag. Does that make sense?

#### Git
Because I have an easier time keeping track of things this way, I only work on my blog repository from one machine. Obviously, this is underutilizing Git, but it suits my needs and and it helps me to keep things clean and tidy. I add, commit and push changes to GitHub which is smart enought to rebuild the site with Jekyll.

#### That's it
If it is't clear, my priorities in the tools I choose and way I work has a lot to do with my personal comfort. Here are my guiding tenents.

**No Mouse.**
I would rather not use a mouse if I can avoid it. This is because I am lazy and don't like to move my hands from the keyboard unless I have to.

**No Noise.**
I also like low noise environments. I don't really know what I mean but it probably has something to do with not switching between different UI's. I dunno.

**Consistant Keybindings.**
I have [mentioned before](/2018/11/17/emacs-keybindings-in-macos.html), I like having consistant keybindings for moving the cursor around. Again, lazy.

I 