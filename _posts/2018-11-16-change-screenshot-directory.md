---
layout: post
title:  "Change screenshot folder in MacOS"
date:   2018-11-16 18:58:30 -0800
---
# Change screenshot folder in MacOS

*By default, screenshots go to your desktop. Ugh. Use this guide to make your life a tiny bit better.*

## First, make a new folder
You can use Finder or the command line to make a new folder. In *Finder* you can use right-click. In the command line you can use *mkdir*.

## Then, open terminal
You can open by holding *command* and pressing the *spacebar*. Then type *terminal* and press *return*.

## Finally, type this
In terminal type this, but change the path to match the path to your new folder.

`defaults write com.apple.screencapture location /path/to/your/folder`

Now, when you take a screenshot (*Command+Shift+4*) it will go straight to its comfy new home instead of crapping up your desktop.