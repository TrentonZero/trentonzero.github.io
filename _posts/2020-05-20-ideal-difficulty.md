---
published: false
layout: post
tags:
- philosophy
- programming
title: Ideal Difficulty
---
Here's a lesson I learned that I'm not sure all my coworkers in the computer field have caught onto yet: 

> There is an ideal level of complexity for any problem.

And a corollary:

> There is an ideal learning curve for any tool.

You are going to have to stick with me, but I learned this from programming games. Take a Zachlike programming game. The way all Zachlike games work is this: they give you a problem that is trivial to solve with the right resources, then deny you those resources. 

Sometimes, it's limit on line count, sometimes it's a limit concurrency. Sometimes (as in Exa Punks), you have near unlimited concurrency, but not enough registers or tools to really solve concurrency, so you are stuck hacking together convoluted Rube Goldbergesque contraptions. There is an ideal level of complexity for solving parallelized and given just enough tools to hack something together, but not to really solve the problem (and good, because if you had enough tools to solve the general problem, you would solve it and the game would be nothing but copy pasting. 

Or, take the older, preXP RPG Makers. Any random teenager willing to devote the time can create the same generic, early 90s-style JRPGs with RPG Maker. But as soon as they want to do anything else, no matter how trivial, they are swimming upstream. I tried to make a scene, as a teenager, of a room full of characters dancing in pairs, and it took more time and was harder than my "Algorithms and Data Structures" final project. It never really worked. Thinking back, I probably needed to go into the assembly and reverse engineer the order in which the asynchronous events fired on the entities, then find some way to ensure the entities were added in that order. 

It wasn't fun.

There are a lot of libraries that I find are like that. I cringe now everytime I find a page for a library that has a single liner invocation. Any problem so trivial that it can be solved by a single function call usually isn't worth the overhead of a third-party dependency. 

Can you think of a counter-example? Maybe "Google search." Ah, but that's a great example, for a whole host of reasons. First, Google search is almost a command prompt, it takes so many special flags. In a programming API,  




