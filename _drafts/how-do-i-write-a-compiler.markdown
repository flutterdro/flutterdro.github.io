---
layout: post
categories: [Compiler Development]
tags: [compiler, C++]
title: "How do I write a compiler? Part 2: Parsing"
---
Like genuinely. How do you do this? Once again this is not an educational post.
This is an attempt to figure shit out. This is like an exploration diary.
The one you find on a cadaver in the middle of the jungle, whose previous owner
probably died from snakes and spiders crawling up his ass and eating him from the
inside.

## Interlude: Where is Part 1?

Part 1 is about lexing but it is piss easy so I skipped it.
Dunno. Maybe I will write about it someday.

## Prologue

Technically I could pull up bison and simplify the proccess of writing
a parser, but that's not it. When I last used bison, what it provided
diverged quite a lot from my vision. And what is my vision?

Well, let's talk about

### What makes a good compiler?

It is a deep question because different people will say different things.

For example tooling developers would ask for heavily customixable compiler,
the one which provides a lot of flags, allows to dump different representations,
provides time-traces etc.

From the pov of the user the most important things are efficiency of the produced
binary, speed of compilation and quality of the error reporting and warnings.

Actually good compilers will provide all of that and a little more.

### My priorities

Obviously, I am a dogshit programmer, like, bottom of the barrel. No,
I am the mold bellow the bottom of the barrel. So I can't write
something actually good.

Buuuuut, I can try and focus on one specific aspect. And I chose error
reporting. What else did you expect from the c++ programmer? Those cryptic
walls of error messages are killing me. Most of it is my fault for writing
unreadable garbage, still some of it definitelly is not my fault.

I guess this is kind of spiritual rite to calm down my soul.

##



---
[^1]: English. I am using English. Lamao
