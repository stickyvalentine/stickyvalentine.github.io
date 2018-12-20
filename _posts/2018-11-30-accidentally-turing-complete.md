---
layout: post
title: "Accidentally Turning Complete"
tags: Turing-Complete Gödel Church Turing Dwarf-Fortress games celular-automation Lambda-Calculus Rule-110 Conway's-Game-of-Life Langton's-Ant Turing-Machine
abstract: "'Turing Complete' describes a system that is computationally complete. Here are some things that are unexpectedly turing complete and a little history."
---
### Gödel Screws Everything Up
Once uppon a time, in 1931, a guy named Kurt Gödel proved something bizare and alarming that turned mathematics upside down. For some time the world of mathematics was largely focused on trying to find a set of axioms to describe all mathematics. Then Gödel proved it wasn't possible. Just shut it down. The swift, fatal blow came in the form of the [Incompleteness Theorems](https://plato.stanford.edu/entries/goedel-incompleteness/) which proved that:

1. A system of a certain complexity can't be both consistant and complete.

2. Consistantcy of axioms can't be proved within their own system.

With that out of the way, many people wondered what else their whole lives could be about. Maybe they needed to dig deeper and first understand what was and wasn't [computable](https://en.wikipedia.org/wiki/Computability). As it turns out, part of the answer to that question was the turing machine.

