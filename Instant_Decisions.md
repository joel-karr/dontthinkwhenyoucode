# Think Clearly Using Mental Models

Filename: Instant_Decisions.md

<!-- begin chapter id="chp.mental_models" -->

<!-- begin storymap -->
Why do I want to read this?

: You feel overwhelmed by the number of decisions required for even simple features and want to understand how senior engineers seem to move through complex problems with confidence.

What will I learn

: How mental models make repeated decisions easier, why experts read code by patterns rather than line-by-line, how decision frameworks eliminate analysis paralysis, and how to build your personal decision matrices.

What will I be able to do that I couldn't do before?

: You'll navigate large codebases quickly by recognizing architectural patterns, make architectural decisions by relying on frameworks, and reduce the cognitive overhead of routine technical choices.

Where are we going next, and how does this fit in?

: Mental models help you think better individually, but complex systems require visual communication. Next, you'll learn diagramming techniques that make complex designs clear to both you and your team.
<!-- end storymap -->

<!-- begin sect1 -->

<!-- AI:BEGIN:mini-toc -->
## In this chapter
- See @sec-applying-mental-models
- See @sec-phd-student-turned-poker-player
- See @sec-overcoming-decision-roadblocks
<!-- AI:END:mini-toc -->

Task templates reduce the number of small decisions that you face when building software. But even with task templates, software engineering is still full of judgement calls. Early in your career, the challenge is finding any possible way to build a feature. As you progress, the challenge shifts to choosing the best approach from multiple viable options. 

That's where mental models come in. In this chapter, we'll explore how to build and apply mental models so you can recognize patterns, navigate large code bases and make confident decisions without feeling overwhelmed.

## Applying Mental Models to Reduce Decisions {#sec-applying-mental-models}

<!-- AI:BEGIN:figure-placeholder -->
<!-- Figure placeholder: consider adding a diagram showing decision flow or a mental model map -->
<!-- AI:END:figure-placeholder -->

One of the most impressive software engineers I have ever worked with was ready to give up. He had just moved onto a less experienced team working in a codebase that was over 15 years old. A patchwork of different approaches and frameworks. We needed him to deliver quickly, but the sheer size and disorganization of the system made it feel impossible.

I walked past his desk and saw a small group huddled around his computer including our director of software engineering. The whole group was in "violent agreement" that the only option was to rewrite the code from scratch, but there wasn't enough time. I could feel the tension. 

They were certain that it would be faster to rewrite because it was going to take weeks just to understand the current code base. The conversation quickly turned to how long it took to read thousands of lines of code. Everyone knew what the ideal code should look like, but the leap between the current code and what they knew was best was far too large. 

Without much thought, I said, "Don't use your eyes to see code."

It sounded crazy or maybe some sort of deep insight. But I was suggesting something simple. We can let our subconscious skim through hundreds of lines of code only trying to identify patterns.  Then we can use those patterns to apply our existing mental models to make decisions. The issue wasn't that they didn't have knowledge or understanding, it was that they didn't know how to make decisions easily.

The team then started looking through code only for things that didn't fit the patterns they expected. The code started to tell a story that was far more than just what the code did. The different patterns and standards made it clear that parts had been written during different time periods. Some had been partially refactored while others remained almost as mini time capsules. Having this awareness allowed the team to group areas of the system and understand not only what they did, but how they could be changed.  

From there, the team looked at the task templates and thought about how they could deliver the same functionality, but with less modern frameworks. Instead of using Azure Cognitive Search, they could use SQL queries with proper database indexes for performance. They didn't need to rebuild the entire front end in React, the existing Classic ASP pages could be adjusted. Aligning the code bases with their mental models allowed them to quickly evaluate decisions and focus on what drove business value.

The shift to pattern recognition gave the team a way forward, but it also highlights something even bigger. There is far more to software than writing code. Success relies on the ability to make constant decisions under uncertainty. That same type of challenge shows up in many different domains. There are surprising similarities between building software and the game of poker. One of the most exciting professional poker players turned her experience playing poker into research on how people can make decisions better.
<!-- end sect1 -->

<!-- begin sect1 -->

## PhD Student Turned Poker Player {#sec-phd-student-turned-poker-player}

