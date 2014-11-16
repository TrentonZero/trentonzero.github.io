---
    layout: post
    category: Personal 
    tagline: "Stay calm, I'm the Doctor"
    title: Welcome to Jekyll
    tags: [blogging, jekyll, discus, wordpress]
    image: /assets/images/jekyll.logo.png
---
{% include JB/setup %}

I am now committed. I've seen enough to let me know that WordPress is out and Jekyll hosted on Github Pages is in. I will be moving my blog from WordPress and over into Jekyll.

I have blogged on five different platforms in my life: static HTML, LiveJournal, a custom CMS written by yours truely on the Google App Engine, WordPress, and now Jekyll. And I have to say that at least so far I feel like Jekyll (along, of course, with Discus for the social functionality) is the best of the bundle, at least for a person of my dispositions and talents. 

<!-- more -->


I will go briefly over the merits of each blogging method: 

* Static HTML/CSS/JS:  What to say beyond the obvious? There is a reason no one but web developers and designers writes HTML by hand anymore. It's too hard to deal with, especially if you want to write compliant HTML that works on a wide variety of devices.  CSS makes life a little better, but the noise to information ratio in HTML is still way, way too high for useful work to be done directly within it.

* LiveJournal: LiveJournal and BlogSpot pioneered the "free, until you want to post a picture." model of doing business. It obviously worked for them, and work for me at the time. I mean, hey, it beat writing HTML by hand. But it suffered one big problem, besides, well, the whole nickle and dime thing over trivial things like posting a photo thing: you had to post online. 

* Custom CMS: I suppose this is where it is when it comes to raw power. Everyone was changable. Everything was exactly how I <strike>wanted it to be</strike> made it. There are some cases, like custom web applications, where that's what you want. But blogging isn't. Blogging is a well-defined problem that has been solved multiple times. There really isn't a whole lot that justifies the time and effort (and security ramifications) of a custom CMS. 

{% include figure.html src="/assets/images/jekyll.logo.png" caption="Where have you been all my life?" align="right" %}

* WordPress: For a long time, I considered WordPress to be the solution par-excellance, and WordPress.com to be a really good free hosting service. Built in community, generous free media hosting, built in SEO. But, a few things rubbed me the wrong way. One, the ads. A few of the ads they chose to show on my page rubbed me the wrong way. What can you do? I mean, it's free, right? And they gotta pay the bills somehow. 


* Jekyll: Jekyll is an odd child in the bunch in lots of ways. It takes a radically different approach to blogging than everything since BlogSpot. From the earliest days of blogging, blogs were seen as problems that required server-side code to support the dynamic blog roll on the index page, comments, and posting access levels. And this meant forcing people to do their writing either inside webpage text boxes or within second rate "blogging clients" rather than, well, text editors. 

 That sounds really little to lots of people out there, but I'm a professional programmer. Like many programmers, I'm picky and opinionated about text editors. I live my professional life inside of three world-class, top-of-the-line text editors. (IntelliJ IDEA, Vim, and Eclipse). I don't want to use some text box wrapper thrown together in ten minutes by some guy in Visual Basic to actually write things.

I'm writing this post, right now, in Vim (cool top-of-the-line editor numero uno.) It's true, I wrote my WordPress blog in Vim as well. But it required a plugin, and while it worked, it wasn't without some really annoying bugs. But Jekyll. Jekyll doesn't care what I write this in. As long as it is saved to a text file in the "_posts" folder and has a file name that starts with a date, it'll be happy.

 You can tell Jekyll was concieved by programmers. Jekyll says, well, hold on a moment. Comments require server-side code, sure. But blogging itself? Not at all. It's really cheating to say that blogs are "dynamic content." The only dynamic things in a blog are the blog roll, the tags, and the categories. And even on an active blog, those change once a day. We'll just generate them (in the background of course), on the writer's machine, for each new post, as static HTML files.

 And we'll use markdown so that people can write their posts almost entirely in plain text and have it come out as pretty HTML in the end, and we'll compile that, in the background of course, on the writer's machine as well. 

And what the hell, let's give the writers a simple web-server that runs just on their machine while they write, so that they can just refresh their browser and see exactly what their entire blog looks like on the internet, including their new post? No need to "publish as draft" (though we'll support that too). Just save the blog post on the local disk, navigate to "http://localhost" and get your entire blog site. 

And (this is where the programmers out there, like me get excited) who needs a clunky web-interface to administer blog content? Blog content is just text files. We'll pair up with Github, and let people administer their blogs via git. And since, from Github's perspective, they are just serving plain old vanilla HTML with no expensive server code, they won't mind serving it for free, no strings attached. And if they ever change their mind, well, the user's will always have both their original text files and the generated static HTML. They can host anywhere. 

This last one is the only thing that really makes Jekyll unsuitable to the wider populace. Even with a graphical-client, I've known professional developers who found git to be a pain-in-the-ass. But, I use git every day at work, so it's no big deal. And for those that don't understand it, the official Github git client and a willingness to get the basic idea is probably sufficient. 