### Turing Completeness
A [Turing Machine](https://www.cl.cam.ac.uk/projects/raspberrypi/tutorials/turing-machine/one.html) is a hypothetical computation machine described by [Alan Turing](https://en.wikipedia.org/wiki/Alan_Turing) in 1936. It's a simple mechanism that reads, writes, and rewrites symbols on a tape following a set of rules. 

Here is an example of a set of such rules. This turing machine reads the binary number on the tape and increments it by 1. 

<table>
    <thead>
        <tr>
            <th> Step </th>
            <th> Read </th>
            <th> Write </th>
            <th> Move </th>
            <th> Next Step </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="3" > 1 </td>
            <td> Blank </td>
            <td> Blank </td>
            <td> Left </td>
            <td> 2 </td>
        </tr>
        <tr>
            <td> 0 </td>
            <td> 0 </td>
            <td> Right </td>
            <td> 1 </td>
        </tr>
        <tr>
            <td> 1 </td>
            <td> 1 </td>
            <td> Right </td>
            <td> 1 </td>
        </tr>
        <tr>
            <td rowspan="3" > 2 </td>
            <td> Blank </td>
            <td> 1 </td>
            <td> Right </td>
            <td> 3 </td>
        </tr>
        <tr>
            <td> 0 </td>
            <td> 1 </td>
            <td> Left </td>
            <td> 3 </td>
        </tr>
        <tr>
            <td> 1 </td>
            <td> 0 </td>
            <td> Left </td>
            <td> 2 </td>
        </tr>
        <tr>
            <td rowspan="3" > 3 </td>
            <td> Blank </td>
            <td> Blank </td>
            <td> Left </td>
            <td> Stop </td>
        </tr>
        <tr>
            <td> 0 </td>
            <td> 0 </td>
            <td> Right </td>
            <td> 3 </td>
        </tr>
        <tr>
            <td> 1 </td>
            <td> 1 </td>
            <td> Right </td>
            <td> 3 </td>
        </tr>
    </tbody>
</table>

The way that you would read the instructions would be something like:

> Step 1: Read the symbol in the current position. If it is 'Blank', keep it that way and move one position to the left. Then go to step 2.

In this way, the tape starts with one set of symbols, follows the rules, and when it's done ends up with a different set of symbols. As it turns out, this simple machine can compute anything that is computable. Because of this fact, the term 'turing complete' can be used to describe a system that can compupute the same things that a turing machine can; that is to say, anyting computable.

There are other systems that perfectly overlap the abilities of the turing machine. One of these systems was described before the turing machine by a mathematician named [Alanzo Church](https://en.wikipedia.org/wiki/Alonzo_Church). That system, known as the [Lambda Calculus](https://www.inf.fu-berlin.de/lehre/WS03/alpi/lambda.pdf) is a tiny formal system of logic that, even thought it is appears very different from a turing machine, is its formal equivalent. Later, Alan Turing and Alanzo Church would combine and distill the ideas behind these systems in to the famous [Church-Turing Thesis](https://plato.stanford.edu/entries/church-turing/) in an attempt to formalize the notion of computability. 

There is a caveat when speaking about Turing Completeness. Because the turing machine is hypothetical, it can have potentially infinite tape. Since that can't ever be realized, neither can an actual Turing Complete machine. But if we can overlook this limitation, there are real systems that we can call 'turing complete'. This is a simplification, but for the purposes of this post it should do.

### To The Point
But this post wasn't intended to be a history lesson. It's supposed to be a look at some surprising things that turn out to be turing complete. So lets got on with it.

#### Dwarf Fortress

For the uninitiated, [Dwarf Fortress](http://www.bay12games.com/dwarves/) is an ASCII-based game that's part builder, part roguelike, and part resource management. It's a vast, complicated game that can be intimidating at first but once you get past that, it will ruin your life.

Because I love Dwarf Fortress, this is the one that I am the most excited about and the impetus for this post.

The proof that Dwarf Fortress is turing complete is evident when looking at [this](http://mkv25.net/dfma/map-8269) turing complete computer, built by dwarven hands and overseen by [Jong89](http://mkv25.net/dfma/user-Jong89) in 2010.

> This monumental build contains 672 pumps, 2000 logs, 8500 mechanisms and thousands of other assort bits and knobs like doors and rock blocks.

#### Minecraft
Minecraft is probably the most well known Turing Complete accident on this list. For many people it seems to be a gateway to the [weird and wonderful](https://www.youtube.com/watch?v=2Op3QLzMgSY) world of computer science. Both of my children have independently spent many hours building logic devices in Minecraft. Indeed, I think many young people have a sense of fundamental CS concepts because of Minecraft. With all of the [logic gates](https://minecraft.gamepedia.com/Tutorials/Basic_logic_gates) that can be built in Minecraft it easily qualifies as Turing Complete but incase you aren't convinced you should look at this [redstone computer](https://www.youtube.com/watch?v=SPaI5BJxs5M).

In the same sense Little Big Planet, Prison Architect and probably other games also contain the logic gates necessary to build a Turing Complete machines.

#### Minesweeper
In an [academic paper](http://web.mat.bham.ac.uk/R.W.Kaye/minesw/infmsw.pdf) published in 2007 by [Richard Kaye](http://web.mat.bham.ac.uk/R.W.Kaye/) of [The University of Bermingham](https://www.birmingham.ac.uk/index.aspx) proves that the game [Minesweeper](https://en.wikipedia.org/wiki/Minesweeper_(video_game)) is not only Turing Complete but also [NP-Complete](NP-completeness - Wikipedia
https://en.wikipedia.org/wiki/NP-completeness). 

#### Magic: The Gathering
This is the one I was most surprised by. In [this](https://www.toothycat.net/~hologram/Turing/HowItWorks.html) article [Alex Churchill](https://www.toothycat.net/~hologram/Turing/About.html) explains in great detail how [Magic: The Gathering](https://magic.wizards.com/en) can be set up and played according to the in-game rules to simulate a turing machine, making the game turing complete. Because I've never played Magic, I can't say it makes much sense to me, but the thought and time Alex put in to not only figuring this out, but carefully laying it all out makes me want to learn.

#### Cellular Automata 
In the 1940's  [Stanislaw Ulam](https://en.wikipedia.org/wiki/Stanislaw_Ulam) and [John von Neumann](https://en.wikipedia.org/wiki/John_von_Neumann) discovered the concepts of [Cellular Automation](https://en.wikipedia.org/wiki/Cellular_automaton). Like Turing Machines and The Lambda Calculus, Cellular Automata are simple systems with simple rules that can model complicated processes. So, maybe it isn't all that surprising that some of these systems are also Turing Complete.

**Langton's Ant** is an imaginary ant that walks around on a grid of black and white squares following these rules:

* At a white square, turn 90° right, flip the color of the square, move forward one unit
* At a black square, turn 90° left, flip the color of the square, move forward one unit

These simple rules lead to complex emergent behavior that is often observed to follow this pattern:

1. Simplicity - Simple, often symmetrical patterns appear early.
2. Chaos - Large, irregular patterns gradually form.
3. Order - Regardless of the starting position, the ant *always* ends up in a looping 'highway' pattern

This last point is only an observation. Theres is no proof that this will always be the case. 

And while I don't understand it, [this paper](http://www.dim.uchile.cl/~anmoreir/oficial/langton_dam.pdf) by Gajardo, Moreira and Goles proves that Langton's ant is Turing Complete.

**Rule 110** may be the simplest Turing Complete system but it is probably not the simplest to explain. It takes a sting of 1's and 0's which continually evolve based on a simple set of rules. Each new iteration of the process is determined by the previous.

The value of a given position either changes or stays the same based on its previous value and the values of its previous adjacent neighbors following these rules: 

| 111 | 110 | 101 | 100 | 011 | 010 | 001 | 000 |
|-----|-----|-----|-----|-----|-----|-----|-----|
|  0  |  1  |  1  |  0  |  1  |  1  |  1  |  0  |

So, a 1 surrounded by 1's becomes a 0 in the next iteration.

In this patern, the absense of a value is considered 0. So a string containing a single 1 is thought to be flanked by on either side by infinite invisible 0's. It's unnecessary to evaluate all of these 0's because any group of 3 0's resolves to a 0. Until you get to a number that *is* or is adjacent to a 1, everything is 0's.

`001`<br>
`011`<br>
`111`<br>

Let's try it with 001. We start with the first 0 which has another 0 to its right and an imaginary 0 to its left. Because 000 resolves to 0, the first number in our next iteration will be 0. The next digit in the triplet is a 0 with a 0 on the left and a 1 on the right. 001 resolves to 1 which is our second digit. Then we have a 1 with 0's on either side which resolves to 1. And so, 001 becomes 011. Following the same rules, the next iteration will be 111.

Almost as interesting as the fact that such a simple set of rules is computationally complete is the [sordid](https://cs.nyu.edu/pipermail/fom/2002-July/005692.html) and [ugly](http://bactra.org/reviews/wolfram/) story of the publication of [the proof](https://www.complex-systems.com/abstracts/v15_i01_a01/). It's suficent to say the proof was written by [Matthew Cook](https://www.ini.uzh.ch/en/institute/people?uname=cook) and not Stephen Wolfram, as much as Wolfram insists otherwise. 

**Conway's Game of Life** might be the most recognizable of the Celular Automata, possibly to [John Conway's irritation](https://www.youtube.com/watch?v=E8kUJL04ELA). 

The game takes place on a grid. Squares that are filled in are said to be alive. Squares that are left empty are dead. If a square, alive or dead, has too many or too few neighbors it will be dead in the next generation. As with Rule 110 and Langton's ant, the rules are simple.

* A living square with less than 2 or more than 3 living neighbors will die.
* A dead square with exactly 3 living neighbors will come to life. 

One possible reason for the [interest](https://www.theguardian.com/science/alexs-adventures-in-numberland/2014/dec/15/the-game-of-life-a-beginners-guide) in the Game of Life is beauty of some of the patterns that have been discovered. Since the game was conceived by John Conway, [many](http://conwaylife.com/wiki/Category:Patterns) interesting patterns and structures and have been discovered and engineered. 

[R-pentomino](http://conwaylife.com/wiki/R-pentomino) is an early example of a [Methuselah](http://conwaylife.com/wiki/Methuselah) which is a pattern that takes a long time to stabilize and is noteworthy because of it's small size. 

Another early discovery was a group of patterns known as [eaters](http://conwaylife.com/wiki/Eater) which are [still life](http://conwaylife.com/wiki/Still_life) patterns that can destroy certain other patterns without taking permanent damage. In that way they they are said to eat the other pattern. 

But some of the most recognizable early patterns were [guns](http://conwaylife.com/wiki/Gun) which are stable, stationary patterens that continually emit [spaceships](http://conwaylife.com/wiki/Spaceship) or gliders. Possibly the most recognizable Game of Life pattern is the [Gosper's Glider Gun](http://conwaylife.com/wiki/Gosper_glider_gun).

Using these and other basic structures as primitives, some [pretty amazing things](http://conwaylife.com/wiki/Gemini) have been engineered. 

As you have probably guessed, The Game of Life is Turing Complete. [Here](http://rendell-attic.org/gol/tm.htm) is a Turning Machine built with it and [here](https://hal.archives-ouvertes.fr/hal-00461197/document) is a book that explains how it works.

#### Steam-Powered Turing Machine
It seems worth mentioning that in 1837 (not a typo) [Charles Babbage](https://en.wikipedia.org/wiki/Charles_Babbage) designed a machine that, had it been funded and built, would have been the worlds [first turing complete general purpose computer](https://en.wikipedia.org/wiki/Analytical_Engine). It is also worth mentioning that in anticipation of this machine, [Augusta Ada King, Countess of Lovelace](https://en.wikipedia.org/wiki/Ada_Lovelace) (commonly known as Ada Lovelace) wrote the first program for the proposed machine, making her the first computer programmer. 

#### Accidentally Redundant
In the process of writing this post, I discovered [an awesome blog post](http://beza1e1.tuxen.de/articles/accidentally_turing_complete.html) with the same title written by [Andreas Zwinkau](http://beza1e1.tuxen.de/) that includes quite a few of the same things and more that I didn't know about. I hope this acknowledgment is enough to justify keeping this post, because I'm pretty excited about it. 

If you find this post interesting I would encourage you to read [Andreas' post](http://beza1e1.tuxen.de/articles/accidentally_turing_complete.html) that predates this one (like the Lambda Calculus predates Turing Machines), where you can also find out why Pokemon Yellow, Super Mario World and MS Powerpoint are also Turing Complete.

#### Academic Integrity Disclaimer
It is also worth noting that throughout this post I play fast and loose with some academic terms that I probably have no right to. When you write to me saying [this](https://news.ycombinator.com/item?id=6578999) I will kindly direct you to this disclaimer. 