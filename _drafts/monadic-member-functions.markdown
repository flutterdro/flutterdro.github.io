---
layout: post
categories: [C++]
tags: [C++, functional programming]
title: "A wee bit of dissapointment in monadic operations for optional"
---

About a month ago I picked up haskell and it was insanely fun.
It taught me a ton of new concepts and gave me a bunch of ideas.

One of those ideas are monads, but todays post is not about them,
at least I will try to act like it is not, I don't want to turn this
post into one of the thousands of generic "Understanding monads" or whatevs.

Also I want to keep this post short for a change.

## Prelude: std::optional<T>

This one is pretty cool. Even before I was enlighten by my brethern
from functional cult, I saw heaps of value in this container or wrapper
or however you call it.

It allows for a value to be in an empty state. So you can do stuff like this

```cpp
struct table {
  auto safe_access(int index)
    -> std::optional<int> {
    if (index < nums.size() and index >= 0) {
      return nums[index];
    } else {
      return std::nullopt;
    }
  }
  std::array<int, 4> nums{1,2,3,4}
}
// and then
auto func() {
  auto nums = table();
  auto num = nums.safe_access(5);
  if (num.has_value()) {
    // do something
  }
}
```

Some of you my say: "Da hell? Why not use pointer/iterator for this?". And
I can say that you could but this one has an advantage. It is a value type.
It fully owns the data it wraps, `std::optional<int>` doesn't depend on the
original `int` it was constructed from unlike `int*`.

Isn't convincing? I don't care. I am not here to advertise it. It was just a
small introduction. Let's get to the brunt of the issue.

## So called "monadic operations"

I promissed that I would not mention monads in this post, but that's
how they are called in cppreference.

There are 3 of them: `.transform()`, `.and_then()`, `.or_else()`.



