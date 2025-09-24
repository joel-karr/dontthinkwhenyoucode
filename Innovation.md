# When to Innovate

<!-- AI:BEGIN:mini-toc -->
## In this chapter
- See @sec-getting-a-new-perspective
- See @sec-using-an-innovation-framework
- See @sec-building-an-innovation-framework
<!-- AI:END:mini-toc -->

<!-- begin chapter id="chp.innovation" -->

Filename: Innovation.md

<!-- begin storymap -->
Why do I want to read this?

: You've built solid task templates for common problems, but you are running into situations where the proven approaches aren't enough. You want to learn how to innovate systematically rather trying different, wild ideas to see if any work.

What will I learn?

: How to create innovative solutions building on your proven foundation. 

What will I be able to do that I couldn't do before?

: You'll be able to approach new challenges with confidence using a structured approach. You will know when it's best to innovate and when it's best to stick to proven solutions.

Where are we going next, and how does this fit in?

: This will conclude the individual mastery section and next you will move to how to work with your team and others.
<!-- end storymap -->

The previous chapters have shown you how to build your core skillset, create predictable task templates, and make solid decisions even in uncertain conditions. What happens when you encounter a business problem that you can't solve?

In movies, the hero might slip, hit their head, and wake up with a genius idea. I wouldn't recommend that approach. Instead, this chapter will show you how to take a systematic approach to innovation—developing new approaches while maintaining focus on the goal. My own turning point came while working to improve the performance of an ecommerce search page. I discovered how using analogies can change your perspective and let you break through tough technical challenges.

## Getting a New Perspective {#sec-getting-a-new-perspective}

<!-- AI:BEGIN:figure-placeholder -->
<!-- Figure placeholder: consider adding an analogy map or PAGES framework visual -->
<!-- AI:END:figure-placeholder -->

Back in 2010, I was working with a experienced database administrator on a complex SQL query for a high-traffic ecommerce site. Tens of thousands of restaurants were on the platform, and daily updates were causing lock waits and unstable performance. We spent months using our standard approaches to improve performance: running frequent maintenance scripts, tuning execution plans, and creating indexes. The core issue was that we had a highly normalized database which meant anytime we returned a collection of restaurants, we had to join over fifteen tables. Updating any restaurant meant potentially locking those tables and quickly creating a backlog of pending search queries.

The database administrator started building views to query against, but we still couldn't reach the target response time. We realized that we would need to find a new approach.

We started playing a game that turned into an excellent catalyst for innovative solutions. A person on our team loved to describe what we were doing by thinking up some wild and crazy analogies. For example, he would turn every component of our solution into different positions on a basketball team, picking famous players based on their attitudes. Or he would explain a feature about referrals as if it was a Tupperware pyramid scheme. The shifts in perspective were exactly what we needed to unlock creative ideas.

We started by defining what success looked like: sub-second response time, ability to filter on twelve different fields, and returning full restaurant objects. Nothing else was off-limits.

After a few attempts at analogies that didn't quite hit the mark, we landed on imagining the search functionality was a popular dating game show from the late 1990s on MTV called *Singled Out*. The show started with 50 contestants all hoping to win a date with the central player called the "Picker". The Picker couldn't see the contestants directly. Instead, each time the Picker stated a preference—like their favorite sport is basketball—contestants who didn't match walked off the stage in single file past the Picker. Round by round, the large group was filtered down to a final few contestants that the Picker would get to see and pick a favorite for a date.

As soon as the Picker would answer a question—like their favorite sport—the contestants who didn't match would start walking out in single file. During a conversation about how the show's host could catch cheating by contestants who try to change their answers to stay in the game, we thought maybe the host already had contestant numbers with their answers to each question on a single card. That way they could quickly see which contestants should remain.

| *Singled Out* Game Show               | Restaurant Search Problem                           |
|---------------------------------------|-----------------------------------------------------|
| Picker chooses preferences            | Customer applies filters (cuisine, rating, etc.)    |
| Contestants eliminated in each round  | Restaurants excluded by each filter condition       |
| Host has quick reference card         | Database uses a flat table of indexed filter fields |
| Remaining contestants = best matches  | Resulting dataset = matching restaurants            |

