---
layout: post
title: Should everyone learn to code?
date: 2014-07-13 09:21:45.000000000 -05:00
tags:
- programming
published: true
---

A notion that seems to be gaining steam lately is the idea that "everyone should learn to code." The advantages are legion and (to us coders) obvious:

<!-- more -->

- Coding enhances critical thinking and problem solving skills. A lot of what goes on when programming can really be boiled down to one fact: (very nearly) every problem can be broken down into smaller, easier to solve problems. And this fact applies recursively. If you drill down far enough, massively complex problems really just come down to a whole lot of really trivial problems.
- Industry needs coders.
- Computers are instrumental to the functioning of our world, and coding is the best way to understand computers, and therefore, our modern world.
- Coding offers a domain of creativity and self-fulfillment.

Nonetheless, I'm not overly enthused with this notion. Let's start by modifying that sentence to something I can agree with, then we will look at the difference between the two statements. Let's change it from "everyone should learn to code" to "everyone interested in coding or serious about entering a scientific or technical field should learn to code." Interested in coding, or curious about coding? Check it out. All of the above advantages are true, including the touchy feely one about creativity and self-fulfillment. Not interested in coding, but serious about entering a scientific or technical field? Learn to code anyway, because so much of your work is going to involve number crunching that being able to get up under the hood of that beefed up calculator you have sitting on your desk will benefit you. I mean, Mathematica rocks, but there's going to be some problem in your field that is trivial to implement in code for someone with the domain knowledge to solve it, and us pros will charge you an arm and a leg if you leave it to us to put it in code for you.

But everyone? I guess that sounds uncontroversial enough, but let's expand it out to its full implications. Let's rephrase it: "everyone, regardless of interest, aptitude, or desire, should be forced to learn fundamental programming." Now, this basic formula "everyone should be forced, even against their will, to learn X" is not invalid. We apply it with no controversy to the "three Rs" (reading, writing, and arithmetic.) Don't like math (and plenty don't)? Fellow mathephobes will sympathize, but only starting around algebra. But arithmetic? Even the mathephobes say "Too bad, do your homework." You simply cannot function in modern society if you can't perform the four basic arithmetical operations with something approaching competency. Ditto for reading and writing in the local language. That's one end of the spectrum.

As you move across the spectrum, you encounter the other subjects of a typical contemporary education: history, literature, civics, science, mathematics (beyond arithmetic), a foreign or classical language, and art. The question becomes, where does "coding" sit on the spectrum? I think the answer is "right next to 'shop'." In other words, right at the end, a subject to be studied by those interested (or obliged by other interests) but otherwise to be left alone. That's a pretty controversial statement right now (especially coming from a programmer), so let me justify it.

First, a word to other programmers. I am speakig to you based on an assumption, namely that the reason you are a programmer today is because you like computers, then one day you tried out this programming thing, wrote "Hello World," realized endless possibilities, and starting soaking up programming knowledge with joy and personal zeal. In other words, you are passionate about it. Those of you that entered the field because you were clueless and figured it was a good way to make money, I don't know you. Nothing wrong with making money, but I don't know you.

For the programmers, driven to program by zeal and passion: other people are not like you. Even if we live in corporate drone land where programming consists of slapping together a VB form as quickly and joylessly as possible, we remember that shining moment when the machine was a bottomless well of possibility and imagination. When we learned about Turing Completeness later in college, we realized we knew it all along in our hearts. Where am I going with this? We knew what this machine could do and it inspired us and made us feel empowered, so when our first artistic vision was finished and we hit "compile" and the compiler spewed 587 lines that looked like this:

error: (Each undeclared identifier is reported only once for each function it appears in) (Main.cpp:455)

We powered through it and figured out that this was just GCC's quirky way of telling us that we mispelled a word, and that it even told us what line it happened on. And we fixed those 587 errors, in the process learning that sometimes GCC seemed to lie about what line had the problem. But, we got through it. We ran the compiler again to see our artistic vision come to life, and realized that now it found 1,542 errors that it couldn't find the first time. And now they say things like:

Undefined first referenced  
symbol in file  
main /usr/local/lib/gcc-lib/sparc-sun-solaris2.7/2.95.2/crt1.o  
ld: fatal: Symbol referencing errors. No output written to a.out

