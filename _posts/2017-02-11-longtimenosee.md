---
    layout: post
    category: Personal 
    tagline: "The State of Things"
    title: What a Disagreeable Old Man I Have Become
    tags: [life, haskell, Yelloturë, remodel, Calloléra, Lumna, Calemorrinna, Alassë, Turë, Yara]
    image: /assets/images/jed.jpg
---

A lot has happened in the world of Vanyanan since I last wrote. Calemorrinna is here, and the two households have been joined. My servant Alassë is anything but alassenen. She is faithful as always, and after great difficulty accepted Calemorrinna. But she has not at all accepted Turë or Yara. Despite constant effort, she isn't any closer to accepting. And Turë has had enough...

<!-- more -->

But let's skip the unpleasantness. Life is going on, whether the little ones get along with one another or not. Calemorrinna is driven to turn my dilapidated fortress into a bright and happy home. Turë and Alassë have their own ideas about that, but it is a pleasant change to have a bathroom floor that isn't crumbling and a stone path in the front yard and even a garden. Really, a garden? How is that going to stand up when the time comes to resist the next horde? It's almost as if we hadn't spent the past year with the Calloléra. The followers of Yelloturë are everywhere, and where they are not, there are the devotees of Lumna, and as their pitched battle reached its conclusion, neither was overly pleased with those fighting with the Calloléra. I haven't written since the battle. Yelloturë is now cáno, and everyone tries to pretend this is normal. Well, almost everyone. 

{% include figure.html src="/assets/images/jed.jpg" caption="You know that young doctor I was telling you about, well, he's got an idea he wants to keep me alive!"  %}

Did I become unpleasant again? Sorry. "What a disagreeable old man I have become!" 

We did succeed in putting in new bathroom floor tile, a new toilet, and some decorative wall tile. Calemorrinna did most of the work, though I helped where I could. I helped enough to throw out my back, ruin a pair of pants (they were practically already ruined anyway), and be about the way you expect a lazy computer programmer to be when trying to install subfloor, lay floor tile, grout tile, and so forth. Circular saws and jigsaws and visions of limbs severed at the hightest joint haunt my nightmares now. As if my nightmares weren't bad enough. 

Yelloturë is cáno. I mentioned that, right? 

We all cope with that in our own ways. For my own part, I've started burying myself in my Z-Machine again. I have told you about my Z-Machine, haven't I? I suppose not. Back in the 70s (in the before time, in the long, long ago), a company called Infocom made text adventure games. To be competitive, they need them to run on half a dozen different radically different architectures. They solved the problem then in the same way we solve our (much easier) problem today. Instead of porting their games to a dozen different systems, they defined a specification for a virtual machine, implemented that virtual machine in software for all their target systems, then wrote all their games to target that virtual system. We do it today with Java, they did it forty years ago with the Z-Machine, or "Zork"-Machine, named after their first and most famous game. 

Since then, it has become the de facto standard for modern parser-based Interactive Fiction. Yes, as text adventures have gotten indie, non-commercial, and artistic, we needed a more pretentious name for them. Interactive Fiction, or IF, is the one that stuck. Graham Nelson at Oxford reversed engineered the specification and has written a series of programming languages designed to build new games for the old Z-Machine. There are literally hundreds of Z-Machine implementations out there, for everything from iPhones to Solaris SPARC to JavaScript. So why write one more? 

I wanted something non-trivial to write in Haskell as a way for force myself to learn that opinionated, pretentious, beast of a programming language. I don't even want to try to explain Haskell to non-programmers, but I brought it up so I guess I better try. How about this?

The D.O.D. evaluated Haskell (along with a dozen other languages) for use for internal projects back in the 90s. They gave the same programming problem to a dozen teams, each expert in their own language, to complete, and measured things like, total documentation, number of bugs, total lines of code, and total time to complete the projects. 

Half the teams delivered code that couldn't be compiled. The other teams spent an average of a full work week on the problem, and wrote thousands of lines of code. 

The Haskell team spent 4 hours and wrote 80 lines of code nestled within 400 lines of embedded documentation. At first, the test committee assumed someone had screwed up and mailed in their spec instead of their source code. Once that was cleared up, the test committee believed the results were so outlandish that no one else would be able to duplicate them. Who'da thunk it, some CS super genius had screwed up their carefully controlled study. Alone among the tested projects, the Haskell project had to be reimplemented, from scratch, by a college student who had never heard of Haskell before. So he had to learn the language, with the clock ticking, and implement the project, and no knowledge of the previous iteration.

I did say the other teams, all pros in their languages, need a full work week? 

The college student finished his Haskell reimplementation in 8 hours, in 140 lines of code. 

The test committee still blew it off, and you are wondering why? 

Because Haskell looks...weird. And under the surface of those weird looks is an even weirder conceptual basis. Haskell is a language in which implementing QuickSort is trivially easy, but implementing "Hello World" for the first time is brain-breaking. Every new Haskell programmer has the experience of saying "WTF is the IO Monad and how do I escape?" Those programmers are caught in a demon's cage, and there is no escape except to re-write the program. 

Haskell is a language, the only one I know of, that begins from the idea that all forms of Input and Output are Faustian Bargains out of which no good can ever come. That a program should spend as much of its code as humanly possible innocent of the dark and arcane sorcery that is interacting with anything it can't mathematically prove to be true at compile time. 

In C, you just put "cout << Hello". In Java, you just put "System.out.println(Hello)". 

Only Haskell says that to show "Hello" on the monitor is an act of evil black magic that a good wizard avoids at all cost, because the only way to ever pull it off, the only way any computer can pull it off, is to summon a hideous demon named "State" directly from the bowels of Hell. C, Java, Perl, like teenagers playing with a Ouija board in a Chic-tract, summon the demon thoughtlessly. Haskell knows that only misery can ever ultimately come of it. Cout seems like fun and games, but it always progresses to cin. 

Haskell knows that, at some point, it has to wrestle with this demon. So, when Haskell does so, it surrounds the Unholy State with crucifixes, throws holy water on it, and screams "The power of the IO Monad compels you!" at it over and over again. It's a hard fight, and the demon is kept in his box, but those who did battle with him are forever tainted, and the IO Monad knows, and ensures they can never again touch the pure and faithful. 

Haskell tutorials have you implement lessons from the middle of your college algorithms course before they dare to test you with the horrors of "Hello World." 

So, I'm writing a highly stateful, bit-twiddling 70s era virtual machine on top of it. 

That is how I avoid thinking about Yelloturë. 










