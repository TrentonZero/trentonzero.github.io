---
published: true
layout: post
title: A Mythical Man Month Corollary Conversation
tags:
- programming
---(A conversation that happened with another developer. Lightly edited to protect the innocent. Also, there may be typos and grammatical errors, since it is copied pretty directly from an IM thread.)

K: I can sit here and think that 100 man developer teams have as their sole advantage over 5 man developer teams that they build systems that can only be maintained by a 100 man developer team…but I have no proof of that, and we already have such a system, so what can I do?

(I really do think that…it can’t be accurate at the limits, but it's marginally true at some wide range that the only thing long-term gained by adding a developer is that they will help you produce the same system that only an n+1 developer team can maintain.)

A lot of successful businesses disagree with me, so maybe I’m wrong…but it feels true. Throw 5 devs at a problem and they will solve it perfectly well with a system that can be maintained by 5 devs. Throw 100 devs at the same problem, and they will solve it just about as well (probably worse) with a system that only 100 developers could maintain.

<!-- more -->

C: “…Sole advatnage over 5 man developer teams…” advantage here is sarcastic in light of your last message?

K: Well, it's an advantage if you are the other 95 devs. :)

C: Ah, yeah.

K: (And it's not an elitist thing. I’m assuming pick any 5, as long as they are broadly competent.)

C: That’s thought provoking. Hadn’t put much thought into it.

K: Isn’t that a large part of the point of the Mythical Man Month?

C: Seems like it’s a natural corollary: More people past a point increases the communication factor to the point that no net speed is gained. Mm… More people past a point increases the communication factor by such a degree that no net speed is gained. (Just rephrased it)

K: And you solve that by…building systems that simplify the communication network.

C: Right, which can only be maintained by 100 developer teams.

K: Yeah

C: Because the complexity has to go somewhere. You haven’t gotten rid of it, really. You’ve streamlined operating with 100 man teams.

K: The 5 man team would have built a monolith.

C: Interesting. Functional or actual? You can partition the problem sensibly, similar to what our last whiteboarding session suggested. It’s going to get treated as a monolith, but kinda has pieces.

K: Actually, though you bring up a good point. I’m getting at something but I’m fuzzy on it. The 100 person team divides up into 20 5-man teams and each builds a component that is a black box to everyone else, and has its own complexity (its own database, its own protocols, its own coding structure). So a single 5 man team trying to wrap their heads around the system have to deal with 20 databases, 20 coding styles, maybe 20 different languages.

C: Potentially 40ish: Usually you have a primary one and then some scriptwork for deployment.

K: But, of course, the 5 man team would break the monolith up into components, but components they can understand. That are organized into a holistic whole. The 100 man team, to solve the communication complexity problem, shifts it into the infrastructure of the system, which allows them to work, but also makes a system that only a 100 man team could maintain. Now, here’s the rub. What if you have a ~100 man team…but they didn’t build a 100 man system. They took architectures from Netflix, Google, Amazon for granted as “best practice” and built a system for a 10,000 man team.

C: Oh, yeah.

K: And then you are a 5 man team trying to interact with it…