This time, no helpful file and line number. It mentions a file, but it's not one of our code files at all. It's a ".o" file, but we are writing .cpp and .h files! For that matter, even though all the words make sense, they don't point the new coder to anything to do about it. And, after digging for awhile, and that while might be a few minutes or might be a few hours, we realized that this (probably) was really just another way of telling us that we mispelled a word. And the blasphemous thought occurs to us, "Why can't it just say that?"

We fix those errors, and this time, we hit compile and, low and behold, the program runs. Our artistic vision has come to life. Except, it didn't. In fact, though the program is running, it doesn't actually do what we expected it to do in any of a hundred different ways. And then, while we are still running it and trying to bask in the glory of having at least a running program, we see this:

fatal signal: Segmentation fault

And the program just stops, and you look-up that message and find out that, somehow or other, your artistic vision tried access a location in memory that didn't really exist, or it didn't have permission to access, or it used to be able to access, but it told the operating system it didn't need it anymore, but it turned out it did need it, but it was too late, or you tried to load a value into a buffer that was larger than its initialized size, or, jumping way out into wonderland, maybe a cosmic ray just happened to hit your RAM chip at that moment and corrupt that exact location in memory. It's a one in a trillion shot, but hey, the code is perfect. After all, the compiler said it had no errors, and we just spent a week trying to appease that bitch-goddess, so surely that means it's pure as fresh snow.

I'll stop there. Nonprogrammers think that is just being unskilled at a new task. They are growing pains that will be gotten over, probably after the first few weeks. We programmers know that what has just been described is, in actual point of fact, "programming." Programming is:

1. Coming up with a brilliant plan
2. Typing it into a text editor/IDE, in the process realizing "all" the places your brilliant plan fell short in detail or flat out contradicted itself. All is in quotes, because as we will discover later, you didn't realize "all" the places.
3. Compiling it.
4. Fixing all the errors.
5. Compiling it again.
6. Fixing that batch of errors.
7. Compiling it.
8. Running it.
9. Realizing it doesn't do what its supposed to do in some way that matters.
10. Fixing that.
11. Compiling it.
12. Realizing your last fix introduced another error.
13. Fixing that.
14. GOTO step 7 until (in the professional world) the product is declared obsolete by management or (in the hobby world) the programmer becomes interested in something else.
15. The program is absolutely perfect. (Note, this step generates a compiler warning, because it is unreachable.)

Now, let's get back to the ordinary people we want to inflict programming on. Ordinary people are:

- Cool with step one, until they realize that their "brilliant plan" is nowhere near sufficiently detailed to base an implementation upon and is almost certainly internally inconsistent. In fact, their brilliant plan tends to be "it'll be totally awesome and do everything!"
- Really annoyed at step 2.
- Really, really annoyed at step 4
- Getting pissed around step 6.
- Want to throw the keyboard against the wall at step 9.
- Really do throw the keyboard against the wall at step 12.
- Start to cry at step 14.
- And despair that it feels like they will never reach step 15 (because they won't.)

But, this is what we do, every day, nine to five. We spend the bulk of our time on steps 7-14, which are actually the most annoying steps for most people. My wife, who knows a few programming languages at a basic level, always runs out of steam around either step 9 or step 12.

Programming is fundamentally unlike other arts and crafts. In art, if the brush stroke is a quarter inch too far to the left, then the painting has a technical imperfection, but it can still be striking. You can say, "Well, I'm no Rembrandt, but this painting of an Amazon war goddess in a chainmail bikini is rather striking, if I do say so myself." If a carpentar drives a nail a quarter inch too far to the right, then its a little off center, but the building will keep standing and he goes on to the next stud. He probably doesn't even notice he drove the nail a quarter inch off center. If he did, and pointed it out to his foreman, and suggested that it be withdrawn and driven correctly, he would be fired.

But if a programmer accesses a memory location so much as one bit too far to the right or left, only God knows what will happen. Maybe nothing. Maybe suddenly the mouse pointer will disappear as we overwrite the portion of memory that contains its graphic. Maybe the "File" text on the menu bar will change to "?Fil". Most likely, the entire program will die suddenly, no matter what is going on, and tell the user:

fatal signal: Segmentation fault

As if there is anything the user can do about that now, other than weep and rage over his now forever lost work.
