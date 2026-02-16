---
layout: post
title: Musing on technical interviews
date: 2014-06-28 20:07:48.000000000 -05:00
tags:
- programming
- work
published: true
---

I've actually had some experience now on both sides of the interviewing fence. Since my rehire back at the UCCE place, I've been one of the lead people in conducting the interviews.

<!-- more -->

At first, I took technical skills for granted, and thought the point was to evaluate for personality fit with the company. But I slowly came to realize that, actually, most people brought in had zero aptitude. Indeed, so few people that interview actually have any aptitude for the job that the chief problem was not "finding talented people who are a good fit for the team." It's "finding competent people with a pulse" and convincing the business side that "competent" was not something to be compromised on.

Is person X's personality a fit for the team? Hell if I know, no one is themselves in an interview anyway! Can person X write a half-decent atoi function if asked and given a computer and a compiler? That's easy, it's objective, and it's empirical. It's also a bar sufficiently high that it eliminates most candidates. Sufficiently many candidates that the business worried it was too hard.

Now, I want to emphasis my interviews were not hard. I set the bar as low as I could and still feel like I was hiring people that crossed the threshold to mere competence.

There were no trick questions. You know the type, the riddles with the different setup each time but the common thread that they require the person to have an AHA moment and perform a counter-intuitive step. Usually they involve a bizarre assortment of characters trying to cross a river. Yeah, none of that nonsense.

No real trivia questions, unless you count asking a person the meaning of "O(n^2)" a trivia question. And no, I don't. A no, that one wasn't a deal breaker either, but it's nice to know that the person interviewing for the job has at least a vague knowledge of computer science proper. A person that knows the meaning O(n^2) remembers the simplest part of his/her algorithms class. Good to know, especially since my next question involves the difference between a LinkedList and an array, and its a much more practical, real-world sort of question. And without fail, the people that know O(n^2) get it right every single time, and the people that don't get it wrong. None the less, still not a deal breaker, but disconcerting because it highly implies (and experience has borne this out) that the developer is, to use the words of Joel Spolsky, "programming by superstition." They don't really know what the commands they are typing and doing, and they are just stringing them together.

And truthfully, all that is moot if the person does a bang-up job (or, inversely, totally washes out) on the last question: write the atoi function. (Or, Integer.parseInt in Java.) It's my favorite interview question ever because:

- 
No formal computer science training required. I already established whether you remembered any formal computer science, see above. Now, I want to know if you can at least code. It's basic testing: test one thing at a time, to the greatest degree possible. And let's be frank, I'll take a person that can code but doesn't know theory before I'll take a person that knows theory but can't program.

- 
No tricks, no counter-intuitive AHA-moment leaps required. They are fun, but don't have anything to do with whether or not a person can write software. This problem is as straight-forward as can be. A complete layman can understand the problem and probably explain at a high-level the solution, once they understand the distinction between "10" as a pair of characters and 10 as an integer. And while laymen don't need to know that, a working programmer damn well better know it.

- 
It is not a hard problem, but it is harder than it looks. What about negative numbers? What about ghibberish? What about "13-213"? The characters are all, taken individually valid, but the context of the negative is wrong. What about buffer overflow? This is good because most real world problems are harder than they look. How does an otherwise bright person (and anyone that makes it this far is in the top 10% of people we brought in) handle the fact that the problem is harder than they originally thought it was? This is the only place where I gave in to the urge to play a mind game. It is a red flag if a person rolls their eyes when they find out that their program returns incorrect data for "123-321", instead of throwing an error, or that it throws the incorrect error when a buffer overflow occurs. (And if you are wondering, I let people solve this on a real computer, in an IDE.)

It also provides opportunities for some of my favorite candidate red-flags, such as:

- 
"Are sure this is Java? This seems like C." This can be translated as "I expect that every single problem I will ever be faced with will have already been solved by the standard library, and I will be utterly helpless if I ever face a problem that isn't."

- 
"I would always just call Integer.parseInt / atoi / whatever." Now, saying this once is fine, because in reality, anybody that decides in production code to write their own 'better' version of atoi is, well, dumb. But if they insist on it after I explain that, this is an interview, it's just a simple question to evaluate their skills as a developer, and that of course in production code we would just call the standard library, well, that's a bad sign.

- 
"That's a training issue." This is usually a response to the failure of their method to handle "123-321" or a buffer overflow correctly. Umm, no, it's not a training issue.
