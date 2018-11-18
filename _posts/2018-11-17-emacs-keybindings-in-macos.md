---
layout: post
title: Emacs Keybindings in MacOS
tags: [MacOS, Emacs, keybindings, Linux]
---
At work, I was given the choice between a MacOS or a Windows machine. My default answer is to
take the Windows machine and put Linux on it. In this case, that wasn't a practical option.
What I ended up with is a MacBook Air *and* a Windows Desktop. Overall, I'm indifferent to
these OSs and approach both with a bit of cynicism. Apple makes beautiful, expensive things
that redefine the word 'proprietary'. Windows is a more accessible ad-driven mess. For all
of it's [many faults](https://www.youtube.com/watch?v=WipM3SAYqK4), the only OS that I feel
any loyalty towards is Linux.

But since I started using the MacBook Air for work, I realized something that makes choosing
between MacOS and Windows a bit easier. MacOS naively supports some of the basic Emacs
keybindings when editing text fields. I discovered it when I was editing a Google Doc and
reflexively pressed `Ctrl-p` to move the cursor up a line *and it worked*. I don't mean to
overstate, but when it happened, the clouds parted and a single ray of sun shone down upon
my caps lock key (which is switched to Ctrl). I even had a sense that somewhere,
[St. IGNUcius](https://stallman.org/saint.html) gave a begrudging nod.

I assumed Google Docs had starting supporting the keybindings. I promptly told several people
who politely pretended to care. But the next time I was using Docs on a Windows machine it
didn't work. So I looked it up. [Sure enough](https://jblevins.org/log/kbd), those keybindings
are built into MacOS. That means that these bindings work in *any* text field on MacOS.

Even though it sounds like a joke about [RMS and Steve Jobs](https://features.slashdot.org/story/13/01/06/163248/richard-stallman-answers-your-questions)
sharing an elevator, if you are someone who is comfortable with the cursor movement in Emacs,
this seems as good of a reason as any to prefer one of these OSs to the other.

Here are some of the basics:

|Keybinding |Action |
|--------|-------|
|⌃a |Jump to the start of the line |
|⌃e |Jump to the end of the line (end)|
|⌃f |Move the cursor forward |
|⌃b |Move the cursor backward |
|⌃n |Move the cursor down (next)|
|⌃p |Move the cursor up (previous)|
|⌃k |Delete to the end of the line (kill)|

Look at [Jason Blevin's post](https://jblevins.org/log/kbd) to see a detailed comparrison between
Emacs and MacOS keybindings.