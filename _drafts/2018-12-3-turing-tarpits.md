---
layout: post
title: "Turing Tarpits"
abstract: "Beware of the Turing tar-pit in which everything is possible but nothing of interest is easy. -Alan Perlis in Epigrams on Programming"
tags: Turing Turing-Machine 
---
As a follow-up to the post about the unexpectedly Turing Complete, I thought I would take a moment to shine a little pessimism on things.

Turing Completeness is incredibly powerful. Staggeringly and beautifully so. But simply being Turing Complete does not necessarily make a thing useful. In fact often these systems are inaccessible almost to the point of uselessness, at least to humans.

The term often associated with this type of system is *Turing Tarpit*. While often applied to [esoteric programming languages](https://en.wikipedia.org/wiki/Esoteric_programming_language) that are designed to be interesting in their minimalism or intentional difficulty it can also be used to describe systems that are Turing Complete but inaccessible for for useful work. These might be systems that are proven to be Turing Complete because they are academically interesting or possibly a part of some of other problem or proof. For some examples of Turing Tarpits, see the post mentioned above.

In this post I am going to highlight some things that are pretty useless aside from the fact that they can compute almost everything. Maybe you know a person like that.

#### Esoteric Programming Languages
While the world of esoteric programming languages is surprisingly vast, I thought I would pick out a few examples that I thing are particularly interesting or ridiculous.

**INTERCAL** is the abbreviation for 'Compiler Language With No Pronounceable Acronym' which is the earliest example of an esolang, dating back to 1972. It was designed by Don Woods and James M. Lyon as a parody of popular languages of the time like Fortan, COBOL, and Assembly.

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

Just as Abraham was the father of many nations, so is brainfuck the progenitor of many difficult and offensivly named languages. Here is a sample of the brainfuck family tree:

* RUM stands for "bRainfUck iMproved." and adds procedures, strings and repetition.
* FukYorBrane and BF Joust pit two Brainfuck-like programs against each other, as in Core War (see Redcode).
* Smallfuck operates only on bits and has no input- or output-commands.
* Puzzlang turns every program into an exercise in patience and logic puzzle skills. The lone X operator becomes any of brainfuck's instructions, depending on the surrounding characters.
* Alarm Clock Radio - throws away the instructions to decrement the memory pointer or memory value.
* Portal and Portal 2 - allows code-level pointer manipulation and theoretically implements the Wang-B Machine.

**Whitespace**

**Unlambda** is the esolang on this list that I am the most excited about. It is also the first functional esolang. It's based on combinatory logic and closely related to the Lambda Calculus. It uses prefix notation and is parentheses free. Most of the instructions are single letters that represent Lambda Combinators. 

**A programming language is a formal language, which comprises a set of instructions used to produce various kinds of output.** quine

Turing Tarpit is a fun, snarky name for systems that are not immediately useful, But I think it's worth noting that Computer Science is largly made of systems that are equally difficult that have been organized into primatives which are used to build abstractions that are useful for some purpose. 