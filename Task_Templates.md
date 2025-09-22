# Be Predictable with Task Templates

Filename: Task_Templates.md

<!-- begin chapter id="chp.task_templates" -->

<!-- begin storymap -->
Why do I want to read this?

: You're tired of every project feeling like you're starting from scratch, with endless debates about implementation details and constantly changing requirements that derail development momentum.

What will I learn?

: How to create task templates, why predictability (not cleverness) is the real goal of great engineering.

What will I be able to do that I couldn't do before?

: You'll build your own collection of task templates for common engineering challenges.

Where are we going next, and how does this fit in?

: Task templates are just the beginning—you need deeper mental models for decision-making.
<!-- end storymap -->

<!-- begin sect1 -->
The previous chapter showed you how deliberate practice builds the skills you need to enter a flow state. But skill alone isn't enough when working inside a complex system under tight deadlines. Even the most talented engineers can find themselves overwhelmed. You need to have predictable execution, with the ability to move quickly without getting caught rethinking every decision. 

There's a saying in software engineering. A junior software engineer knows one way to solve a problem. A mid-level engineer knows many ways. An expert knows which one to use. Mastery isn't about collecting every skill possible like they are Pokémon cards, it's about instantly choosing the right approach for the moment and executing without hesitation.

In this chapter, we’ll explore a practical tool that builds on your strengths and makes your work predictable: task templates. They turn repeated decisions into reusable collections, so you can save your mental energy for the real problems that matter.

<!-- begin sect1 -->

## Six Months to Finish a 10-Month Project

Predictability is a competitive advantage. It lets teams focus on building quality applications instead of constantly worrying about unknowns, risks, and immovable timelines. I learned this firsthand in a project where the original estimate was ten months, but we had only six before the deadline.

Sitting in a small conference room, I listened as a team of top software consultants walked through the remaining work left on a very large project. The company had signed a multi-million dollar statement of work with this firm to deliver a product expected to generate major revenue in the first year. For the first few minutes, it was the usual consultant talk about cutting-edge tech stacks, new frameworks, and ability to hyper scale. But then I heard something that made me sit up straight. When they totaled up all the estimates, the product wouldn't be ready for another ten months. That was a problem. The U.S. Securities and Exchange Commission (SEC) had regulations taking effect in just six months. If the product wasn't ready, we would lose all the revenue.

As they walked through the timeline, it echoed my experience in the cloud room at a previous company. As I described in the previous chapter, we tried to build our first cloud-based, scalable system using untested technology---and our estimates quickly collapsed from all the unknowns.

I left the room with my mind racing. Could we reduce scope? Could we change the approach? I couldn't call the SEC and ask for an extension. I needed a plan, and I needed it fast.

I kept coming back to one thing. Most of the time was allocated to researching and testing new ideas. What if we focused on our strengths and only used approaches that we knew would work? I pulled in a close friend and colleague who’d been in the cloud room with me and had fought through the same challenges with new tech and too many unknowns. We spent the next few hours breaking down the solution into known approaches.

We ended up with a detailed list of tasks that we were confident could deliver the business value our customers were expecting after six months. Hitting that deadline meant protecting the millions in revenue our company had already committed to investors. Over the next few months, anytime that scope changed, we checked to see if the change added new tasks. If it did, then we knew that we had to find ways to pick up the extra tasks without extending our timeline.

We were successful not because we worked long hours or drastically cut scope. Our success came from limiting unknowns and sticking to a detailed plan everyone understood.

Instead of researching new technologies under deadline pressure, we identified patterns we'd used successfully before. Instead of debating architectural approaches for each component, we applied the proven structure everywhere. The plan the consultants had created for their own estimates required learning and building simultaneously. We separated those activities. We learned during planning, then executed during building.

This is what I now call task templates---pre-built approaches for common problems that eliminate repeated decision-making.

Most teams treat every feature like it's never been done before. They debate the same architectural decisions repeatedly, research the same technology trade-offs, and reinvent solutions to problems they've solved before.

Great engineers work differently. They document past approaches, task templates, that turn complex decisions into predictable execution.

A key skill is recognizing patterns. Many features are variations of the same building blocks: reading and writing data, applying business logic, and triggering events. If you have built strong task templates for each, you can use them to deliver countless different features.

Often we know we should stick to well proven approaches, but the pressure to deliver faster tempts us into trying something new. Software engineers are constantly required to make decisions under pressure with incomplete information. Research has shown that teams who can resist this urge and maintain predictable approaches are more successful. 

<!-- end sect1 -->

<!-- begin sect1 -->

## Predictable Teams Move Faster

Let's look at a field outside of software where predictability can mean the difference between life and death: firefighting.

Firefighters operate in extreme conditions where they are unsure how far a fire has spread or what parts of the structure have been compromised. They can't afford to stop and debate the best approach. They need to act quickly and reliably so that everyone around them can do the same. 

The National Institute for Occupational Health and Safety has repeatedly found that when predictability breaks down through unclear roles, inadequate procedures, or poor communication, the results can be fatal.