Our system, built with domain-driven design, always dealt with full restaurant objects as XML. That meant updating restaurants by parsing objects from XML and splitting them into many SQL tables, then reconstructing the same XML again with complex joins for our search. It felt wasteful. In our analogy, that would be like the host having a card with every detail for each contestant. How could they possibly know who was eliminated quickly if the data was only stored on individual cards?

For our restaurant search site, we realized that we already knew the full set of filters including things like cuisine or star rating, so instead of going to different normalized tables, we could have a single flat table with only the items they could filter.

NoSQL databases and Lucene were gaining in popularity at the time, but certainly not widely used enough for us to risk the most critical parts of our system by relying on them.

That's when it clicked. We could have the best of both worlds by building a SQL table that had complex objects flattened into fields that we would use for filters and the full restaurant XML object stored in a column as a large XML string. This allowed us to query a single table and still get back all the data we needed for restaurants that matched the filters.

By using analogies, you can change your perspective to think of new ways to solve technical challenges.

## Using an Innovation Framework {#sec-using-an-innovation-framework}

As a student in the very first iMBA class at the University of Illinois, I was excited to take a course on Innovation with Professors Jeffrey Loewenstein and Jack Goncalo. Like many, I always had been told that creativity or innovation was a skill that people are born with or without.

Their central idea was that creativity isn't a rare gift. It's a process that can be trained like any other skill. When they introduced their research on shifting perspectives, I immediately thought back to the breakthrough we had with the restaurant search site. It turns out that using analogies was the simplest version of what Prof. Loewenstein had formalized into a structured framework.

In his book with Matthew A. Cronin, *The Craft of Creativity*, Prof. Loewenstein described an approach where you first identified each piece of a scenario and then systematically swapped them out to see how it may change your perspective.

His framework is captured by the acronym PAGES:

* Parts: Components or elements involved in the situation
* Actions: Activities or behaviors related to the parts
* Goals: Objectives or outcomes desired from the actions
* Events: Incidents or occurrences that affect the situation
* Self-concept: Identities or roles of the individuals involved

Although designed as a general creativity tool, the framework seems tailor-made for software engineering. We already build systems in ways that group information like this.

Let's see how the PAGES framework might apply to a software engineering challenge.

Take an e-commerce website: search results pages usually show some number of items with pagination or continuous scroll. This setup creates a bias towards items at the top of the page, even if they're not the best fit for the customer. What if we wanted to change this customer experience?

We can start by mapping the current state of each piece:

* Parts: Cards to display each result, pagination, filters, a search bar, API, NoSQL database  

* Actions: Entering a search term, clicking the next page button, applying filters, hovering over items to see more details

* Goals: Helping the user find the best match quickly, minimizing time spent searching, or reducing the number of item detail pages they need to view

* Events: Real-time inventory changes or updates to restaurants that impact displayed result information

* Self-concept: A person looking to find a restaurant

Once we have listed out all our different pieces, we can experiment by swapping them out to see how it changes our perspective.

For example, what if the results page only displayed one item instead of a list?  That might force the users to give more information about what they want instead of scrolling. Changing that part forces us to rethink filtering. Could we use a large language model to guide filtering instead of traditional options with predefined fields? This would make the experience for the user more like a chat where they continue the conversation until they find an option they like.

We may have found a better solution but let’s swap out another item. What if we changed our self-concept to be a salesperson. By showing a single option, we may lose the opportunity to sell multiple restaurants.

Let's try using self-concept to adjust our perspective again. What if we think like a salesperson and we look at this new solution? You may realize that by only showing a single option, you may lose the chance for the user to browse past other things. Let's add a smaller section that has secondary recommendations for the user. The LLM would still drive the results, but now we have the top result and then other recommended results.

Each shift gave us a new perspective and helped us create a new solution.

## Building an Innovation Framework for Software Engineers {#sec-building-an-innovation-framework}

We can take the lessons that we have learned from analogies and the PAGES framework to create a targeted approach for software engineering.

### Step 1: Define the Challenge

Software engineering often involves trade-offs. One fix may solve a problem but create a new one, and teams can lose sight of the original goal. Start off by writing down the specific technical challenge you are looking to solve. Throughout the process, check back with your original challenge to stay on course.

