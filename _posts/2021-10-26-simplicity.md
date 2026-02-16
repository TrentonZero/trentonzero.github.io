---
published: true
layout: post
tags:
- philosophy
- programming
title: Programmer Rant On Complexity
image: /assets/images/simplicity.jpg
---

## Programmer Rant on Complexity

{% include figure.html src="/assets/images/simplicity.jpg" caption="One of these is not like the other..." align="right" %}

A meme on LinkedIn accomplished its mission, if its mission was to "trigger" me. I've attached it here. It's true, but it's a paradoxical truth, and at the risk of pedantry, I want to explore the paradox.

<!-- more -->

Like a lot of paradoxically true things, the paradox is explained by using two definitions of the same word. In this case, the meaning of complexity changes as you move from the left side of the graph to the right.

On the left side, "simple" means "with few parts." And sure enough, beginner code has few parts: it is one gigantic procedure manipulating a mass of highly-entwined global state.

In the middle, OOP and design patterns come in as a way to manage all the entwining, but the engineer thinks they are making things more complex. There are more "things" to think about. They create objects and interfaces, almost at random, because their guiding principle is now a dual mandate: balance entwined global state with "simplicity" (meaning having few parts.) This is "encapsulation."

At the right-side of the graph, they have realized that complexity actually means "entwined," and that simple code is not the code with the fewest parts, but code with the *least entwined* parts. Techniques from functional programming that seemed eccentric are now seen as essential to good code. The design patterns make sense.

Getters and Setters, those obscenities of Java best practice, actually make sense (and the cargo cult around them becomes infuriating for a very, very different reason.)

With this later, more sophisticated definition of "complexity," the beginners code was the most complex of all. Half a century software engineering wisdom, all the best practices and all the disciplines and paradigms, are created to try to coerce the "simplicity" of beginner code (which was also the "simplicity" of FORTRAN) into truly simple code.

