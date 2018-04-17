---                                                 
    layout: post                                    
    category: Personal                              
    tagline: "Software should be habitable"
    title: Patterns of Software                                 
    tags: [great books, programming, architecture, lisp, business]   
---

What does it mean to live in a home that is both practical and beautiful? What does it mean to work in an office that is practical and beautiful?

What about software? 

<!-- more -->

[Patterns of Software]() by Richard Gabriel is the only programming book I've ever read for which the first hundred or so pages are entirely, 100% about architecture. Not software architecture, but rather old fashioned stone-and-mortar architecture. Software scarcely comes up in the first hundred pages, but instead we are reading about experimental housing projects in Mexico and a curious fascination with Turkish rugs.

In Gabriel's view, we developers live in the software we maintain. This is a metaphor for the more prosaic statement that 90% of the cost of a software project is in the maintenance, but with a shift in focus that reveals something a little less obvious. We software engineers know that we spend most of our time maintaining software. We also know, from painful experience, what it is like to work with maintainable code, and what it is like to work with unmaintainable code.

Gabriel uses the work of Christopher Alexander to show that we can also have some pretty wrong ideas about what makes for maintainable code versus unmaintainable code. There is a strong temptation to think that the key to maintainability is a perfect formal design. We *know* that maintainable code has no code duplication. After all, if there is code duplication, then a thing is implemented twice, and some later developer will come along and change one instance without knowing that they need to change the other. Eventually, the two bits of code that are intended to do the same thing will do things radically different. We also *know* that the answer to this is usually abstraction. 

Patterns of Software attacks these things we know, and the idea of living in the code is essential to understanding it's point. Code should be habitable, the way a good office or a home is habitable. This isn't an invitation to turn our code into a work of artistic self-indulgence. It's not to say that our code is a form of self-expression.

What makes an office "habitable"? What makes it a great working environment? Well, one answer is, deduplication of functions isn't it. If you need a stapler, the right stapler is the one on your desk, not the one stapler for the building. There's one standard: from the perspective of the programmer, which tool is close at hand? That doesn't seem very controversial, but it has some less obvious effects. What if you discover that two libraries, maintained by your team, share some functionality? There is a thread of wisdom that says "Make a third library that refactors out that common functionality." Sometimes that's the right answer. Maybe it's better to duplicate the code of the common structure than to add the organizational complexity of an extra project with its own version control and release cycle in order to eliminate that duplication. 

Here's another one, a bit more insidious. Let's return to the office metaphor and to the stapler. Everyone gets a stapler on their desk. But in order to keep things simple, everyone gets the same model of stapler. That's better, but not ideal. The programmers roll their eyes and throw the useless piece of junk in the empty file cabinet by their desk, because what barbarian uses paper in this day and age. Marketing is annoyed at how heavy the thing is and wish they just had paper clips. Documentation is frustrated because it isn't heavy enough and can't handle bundles of more than thirty pages.  

