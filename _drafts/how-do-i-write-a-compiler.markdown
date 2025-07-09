---
layout: post
categories: [Compiler Development]
tags: [compiler, C++]
title: "I decided to waste my time"
---
Its been quite a while, eh? I decided to make this blog
more of an actual dev blog. So instead of posting only
when I come up with something cool or abhorent, I will post
more regular thoughts.

## What I've been up to?

tldr; I've ditched emulators for a while to write a compiler.
Moreover I want to do everything from frontend to backend on my own.
No bison/flex, no llvm. Not because I dislike the tools but just
for the bragging rights. You know I am a c++ programmer, right? I would
sacrifice my firstborn if it gave me one more thing to be a snob about.

But in reality, I think it will make for a better learning experience.
Since I was kicked out of the uni like a pathetic failure I am, I have to
grasp at straws.

Turns out it was a very presumptious idea. And I already spent nearly a year
on the frontend alone.

Turns out that designing a compiler to be actually useful is hard,
even for a dirt simple language like pascal.
Who would have thought?

While my fight against the design of the compiler reached an
impasse, I decided to write a post, where I try to convince myself
that my design makes sense. Soooooo.

## AST design

At the core of my ast design is one class

```cpp
template<typename AstElementT>
class handle {
    //some methods
private:
    std::unique_ptr<AstElementT> m_data;
}
```
Well, duh. Of course it is. AST is a tree structure. And you need
handle-like thing whether it is a simple pointer or some abstraction
above pointer like `unique_ptr`.

But my handle is _special_. Not good kind of special. But the kind
I am.

### _Special_

There are 2 things that seperates my `handle` from a
regular pointer-y thing.

First, invalid state is called poisoned and is constructed from
the `poison_pill`. Not much of a difference to be honest,
potato potato.

Second, it is not dereferenceable. You can't access underlying data
not via `operator*()` nor via some kind of `get()` function.



---
[^1]: English. I am using English. Lamao