In the early 2000s, poker exploded in popularity after an amateur player named Chris Moneymaker --- yes, that's his real name --- won the World Series of Poker. College dorm rooms everywhere turned into late-night poker parlors. While most players were chasing luck, one professional player named Annie Duke stood out because she was studying the game, not just playing it.

Duke was a PhD student studying cognitive psychology when some early success in poker changed her life. Most players were focused on finding someone's "tell," a physical habit or expression that would let them know they were bluffing. The idea was amplified by the movie *Rounders* (1998) where Matt Damon plays a law student who outwits his opponent by noticing his habit of twisting open Oreo cookies while playing. The real world is far less obvious. Duke wasn't searching for some magical tell, she was analyzing how they made decisions.

Poker requires high pressure decision making with far from complete information. A player could calculate the probabilities that their opponents have a better hand based on the limited amount of known cards.  The game itself is far more complex than just doing math. Removing emotions from decision making is crucial. A great player needs to be able to make decisions under uncertainty and not tie future decisions to the outcome.

After winning over $4 million, Duke left poker in 2012 to return to her research on decision making. The strategies she has developed apply extremely well to software engineering. One of the core principles she discusses is that often people are able to go through a process of sorting potential decisions into ones they think will work and ones that will not. It's the next step where they go wrong. We want to believe that we are able to always take two decisions and pick the better one. We spend hours trying to build some matrix to objectively evaluate our options.

Duke says we shouldn't waste time and instead pick one. She calls this the "menu strategy". She relates it to when you have already done the hard part of picking a restaurant, but then you want to agonize over two options on the menu. Instead, you should just pick one without over thinking it. Duke also focuses on how we should not tie our decisions to results. We should hold ourselves accountable to the decisions we make with the given context, but not the specific result. There are many times that we hesitate to make decisions because we are afraid that someone will blame a negative result on us. What is important is that we make good decisions based on the information we have at the time, and as information changes, we adjust.

The same approaches can be applied to decision making in high-stakes poker, the general business world, or software engineering.
<!-- end sect1 -->

<!-- begin sect1 -->

## Overcoming Decision Roadblocks {#sec-overcoming-decision-roadblocks}

We have all been there. We worry about what our teammates will think about our decisions. We worry that the business leaders will think our estimates take too long. We worry the requirements are going to change and we won't be able to adjust. Instead of thinking about how to build a solution, we are stuck worrying. As we learned from Annie Duke, we often don't stall because we don't know ways to solve the problem. We fear the outcome of choosing between the options we know would work.

A major reason we get stuck is because we don't trust our subconscious. It becomes too large a burden for our conscious mind to analyze all our options. Our survival instincts are designed to avoid conscious decisions. It’s slow. We aren't wired to make deliberate decisions all day long. We are made to identify patterns and react in ways that we have done before.

This is the same mechanism that magicians rely on to fool us. When a magician sets up a trick by repeating the same movements multiple times, it's hard for us to keep focusing on it. Our subconscious tells us what will happen next so we can use our energy on other things. It's in the moment that our brains assume the outcome that the opportunity arises for the magician to trick us. We don't notice the trick because we are careless or not smart enough. We miss it because our brains are efficient, applying patterns to what they expect will happen.

The true problem here is that we haven't properly trained our subconscious to make decisions. Often the results of decisions don't become apparent for weeks or months after you made them. By that time, numerous other variables have distorted the connection between the original decision and the outcome. A feature may not have been successful because the market shifted, or because it didn't have proper training and change management. We are constantly trying to determine new approaches without ever knowing if we made a good decision previously.

To recognize patterns and make solid decisions fast, we need to be proactive.  Just like how we trained our skills and built out task templates to common approaches and reliable estimates, we need to train our subconscious to make decisions we can trust.
<!-- end sect1 -->

<!-- begin sect1 -->

## Building Your Mental Models {#sec-building-your-mental-models}

It's time for you to train your subconscious to make decisions. This will feel exhausting at first. Start small, just like we did with our deliberate practice exercises in Chapter 2.

<!-- begin sect2 -->

### Step 1: Start a Decision Journal