#### Example: Defining a Routing Challenge

Challenge: Route phone calls to an agent queue in under one second based on both department and brand. The system connects to multiple CRMs, each with a 3-5 second response time.

### Step 2: Choose an Existing Task Template

It's easier to start from something proven than from scratch. Pick a task template that can solve at least part of your challenge. If the problem requires multiple task templates, go ahead and include them all.

#### Example: Selecting the Basic API Template

We need to be able to call an API and return the department and the brand. We have a task template that can be a Basic API for a single data source.

Our Basic API task template includes an API that has read and write endpoints for a data source. 

![Task Templates Example](images/task_template_example.pdf)

### Step 3: Identify the Shortfalls

Now list out where the existing task template doesn’t meet your needs. This keeps innovation focused on real gaps rather than reinventing everything.

* Does it meet performance requirements?
* Can it handle the required scale or volume of traffic?
* Does it work across all systems?

#### Example: Spotting Performance Gaps

Our Basic API Template works for one data source, but it can't handle multiple CRMs. Each CRM responds in 3-5 seconds, which is too slow for the under-one second routing goal.

### Example: Using a Cache to Speed Up Routing

This is where innovation begins. Pick one part of your task template and swap it with an alternative. You might change data storage, replace a synchronous call with a cache, or use a different messaging pattern. The goal is to rethink without abandoning proven, reliable tools.

#### Example: Route Phone Calls

Replace the real-time CRM lookup with a cache that stores department and brand data across tenants. This solves the performance issue but introduces the risk of stale data. To fix that, we can add triggers that update the cache in real time whenever a CRM changes.

Checking back to our original goal: we still have fast response times, and we can support multiple CRMs.

### Step 5 (Optional): Use Analogies

If swapping parts don’t help you break through, analogies can shift your perspective. Compare your challenge to something unrelated---games, shows, or real-world systems. Analogies often spark ideas you wouldn’t have considered.

#### Example: Borrowing from Airport Security

In our case, we realized our cache could still lag behind the CRMs. If a department or brand changed but the event didn’t fire quickly enough, we’d risk routing calls to the wrong queue.

We could continue swapping out parts of our task template to see if we could find a solution, but simply having a different data storage type wasn't going to get us to the solution we needed.

At security, each passenger scans their boarding pass. The system checks their airline and terminal, and routes them toward the right gate. This is like our fast initial routing using the cache—most of the time it’s correct, and it keeps traffic flowing.

But sometimes gates change at the last minute. If the airline waited only until check-in to fix this, travelers would miss their flights. Instead, there are monitors past security that display the latest gate info. Passengers are already moving, but they still get an update if something changes.

That sparked an idea: what if we did the same thing? Route the caller instantly using cached data, then re-check the CRM once they’re already in the queue. If the CRM returns new information, we could shift the caller to a different queue before they speak to an agent.

This way, the analogy didn’t just hand us a solution---it helped us troubleshoot. 

Let's check back again with our challenge definition from step 1.

* Our routing is under one second even if it will not always be perfect
* We can support multiple CRMs even if they don't trigger fast enough to always update our cache

### Putting It All Together

This five-step process gives you a practical innovation toolkit:

1. Define the Challenge – Know what you’re solving.

2. Choose a Task Template – Start from something proven.

3. Identify Shortfalls – Focus your innovation where it’s needed.

4. Swap Parts – Rethink components without throwing everything out.

5. Use Analogies – Shift perspectives when you get stuck.

## Up Next: Applying Mastery with AI Code Generation {#sec-up-next-ai}
<!-- AI:BEGIN:end-matter -->
## Exercises
- Apply the PAGES framework to a current project challenge and list 3 potential swaps.
- Prototype one small analogy-driven idea and evaluate its feasibility.

<!-- AI:END:end-matter -->

When new developer tools like AI code generators become widely used, does everything change?

Not really. The same principles to become a great engineer---deliberate practice, using task templates, making instant decisions, and innovating systematically---are exactly what will keep you effective when working with AI-assisted coding. In the next chapter, we'll explore how to apply advancements in developer tools to make writing code faster, but the same proven approach is still vital.










