---
title: Introduction to TDD
---

[TDD](https://en.wikipedia.org/wiki/Test-driven_development) stands for Test-Driven Development and is a discipline
where the primary idea is to write tests before writing any production code.

This might seem weird at first. It did to me too. But after playing around a bit with Puppet module testing, I am, as
it seems, infinitely intrigued by the concept.

On a quest to discover more, I came across this video: [The Three Laws of TDD](https://youtu.be/AoIfc5NwRks).

It is done by a TDD-enthusiast [Uncle Bob](https://en.wikipedia.org/wiki/Robert_Cecil_Martin) in which he introduces
the concept of TDD, explains why it could be beneficial, gives an example of usage, and then answers some questions.

So, summing up the main points, here are the

##### Three Laws of TDD
1. You are not allowed to write any production code unless it is to make a failing unit test pass.
1. You are not allowed to write any more of a unit test than is sufficient to fail; and compilation failures are
failures.
1. You are now allowed to write any more production code than is sufficient to pass the one failing unit test.

This actually got me thinking about how do you ever pass the tests that fail to compile. Am I misunderstanding the
concept? Because once your test fails to compile, you're not allowed to continue writing it. And you can never write
production code that will make the test pass because the test doesn't compile. Is this some kind of a "ideal gas"
situation where we're describing the concept that is impossible to achieve?

Anyways, the other important part of the video, as I said, was

##### The Benefits of TDD
* You're going to spend a lot less time debugging the code. You might even go as far as to forget some of those **Step
Over**, **Step Into**, and **Step Out** keyboard shortcuts. But code is code - sometimes you'll have to polish up
those rusty skills and get down to the gritty bits.
* You're going to be documenting the code as you write the tests. All those objects that you can create, the parameters
you pass them, the functions you can call on them - all of this will end up in your test suite. And those snippets of
code will be available to you and everybody else who uses the code. And you also create a set of documentation that
is written in a completely unambiguous language of Code.
* You write code that is easier to test. This one's easy. As long as you write the test first, the code will always be
easily testable.
* Starting with TDD is a lot more rewarding than supporting an existing codebase with tests. You constantly "fix
mistakes". It fails, then it passes. Shabang! Rewarding (-
* And, most importantly, **if your test suite has been produced by TDD then when it passes, you can be sure you're
ready to deploy**.

These all sound like bald promises and they are. Whether the benefits are worthy of rewriting the legacy infrastructure
(more on that is in the question section) is up to you.

I'll definitely get back to the concept and the discipline of TDD, and the way I  use it to write infrastructure code.
For now you can check out a couple of my tiny Puppet modules, that I tried to apply the TDD principle to:
* [puppet-cron](https://github.com/pegasd/puppet-cron)
* [puppet-incron](https://github.com/pegasd/puppet-incron)

Any thoughts on TDD are welcome. I'd love to hear more from those who are a lot more familiar with the concept than I
am.

Peace! ✌🏼
