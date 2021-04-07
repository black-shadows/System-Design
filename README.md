# System-Design

> Picking the right architecture = Picking the right battles + Managing trade-offs

<p align="center">
  <img src="images/title.png">
</p>

## What are System Design Questions?

In this section, I'll talk about the questions which require the interviewee to design a high-level architecture for some sort of software system. This can be a web-facing service, a RESTful API, a peer-to-peer desktop app, and so on. The exact type of question will most likely vary depending on the specifics of the company you interview at.

## Some Examples

I can give a few examples of such questions:

* Design a URL shortening service like bit.ly.
* How would you implement the Google search?
* Design a client-server application that allows people to play chess with one another.
* How would you store the relations in a social network like Facebook and implement a feature where one user receives notifications when their friends like the same things as they do?

Hopefully, these example questions give you some idea of what I will be talking about. The web is full of many other examples. In addition to that the book [Cracking the Coding Interview](https://github.com/black-shadows/Cracking-the-Coding-Interview) has a small section offering some more such questions.

## Don't Panic

These questions may seem intimidating at first. After all, how does one design Google Search in 20-30 minutes!? It took many smart people several years to do that properly. Don’t worry, no one really expects that from you.

The idea of these questions is to have a discussion about the problem at hand. What’s important for the interviewer is the process, which you use to tackle the problem. The typical outcome of such a discussion is a high-level architecture addressing the goals and constraints in the question. Perhaps the interviewer will choose one or more areas where they will want to discuss bottlenecks and other common problems.

Remember that there is no one right answer. A system can be built in different ways. The important thing is to be able to justify your ideas. This is somewhat different from the algorithm design questions as discussed here at [InterviewBit](https://github.com/black-shadows/InterviewBit-Topicwise-Solutions) and [LeetCode](https://github.com/black-shadows/LeetCode-Topicwise-Solutions).

Finally, keep in mind that the discussion about the same system design problem could go in different directions depending on the goals of the interviewer. They may be willing to see how you create a high-level architecture covering all aspects of the system. Or rather, they could be more interested in looking at a few specific areas and diving deeper into them. In any case, you should have a strategy for how to approach different situations. We will look into such strategies in the next sections.

## Our Approach

Similar to the algorithmic questions, I believe that system design questions require a combination of the right strategy and knowledge. By strategy, I mean a way to approach the problem at an interview. I've seen good candidates fail not because they lack the knowledge but because they cannot focus on the right things while discussing a problem.

Because of that, in the next few sections, I will present our strategy for approaching system design questions at tech interviews. In addition to that, I've collected useful online resources, which will help you update your knowledge of software systems design.

## Quick Overview

Over time, I've identified two major challenges most candidates face when it comes to system design questions. Candidates either:

* Approach questions in a chaotic way and get ratholed, or
* Lack solid understanding of how to properly design architectures that scale.

Fixing these two problems is going to be our focus. By the time you've finished all sections, you'll be exceptionally well-equipped to tackle any system design question.

## The System Design Process

First things first: I'll kick off by replacing chaos with a structured approach to system design. The System Design Process described in the next section takes care of that, as it describes all the steps you need to follow from hearing the problem to declaring it solved.

## Designing Scalable Architectures

With the right process in place, I'll move on to destroying the second obstacle to your dream job. I'll spend a significant amount of time building up your knowledge and intuition around designing scalable architectures.

Scalability is the 4th step of the System Design Process. I am spending a disproportionate amount of time on it simply because this is where candidates struggle the most.

To beef up your scalability knowledge, I've selected some of the best [readings](http://book.mixu.net/distsys/single-page.html) and [videos](https://www.codekarle.com/) available online. They'll teach you the real-life practical underpinnings of designing systems that scale. Examples of some of the Internet's most popular websites: Instagram, TripAdvisor, Salesforce.com, StackOverflow, and many others.

## Step 1: Constraints and Use Cases

Just like algorithm design, system design questions will also most likely be weakly defined. Consider the question about the URL-shortening service ("Design a URL shortening service like bit.ly"). There are so many things that are unclear about it! Without knowing more, it will be impossible to design an appropriate solution. Actually, many candidates forget about this and start designing a solution immediately.

**Don’t make this mistake!**

The very first thing you should do with any system design question is to clarify the system's constraints and to identify what use cases the system needs to satisfy. Spend a few minutes questioning your interviewer and agreeing on the scope of the system. Many of the same rules we follow while building algorithms apply here as well.

Usually, part of what the interviewer wants to see is if you can gather the requirements about the problem at hand, and design a solution that covers them well. Never assume things that were not explicitly stated.

For example, the URL-shortening service could be meant to serve just a few thousand users, but each could be sharing millions of URLs. It could be meant to handle millions of clicks on the shortened URLs or dozens. The service may have to provide extensive statistics about each shortened URL (which will increase your data size), or statistics may not be a requirement at all.

You will also have to think about the use cases that are expected to occur. Your system will be designed based on what it's expected to do. Don't forget to make sure you know all the requirements the interviewer didn't tell you about in the beginning.

## Step 2: Abstract Design

Once you've scoped the system you're about to design, you should continue by outlining a high-level abstract design. The goal of this is to outline all the important components that your architecture will need.

You can tell the interviewer that you would like to do that and draw a simple diagram of your ideas. Sketch your main components and the connections between them. If you do this, very quickly you will be able to get feedback if you are moving in the right direction. Of course, you must be able to justify the high-level design that you just drew.

Don’t get lured to dive deep into some particular aspect of the abstract design. Not yet. Rather, make sure you sketch the important components and the connections between them. Justify your ideas in front of the interviewer and try to address every constraint and use case.

Usually, this sort of high-level design is a combination of well-known techniques, which people have developed. You have to make sure you are familiar with what's out there and feel comfortable using this knowledge. In this section, I will assume that you have enough experience to design such a high-level system. My goal is to focus more on the next steps, where I will talk mainly about scalability and about removing bottlenecks.

If you feel like a complete beginner in system design, perhaps it will be very useful for you to first look at a book on the topic or take advantage of some of the resources I've shared in the sections above.

## Step 3: Understanding Bottlenecks

Most likely your high-level design will have one or more bottlenecks given the constraints of the problem. This is perfectly ok. You are not expected to design a system from the ground up, which immediately handles all the load in the world. It just needs to be scalable, in order for you to be able to improve it using some standard tools and techniques.

Now that you have your high-level design, start thinking about what bottlenecks it has. Perhaps your system needs a load balancer and many machines behind it to handle the user requests. Or maybe the data is so huge that you need to distribute your database on multiple machines. What are some of the downsides that occur from doing that? Is the database too slow and does it need some in-memory caching?

These are just examples of questions that you may have to answer in order to make your solution complete. It may be the case that the interviewer wants to direct the discussion in one particular direction. Then, maybe you won’t need to address all the bottlenecks but rather talk in more depth about one particular area. In any case, you need to be able to identify the weak spots in a system and be able to resolve them.

Remember, usually, each solution is a trade-off of some kind. Changing something will worsen something else. However, the important thing is to be able to talk about these trade-offs and to measure their impact on the system given the constraints and use cases defined.

Once you've outlined the core bottlenecks you see, you can start addressing them in the next step.

## Step 4: Scaling Your Abstract Design

Once you're ready with your high-level design and have made sure that the interviewer is ok with it, you can dive into making it more detailed. Usually, this means making your system scale.

I've devoted the next sections of this discussion to the topic of scalability. I will first cover some theoretical fundamentals and then look at many real-life examples of scalable architectures. Finally, I'll wrap things up with several of the core principles for discussing scalability at interviews.

## Scalability: Fundamentals

Now that you've designed a solid abstract architecture, the next step is to take it to scale. If you've never built a large-scale system, this task may seem a little daunting.

## Where do you start?

There is a common set of scalability principles that you need to know. Knowing what they are, understanding how they are used, and being able to discuss their pros and cons is what scalability at interviews is all about.

How do you build up that intuition?

The first thing I’d recommend you to do is watch this [video](https://www.youtube.com/watch?v=-W9F__D3oY4&ab_channel=JorgeScott).

In it, professor David Malan from Harvard is teaching a huge part of the intuition you will need to have when it comes to scalability. So start here, watch the video and make sure you understand it well.

After watching it, you should have a good fundamental understanding of the following concepts:

* Vertical scaling
* Horizontal scaling
* Caching
* Load balancing
* Database replication
* Database partitioning

Next, I recommend reading this great 4-post “Scalability for Dummies” tutorial ([part-1](https://www.lecloud.net/post/7295452622/scalability-for-dummies-part-1-clones) | [part-2](https://www.lecloud.net/post/7994751381/scalability-for-dummies-part-2-database) | [part-3](https://www.lecloud.net/post/9246290032/scalability-for-dummies-part-3-cache) | [part-4](https://www.lecloud.net/post/9699762917/scalability-for-dummies-part-4-asynchronism)). It reiterates on some of the topics mentioned above, but also introduces several important new concepts:

Using NoSQL instead of scaling a relational database
Being asynchronous
You would also know how to deal with the two major bottlenecks: handling a lot of users and handling a lot of data.

Finally, you may want to read this tutorial on [Database Sharding](http://highscalability.com/blog/2009/8/6/an-unorthodox-approach-to-database-design-the-coming-of-the.html). It's a very common and powerful way of database scaling (as you learned from prof. Malan's lecture).

## Scalability: Examples

The awesome thing about scalability is that it's all around us. If you want to work on an exciting and successful product or service, by definition it's going to have to operate at scale.

Many of the web's largest websites have been very open about how they scale. It's extremely interesting to look "under the hood" of Instagram, Salesforce.com, TripAdvisor, Twitter, Google, and many, many others. That's exactly what we'll be doing in this section.

The goal is to show you how the theoretical principles from the previous section are applied in practice, as well as to introduce you to some of the real-life technologies many companies use nowadays.

## Let's get going!

Here are some real-life architectures I'd recommend you read, analyze and understand:

| Product | Question |
| ---      | ---      | 
| <img src="images/uber.jpeg" width="70" height="50" />  | [How Uber had to scale fast, about breaking your service into many microservices spread across many repos](http://highscalability.com/blog/2016/10/12/lessons-learned-from-scaling-uber-to-2000-engineers-1000-ser.html) |
| <img src="images/facebook.jpeg" width="70" height="50" />| [How Facebook handles 800,000 simultaneous viewers on a live stream](http://highscalability.com/blog/2016/6/27/how-facebook-live-streams-to-800000-simultaneous-viewers.html) | |
| <img src="images/twitter.jpeg" width="70" height="50" />| [How Twitter handles 3,000 image uploads per second and why the old ways it used would not work nowadays](http://highscalability.com/blog/2016/4/20/how-twitter-handles-3000-images-per-second.html) |
| <img src="images/salesforce.jpeg" width="70" height="50" />| [A relatively short example from Salesforce.](http://highscalability.com/blog/2013/9/23/salesforce-architecture-how-they-handle-13-billion-transacti.html) |
| <img src="images/espn.png" width="70" height="50" />| [Another awesome and thorough example, this time from the digital media industry.](http://highscalability.com/blog/2013/11/4/espns-architecture-at-scale-operating-at-100000-duh-nuh-nuhs.html) |
| <img src="images/twitter.jpeg" width="70" height="50" />| Finally, some good example of Twitter subcomponents: [Storing data](http://highscalability.com/blog/2011/12/19/how-twitter-stores-250-million-tweets-a-day-using-mysql.html) and [Timeline](http://highscalability.com/blog/2013/7/8/the-architecture-twitter-uses-to-deal-with-150m-active-users.html) |
| <img src="images/google.png" width="70" height="50" />| [How Google store and manage huge amount of data](http://highscalability.com/google-architecture) |
| <img src="images/youtube.png" width="70" height="50" />| [How YouTube distribute their most popular content and priortize resources](http://highscalability.com/youtube-architecture) |
| <img src="images/stackoverflow.png" width="70" height="50" />| [How Stackoverflow handles 16 million page views and 3 million unique visitors a month](http://highscalability.com/blog/2009/8/5/stack-overflow-architecture.html) |

Don't worry if you don’t understand everything. Many of the posts contain lots of nitty-gritty details which, while priceless to know on your job, are not requirements at interviews. Try to focus on the shared principles used, and keep track of the lessons learned by these folks.

As you read the posts, you'll start noticing common technologies and patterns appear. As you do, make sure you do some research on each frequently seen technology. Try to write down **what problem it solves**, what its alternatives are, and what some common pros and cons may be.

One good way to research the alternatives to technology is to type its name in Google followed by the text " vs ", and see what shows up in the Google Suggest box. For example, if you typed "rabbitmq vs" you'd get entries like "rabbitmq vs activemq", "rabbitmq vs redis", "rabbitmq vs msmq", "rabbitmq vs kafka" - which is a pretty good list to get you started. 

The goal of all this reading (other than having tons of fun) is to develop practical knowledge about what works and what doesn’t work in “the real world”. After reviewing a bunch of these architectures and seeing where they agree or disagree, you’d be very well positioned to move on to the next step.

## Scalability: Warp-up

Alright, at this point you already have a solid theoretical and practical understanding of system design. In this section, I'll wrap things up and put them in the context of technical interviews.

## Everything is a Tradeoff

This is one of the most fundamental concepts in system design.

Hopefully, at this point, this is not a surprise to you. If you've looked at the real-life architectures, you saw that there rarely is one perfect way to do things. Each company ends up with a different architecture. Designing a scalable system is an optimization task: there are tons of constraints (time, budget, knowledge, complexity, technologies currently available, etc.), and you need to build the best thing that fits those constraints. Every technology, every pattern is great for some things, and not so great for others. Understanding these pros and cons, the advantages and disadvantages, is key.

**Remember: there is no one optimal system design.**

Sure, there are best practices you can use. But at the end of the day, it all boils down to balancing between time to market, system complexity, cost of development, cost of maintenance, availability, and many other things.

Being able to understand and discuss these trade-offs is what system design (and thus system design questions) is all about.

In your preparation, don’t try to find silver bullets. Instead, focus on what each scalability pattern is good for, what its shortcomings are, and why people prefer it over other patterns.

## Putting it all together and Staying up to date

At this point, the most useful thing you could do is come up with a one or two-pager that contains the scalability lessons you've learned.

Finally, you'd be well served throughout your professional career to stay up to date on how scalability evolves. For example, 10 years ago there were no Amazon Web Services, and companies were forced to manage their infrastructure in-house. Nowadays, using services like EC2, RDS, S3, Elastic MapReduce, etc. you can build a giant company. So while AWS didn’t change the fundamental scalability principles, it did change the landscape of technologies people need to be familiar with when scaling. Thus, staying up to date is quite important (or else you’d be reinventing the wheel).

## At the Interview

So what should you do at your interview?

First of all, follow the System Design Process. You already know how to apply it. Don't skip steps, don't make assumptions, start broad and go deep when asked.

Second, keep in mind that system design questions serve as an idea exchange platform. Be prepared for discussions about tradeoffs, about pros and cons. Be prepared to give alternatives, to ask questions, to identify and solve bottlenecks, to go broad or deep depending on your interviewer's preferences.

Don't get defensive: whenever your interviewer challenges your architectural choices, acknowledge that rarely an idea is perfect, and outline the advantages and disadvantages of your choice. Be open to new constraints to pop up during the discussion and to adjust your architecture on the fly.

Most of all, have fun. Dreaming up architecture is a very stimulating mental process - enjoy it and stay positive. You're already equipped with the right knowledge, just apply it during your interview and you'll do well.

## How to Practice?

Practicing system design questions is more difficult than practicing algorithm design questions. For algorithm design, there are online judges and courses like the one from [HiredInTech](https://www.hiredintech.com/courses/algorithm-design) that combine problem banks with sample solutions and automated graders that can tell you exactly how good your solution is. This is simply priceless. There is no such thing as system design.

So what do you do?

I have several suggestions in the following lessons in this section.

Also, there are some more useful resources online that you can take a look at:

* [Introduction](https://lethain.com/introduction-to-architecting-systems-for-scale/)
* [Basics of System Design](https://weifoo.gitbooks.io/systemdesign/content/)
* [Concepts You Should Know](https://www.freecodecamp.org/news/systems-design-for-interviews/)
* [Solved Examples of System Design](http://blog.gainlo.co/index.php/category/system-design-interview-questions/)

## Solve with Friends

Look at the massive systems you use every day developed by the companies you are interviewing for. What systems did these companies have to design? Create a list of the fundamental system design questions that bubble up in your brain. Here are a few to get you started:

* Twitter: real-time feed of the tweets by the people you’re following
* Google: instantly returning the pages matching any search query (Search); Storing and serving massive amounts of video data (YouTube); Aggregating the world’s news by topic (Google news)
* Facebook: serving massive amounts of photos

Start by compiling a list of 10 to 20 of these questions. Then, pick one and try to come up with an efficient design. Make sure you follow the process discussed in the previous sections.

Once you’re ready, find a knowledgeable friend or coworker, go to a meeting room and start discussing ideas. It’d be tons of fun and you’ll learn a lot from the process.

Don’t spend hours: initially, limit your time per question to one hour and ultimately try to fit every question in 20 to 30 minutes.

If you can’t find a friend/coworker, go to a site like HighScalability that contains tons of examples of real-life architectures and compare what you conjured up to what these companies actually did. You’d be surprised how many of the top websites’ architectures are widely available. Keep in mind that these systems were designed by multiple people over multiple months, so don’t expect to be able to come up with every low-level decision they made. Focus on the high-level stuff.

## Mock Interviews

While practicing in isolation with a friend is very useful up to a point, at some stage in your preparation process it’d be time to face the music. You need to get actual real-life interview experience under your belt.

Mock interviews are a fantastic way to practice system design questions. System design questions are all about organic discussions around trade-offs. Try to find an unbiased and knowledgeable person, and do several interviews with them. It can be a friend, a colleague, or you could use a paid service.

Paid mock interviews allow you to practice being comfortable discussing ideas with a stranger, working under the stress of time pressure, and guarantee objective feedback. And if the person providing it is skilled at interviewing, you’d get lots of action items and high-quality advice.

If you choose to do it with a friend, make sure they stay impartial and give you honest feedback (friends tend to be too nice to us). The nice thing about doing mock interviews with friends is that they are very generous with their time, so you can do multiple interviews with them at no cost. But make sure you choose a skilled interviewer: there is little value in doing mock interviews with someone who has poor interviewing skills.

Nowadays, is it also possible to do mock interviews with other people online for free? One service that I found useful for this is [Pramp.com](https://www.pramp.com/?utm_source=hiredintech&utm_medium=website-link&utm_campaign=HiredInTech#/) - you could use it for your system design interview preparation.

No matter if you choose paid services or interviewing with friends, mock interviews are going to be highly useful to you when it comes to system design questions. Make sure you do at least a few of those prior to your interview.

## Summary

A strong process is crucial to successfully solve system design questions. I broke it down into four steps:

* **Scope** the problem: Don't make assumptions; ask questions; Understand the constraints and use cases.
* Sketch-up an **abstract design** that illustrates the basic components of the system and the relationships between them.
* Think about the **bottlenecks** these components face when the system scales.
* Address these bottlenecks by using the fundamentals principles of **scalable system design.**

When it comes to system design, it's incredibly useful to review real-life architectures. As you do this, make sure you:

* Pay attention to what technologies are used. Go ahead and research each new technology and see what problem it solves, what its alternatives are, where it excels, and where it fails.
* Take note of the common patterns you see, and how they relate to the scalability theory you learned in the previous section.
* Read through the lessons learned - they are a very quick way to learn from other people's battle scars.

You now know how to approach any system design question. You first build a high-level architecture by identifying the constraints and use cases, sketching up the major components and the relationships between them, and thinking about the system's bottlenecks. You then apply the right scalability patterns that will take care of these bottlenecks in the context of the system's constraints.

We discussed several strategies for practicing system design questions. By combining discussing solutions with friends or coworkers with reading about scalable real-world systems and doing mock interviews, you’d be able to develop strong system design chops.

My recommendation is to start by working on system design questions yourself, then move on to discussing designs with friends, to finally doing mock interviews.

**Good luck and enjoy!**

If you have any doubts regarding system design, feel free to contact me **abhisheksharma.0517@gmail.com**.