That's why fire departments train relentlessly. They separate practice from execution. In training, they explore new or innovative approaches. On an actual response call, they rely on predefined playbooks. This lets them operate at an extremely high level of efficiency. Training turns their actions into instinct, and since each firefighter acts predictably, their teammates can make fast, confident decisions too.

When the alarm sounds, everyone knows their role. The first engine company handles initial attack and rescue. The second engine company establishes water supply. The first ladder company handles ventilation and search operations. Predictability is what allows them to coordinate, even when conditions are chaotic and pressure is high.

The same principles apply to software teams. When someone working on a backend API can confidently say when it will be ready, someone working on a frontend task can decide whether to mock out objects or wait to integrate. When scope changes, everyone on the team can understand how it will impact their own tasks.

Many engineers resist this kind of structure. It can feel like unnecessary red tape. People don't want to plan out tasks when they could already be writing code. Leaders don't push for planning to make slide decks look good in board meetings. They do it because the entire company is more successful when all teams know what to expect and can plan accordingly.

The fire department figured out that even though chaos feels urgent, predictable execution saves lives. Software teams need to apply the same lesson: systematic approaches enable speed under pressure. It's time invested that lets you work with confidence.

We know that predictability makes teams move fast, but the biggest obstacle is our temptation to reinvent instead of reusing what already works.
<!-- end sect1 -->

<!-- begin sect1 -->

## The Innovation Trap

Software engineers often believe they need to find a new solution to demonstrate their skills. They look for different ways to build things, even when a simple, proven approach already works.

This obsession with innovation often backfires. Engineers end up debating architecture for each new product request. Teams spend more time researching and refactoring than building. They abandon working solutions because they think they're boring, not because they're broken. 

The irony of the situation is that true engineering value doesn't come from inventing new approaches. It comes enabling business to solve real world problems by solving complex real-world scenarios with well known patterns.

I learned this lesson through a computer science course on AI several years ago. The final project for the course was to create a bot that would play [The Prisoner's Dilemma](https://en.wikipedia.org/wiki/Prisoner's_dilemma) against our classmates' bots.

The rules of the game were simple. Two criminals were arrested and held separately. Each one could either stay silent or betray the other. If they both stayed silent, they would each get a one-year prison sentence. If one confessed and the other didn't, the person who confesses goes free and the other gets 5 years. If both confess, they each get 3 years.

For our class tournament, bots played 10,000 rounds against each opponent. After each round, your bot learned what the other bot had done. The bot with the lowest total number of years sentenced won. The professor had offered up the prize of an automatic A for whoever could build the best bot.

The game itself was far from new. Robert Axelrod had started a famous international tournament for the game in 1980. Each year people would submit complex strategies from around the world but the same simple strategy always won. The strategy was called "Tit for Tat" and had just two rules: cooperate on the first move, then copy whatever your opponent did on the previous move. That was it.

Not only was I a full-time student getting a Master's degree, but I was working full time for a company about to launch a new product. We were way behind on the product so I was spending every hour I could getting it ready for a convention in Las Vegas. I was writing code all the way up until the time the doors opened and people started coming to our booth. After 3 days of demos, I hadn't even started creating the bot and only had 48 hours left until the deadline.

On the plane ride home, I started the project but didn't have time to develop an elegant strategy. The professor had told us about how the same simple strategy had always won Axelrod's tournament, but that couldn't be the answer, could it?

Poor time management worked to my advantage. I couldn't waste time trying to outwit my classmates, so I built a simple bot with one slight adjustment. The professor had shown us four slight variations of the Tit for Tat strategy. I created a bot that would try each of those for 100 rounds each. After 400 rounds, whichever bot had performed the best, I would use for the remaining rounds against that opponent.

And to my surprise, the bot built on decades of proven approaches won the tournament. This demonstrates how often proven strategies outperform clever but untested ideas. Great engineers build on known approaches, and that's exactly where task templates come in.
<!-- end sect1 -->

<!-- begin sect1 -->

## Introducing Task Templates

Task templates can be a secret weapon for great engineers. They allow you take complex product requirements and turn them into actionable tasks that can be executed with confidence.

One of the most stressful conversations any software engineer can have is when a product manager asks for an estimate. They always give plenty of caveats about how they won't hold us to the timelines. We know that the reason they are asking is because they need to give an estimate to their boss, who needs to give an estimate to their boss, who needs to give an estimate to the CEO. And so we scramble to come up with a number that is both realistic yet doesn't make us look incompetent.

There are tons of frameworks and different approaches to estimating such as story points, t-shirt sizes, and even the Fibonacci sequence. But in reality, no one cares about how many story points a team completes—they care about the cost of a feature and when it will be ready to deliver value.

The industry has fostered a culture where engineers feel unpredictability is acceptable, even though predictability is essential for a successful business.

Strong business leaders can navigate any scenario, except uncertainty. Tell them a solution needs three months, they can plan an interim manual process. But if you tell them that you don't know how long it will take, they risk spending too much time or money on a temporary solution.