Add a section to your notebook for decisions.  When you find yourself making a technical choice, write it down.
Include any information that influenced your decision. Don't overthink it. We will come back to these later.

Examples:

- *Question:* Should I add this endpoint to an existing API or create a new API?
  
  *Context:* Existing system using domain driven design. Endpoint will have abnormally high traffic. It's part of the business-critical workflow.
  
  *Decision:* Create a new API.
- *Question:* Is it better to store this as relational data in SQL or a non-relational database like Azure Cosmos?
  
  *Context:* The data will only be accessed by ID. There is nested data that is optional. A deadline is fast approaching.
  
  *Decision:* Use Azure Cosmos.
<!-- end sect2 -->

<!-- begin sect2 -->

### Step 2: Revisit Your Decisions

Set aside time away from pressure or distractions to review. Pick one decision and start with the context. Explore what information you had and how that influenced your decision.

What context didn't you write down? Was there someone else on the team that spoke up first and you followed their lead? How big of a risk was the decision based on the unknowns?

Instead of focusing on the result, determine if you made the right decision based on the information available. If you think you did, write down how you measured success.  If not, what would you do differently next time?
<!-- end sect2 -->

<!-- begin sect2 -->

### Step 3: Get Outside Input

You can now speak to the context of the decision and how that led to your choice. Find a peer or a mentor and ask them if they can walk through it with you. They may have a different perspective that led them to a different decision. Or they may have used different contexts to arrive at the same decision.

Discuss which items had the biggest impact on the overall decision. This is about learning how you want to think about decisions.
<!-- end sect2 -->

<!-- begin sect2 -->

### Step 4: Create Decision Frameworks

Here is where you get to create a cheat sheet for your subconscious. Take the decisions you have made and identify the most important pieces of context. Ask yourself if you can make a rule to almost always apply that decision. 

Examples:

- *Question:* Should I add this endpoint to an existing API or create a new API?
  
  *Rule:* If an endpoint is expected to have a much different amount of traffic than existing endpoints, it should be a new API.
  
  *Rule:* If using domain driven design, find the closest related objects and consider adding existing endpoint to that API.
- *Question:* Is it better to store this as relational data in SQL or a non-relational database like Azure Cosmos?
  
  *Rule:* If only getting by ID, use a non-relational database.
  
  *Rule:* If needing to do counts or aggregates, use a relational database.
<!-- end sect2 -->

<!-- begin sect2 -->

### Step 5: Practice Pattern Recognition

As you build your decision frameworks, look for patterns that help you identify the context quickly. Spend some time skimming unfamiliar code. Don't try to understand every line. Look for patterns that you can categorize and use to make decisions.

Now look for patterns outside the code. Are there types of requests that are always under time pressure? Is there a way to identify which requests value reliability over performance?

The goal is to recognize these patterns and be able to map them to your context. Think of these as input to your subconscious rule engine. That's exactly why we're training it: so those patterns can pop into view before you even realize you're seeing them.
<!-- end sect2 -->

<!-- begin sect2 -->

### Step 6: Make Continuous Improvements

Next time you come to a decision point, apply your framework first. Consider if there are any obvious reasons why you shouldn't use that decision. Instead of trying to pick between a few different options, if your decision framework gives you a viable solution, go with it.

After a few weeks, review how your decision framework performed. Would you make the same decision now given the same information you had available at the time? If not, then adjust your decision framework rules. Be careful not to make your rules too complex. If you feel yourself adding too many If/Else clauses, you may need to take a step back and see if you can simplify your framework.
<!-- end sect2 -->
<!-- end sect1 -->
<!-- start sect1 -->

## Next: Innovation

We've focused on training your mind to recognize patterns and apply proven solutions. That's powerful when you're facing familiar problems. But what happens when the challenge isn't choosing between known options, it's finding an approach when no clear option exists? Just as mental models help us make decisions with confidence, we can also use structured frameworks to create new ideas. In the next chapter, we'll explore how to systematically think in new and creative ways.
<!-- end chapter -->

<!-- AI:BEGIN:end-matter -->
## Exercises
- Start a decision journal and capture 5 decisions this week, noting context and outcome.
- Create one simple decision framework for a recurring choice in your work.

<!-- AI:END:end-matter -->


