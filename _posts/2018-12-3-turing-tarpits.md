---
layout: post
title: "Turing Tarpits"
abstract: "Beware of the Turing tar-pit in which everything is possible but nothing of interest is easy.      -Alan Perlis in Epigrams on Programming"
tags: Turing Turing-Machine Lambda-Calculus esolangs Turing-Tarpit Combinatory-Logic
---
As a follow-up to the post about [the unexpectedly Turing Complete](/2018/11/30/accidentally-turing-complete.html), I thought I would take a moment to shine a little pessimism on things.

Turing Completeness is incredibly powerful. Staggeringly and beautifully so. But simply being Turing Complete does not necessarily make a thing useful. In fact often these systems are inaccessible almost to the point of uselessness, at least to humans.

The term often associated with this type of system is *Turing Tarpit*. While often applied to [esoteric programming languages](https://en.wikipedia.org/wiki/Esoteric_programming_language) that are designed to be interesting in their minimalism or intentional difficulty it can also be used to describe other systems that are Turing Complete but inaccessible for for useful work. These might be systems that are proven to be Turing Complete because they are academically interesting or possibly a part of some of other problem or proof.

In this post I am going to highlight some things that are pretty useless aside from the fact that they can compute almost everything. Maybe you know a person like that.

#### Esoteric Programming Languages
While the world of esoteric programming languages is surprisingly vast, I thought I would pick out a few examples that I think are particularly interesting or ridiculous.

**INTERCAL** is the abbreviation for 'Compiler Language With No Pronounceable Acronym' which is often considered the earliest example of an esolang, dating back to 1972. It was designed by Don Woods and James M. Lyon as a parody of popular languages of the time like FORTRAN, COBOL, and Assembly.

As interesting as the language itself is the [manual](https://www.muppetlabs.com/~breadbox/intercal-man/s01.html) which reads like a Douglas Adams novel. Here is an excerpt under the heading 'Uses for INTERCAL':

>INTERCAL's main advantage over other programming languages is its strict simplicity. It has few capabilities, and thus there are few restrictions to be kept in mind. Since it is an exceedingly easy language to learn, one might expect it would be a good language for initiating novice programmers. Perhaps surprising, than, is the fact that it would be more likely to initiate a novice into a search for another line of work. 

My favorite part of the language itself is the required 'PLEASE' command. If isn't used often enough in a program it will be rejected by the compiler as *impolite*. Conversely, if it's used too often it will be rejected as *overly polite*.

**brainfuck** Is probably the most widely known esolang, partly due to its memorable name.

The language uses the concept of 'tape' as memory, much like a Turing Machine. Cells are incremented and and decremented according to the program. When the program halts, the result is whatever remains on the tape. The entirety of the language is as follows:

| Command | Description |
|---------|-------------|
|>|Move the pointer to the right|
|<|Move the pointer to the left|
|+|Increment the cell under the pointer|
|-|Decrement the cell under the pointer|
|.|Output the character at the pointer|
|,|Input a character and store it at the pointer|
|[|Jump past the matching ] if the pointer cell is 0|
|]|Jump back to the matching [ if the pointer cell is nonzero|

While brainfuck is difficult to use, to the point that you may as well use assembly, I think it also has a certain beauty that may not be appropriately conveyed by its name. This may come from it's similarity to [P′′](https://en.wikipedia.org/wiki/P%E2%80%B2%E2%80%B2) which is a language created 30 years earlier by [Corrado Böhm](https://en.wikipedia.org/wiki/Corrado_B%C3%B6hm). It's unclear if this similarity was intentional or not.

Here is the shortest known 'hello world' program in brainfuck:

`+[-->-[>>+>-----<<]<--<---]>-.>>>+.>>..+++[.>]<<<<.+++.------.<<-.>>>>+.`

Just as Abraham was the father of many nations, so is brainfuck the progenitor of many difficult and offensively named languages. Here is a sample of the brainfuck family tree:

* RUM stands for "bRainfUck iMproved." and adds procedures, strings and repetition.
* FukYorBrane and BF Joust pit two Brainfuck-like programs against each other, as in Core War (see Redcode).
* Smallfuck operates only on bits and has no input- or output-commands.
* Puzzlang turns every program into an exercise in patience and logic puzzle skills. The lone X operator becomes any of brainfuck's instructions, depending on the surrounding characters.
* Alarm Clock Radio - throws away the instructions to decrement the memory pointer or memory value.
* Portal and Portal 2 - allows code-level pointer manipulation and theoretically implements the Wang-B Machine.

**Whitespace** is a language written in entirely whitespace characters, meaning spaces, tabs and linefeeds. As a result, all whitespace code is invisible. The sneaky thing about Whitespace is that it can be secretly tucked away in some interesting places, for example, inside a program in any language that ignores whitespace characters. It's a stack based language (possibly) similar to [Forth](https://en.wikipedia.org/wiki/Forth_(programming_language)) and (probably) pretty inaccessible.

**Unlambda** is the esolang on this list that I am the most excited about. It is also the first functional esolang. It's based on combinatory logic and closely related to the Lambda Calculus. It uses prefix notation and is parentheses free, for all of the Lisp haters. Most of the instructions are single letters that represent Lambda Combinators.

So if you are someone who isn't satisfied until you have found the most difficult way to get something done and you like Functional programming, Unlambda might be the language you have been looking for. 

#### Other Tarpits

**Turing Machines** should easily qualify as Turing Tarpits, even if the idea is a little bit recursive. They are both simple and extremely difficult to use for any type of complicated computational tasks. And while they are primarily of academic value, there are some interesting things that can be done with Turing Machines. A fun one (depending on your idea of fun) is the [Busy Beaver Game](https://en.wikipedia.org/wiki/Busy_beaver).

The point of the Busy Beaver Game is to make the binary Turing Machine that prints the most 1's before halting. It is important that the machine halts because making a Turing Machine that spits out 1's forever is trivial. The machines only compete against other machines that have the same number of states. For example, a two state machine that could print 4 ones would beat a two state machine that could only print 3.

Here are some of the record holders:

| states | # of 1's | # of Steps |
|--------|----------|------------|
| 1 | 1 | 1 |
| 2 | 4 | 6 |
| 3 | 6 | 14 |
| 4 | 13 | 107 |
| 5 | 4098 | 47,176,870 |
| 6 | ≈3.515 × 10^18267 | ≈7.412 × 10^36534 |

**The Lambda Calculus** is one of the quintessential examples of a simple system that is computationally complete. Even though it feels strange to call something that predates Turing Machines a Turing Tarpit, it fits every bit as well as any other example. Possibly more so considering it's purely abstract and not bound to any concept of state or mechanism.

The Lambda Calculus is essentially a framework for combining simple functions. Each function takes one argument and returns one value. These functions can then be passed into other functions as arguments and expressions can be built up. And that is all you get. No numbers, no operators, no loops. If you want them, you have to make them. To see this witchcraft at work, watch [this enlightening video](https://www.youtube.com/watch?v=3VQ382QG-y4).

For some fun Lambda Calculus puzzles, read [To Mock a Mockingbird](http://www.enthusiasticallyconfused.com/Mathematics/Riddles%20%26%20Puzzles/Raymond%20Smullyan/To%20Mock%20a%20Mocking%20Bird%20-%20Smullyan.pdf)

#### Conclusion

Turing Tarpit is a fun, snarky name for things that may not be *immediately* useful, but I think it's worth noting that Computer Science itself is built out of things that are difficult at their atomic level. It's only after layers of abstraction are built up that they become useful. But the those layers are tailored with specific purposes in mind and the utility that is gained comes at the cost of flexibility. Even some of these extreme or ridiculous examples can serve to remind us that the shape of things as we know them is not the only shape they can be. Incremental utility doesn't need to be the only guiding tenant of Computer Science. That sometimes its useful to step back and look at the infinite possibilities instead of what is immediately useful. 