I got into long discussions (arguments) with my colleagues as many of them had been burned by scope changing or dependencies on third party vendors. The process changes they proposed focused on protecting the software team from the risks of shifting requirements. But if you do not allow scope to change during a sprint, you risk spending time building the wrong thing. And if you force software engineers to agonize over every decision, you slow down the development process.

There are always things that we can't predict or control. What if we focus on what we can control? If you ask a software engineer how long they take to build a CRUD API for an object, they will likely throw out some number that is padded for unknowns. But if you actually track how long it takes for that specific task repeatedly, not only do they get much better at estimating it, but will become more efficient.

The key is to be able to group tasks together into components so that you don't have to debate every minor change in scope. Instead of only how long a product request will take, you can discuss what components you are going to build and how that creates the product feature. If the scope change requires you to build something that wasn't included in your task templates for that feature, then you can discuss whether it's worth adjusting the timeline.
<!-- end sect1 -->

<!-- begin sect1 -->

## Building Task Templates {#sec.buildtasktemplates}

Task templates are pre-defined collections of software tasks that represent decisions your team has already made around technical standards. They eliminate the need to re-debate architectural choices for common scenarios and enable reliable estimates. A good task template captures enough information that anyone reading it can understand the actions to take and the decisions have already been made. Task templates are living documents. Update them only when new information proves a better approach, not just because someone has a new preference.

Keep them somewhere visible and accessible such as a team wiki or knowledge base. Most templates are kept short and use bullet points so that they are easily consumable. Think of them as your playbook. 

![Task Templates Example](images/task_template_example.pdf)

<!-- begin sect2 -->

### Step 1: Build Your Template Library

Document the tasks you need to build things using your team's standards.

<!-- begin sect3 -->

#### Example: CRUD API Template

*Template Name:* Standard CRUD API for DOMAIN_ENTITY with Event Sourcing

*Technology Stack:* ASP.NET Core, Dapr, MediatR, Entity Framework

*Development Tasks:*

- Create domain entity classes
- Set up Entity Framework DbContext and configure entity mappings
- Implement command/query handlers
- Create a REST API controller 
- Set up Request/Response DTOs and AutoMapper profiles for data mapping
- Add FluentValidation rules
- Configure JWT Bearer authentication and authorization policies

<!-- end sect3 -->

<!-- begin sect3 -->

#### Example: Background Job Template

*Template Name:* Background Job

*Technology Stack:* Azure Function, Dapr, MediatR

*Development Tasks:*

- Create .NET Worker Service project with dependency injection configuration
- Set up hosted service class
- Implement command handlers with business logic and error handling
- Configure Polly retry policies and circuit breaker patterns
- Add structured logging with correlation IDs
- Handle dead letter queue scenarios with retry logic
<!-- end sect3 -->
<!-- end sect2 -->
<!-- begin sect2 -->

### Step 2: Discuss with Your Team

Now that you have created a draft template, share it with your team members for feedback. Set the ground rules: the goal is to agree on repeatable steps that best fit your team's skills and business needs. Keep the discussion focused by asking questions like, "Would we be able to deliver this approach under pressure from deadlines?" or "How does this improve our ability to deliver business value?" Once the team has come to a consensus, you should all agree not to revisit the selections unless new information is introduced.

#### Example: Discussion on CRUD API

You: "Here's the draft CRUD API task template. It lists setting up the classes, wiring up Entity Framework, adding CQRS handlers and creating an API controller."

Teammate A: "Should we look at using GraphQL endpoints? That makes it far more flexible."

You: "You could be right. What are the most important principals for our company and how would that increase the business value?"

Teammate B: "Right now reliability is critical. GraphQL may add complexity that we may not need."

You: "I agree. Let's stick with REST endpoints and revisit it if the business needs change"

Teammate A: "Ok. Can we note that we should always have HTTPS only set for security reasons?"

You: "Great idea. Let's add that. Now that we are all aligned, we can add this task template to our team task template collection"

<!-- end sect2 -->
<!-- begin sect2 -->

### Step 3: Practice Your Templates to Accurately Record Times

You can't estimate what you haven't actually measured. Run through each template on its own and time yourself to get a real baseline.

The first time you may find yourself stopping if you are unsure about a specific task. That's okay. It's a great opportunity to add that to your practice notebook. The goal here is only to get a baseline for how long a task template takes you to complete, not get a high score.

#### Example: CRUD API Template Practice

- Attempt 1: 12 hours
- Attempt 2: 8 hours
- Attempt 3: 7.5 hours

Final time used for estimates = 8 hours

<!-- end sect2 -->

<!-- end sect1 -->

<!-- begin sect1 -->

## Up Next: From Task Templates to Decision-Making

Now that you know how to use task templates to bring structure and predictability to your work, the next step is building better decision-making tools. In the next chapter, we'll look at how to develop personal mental models that help you identify patterns, apply decisions, and lead more strategic conversations with your team and leadership. 

<!-- end sect1 -->

<!-- end chapter -->

