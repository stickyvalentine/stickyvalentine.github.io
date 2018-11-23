---
layout: post
title: Customize Gem-based Jekyll Themes
abstract: Gem-based Jekyll themes keep some of their parts tucked away in a Gem. This is how to make changes to the theme while keeping the Gem intact.
tags: Gems theme Jekyll
---
Some Jekyll themes are Gem-based meaning that parts of the theme are kept seperate from the site's main directory in a *Gem*. That way the gem can get updates from the theme developer without affecting the content of the site.

If you are using a Gem-based Jekyll theme, there are a few reasons you might want to keep the original Gem intact when you modify the theme. One reason is that you will have a backup in case something goes wrong. Another is that you will be able to get updates from the developer without loosing cusotomizations.

If haven't changed your theme since installing Jekyll, it's a safe to assume that you are using Minima, which is the default Jekyll theme. It is also Gem-based.

It's easy to make changes to a Gem-based theme without chaning the Gem files: **First**, locate the Gem directory. **Then**, copy the file you need to your site directory. **Finally**, make changes to the copies. The altered copies of the files will override the files in the Gem when your site is generated.

#### **First**, Locate the Gem directory
In a terminal navigate to your Jekyll site root. Then, to find the Gem directory for your theme type `bundle show` followed by the *name of your theme*. If you are using Minima, you would type `bundle show minima`. Bundler is program for managing Gems. This command tells Bundler to show us where the Minima Gem is. In my case, Bundler replied with `/Library/Ruby/Gems/2.3.0/gems/minima-2.5.0`.

#### **Then**, copy the file you need
To copy the file you want to change and put it in the site directory. Just make sure to preserve the directory structure of the Gem. For example, if the location of the file in the Gem is [root] > _layout > post.html, make sure post.html ends up in a directory called _layout which is in the root of your site directory. If there isn't a directory called _layout yet, you can make one.

#### **Finally**, make changes to the copies
Now, Jekyll will use the copied version of the file instead of the originals in the Gem. You can change them without affecting the Gem. Not only that, but you can safely update the Gem with out loosing the changes you have made. 