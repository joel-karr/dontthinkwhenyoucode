# Think Together

Filename: Think_Together.md

<!-- begin chapter id="chp.think_together.md" -->

<!-- begin storymap -->
Why do I want to read this?

: You struggle to organize complex architectures in your head and communicate system designs clearly to others. You want to focus on specific areas of a system without getting lost in overwhelming details.

What Will I learn?

: How to group complexity using visual frameworks and analogies, techniques for creating mental footholds that let you navigate between different system areas, and methods for making abstract architectures concrete and manageable in your own thinking.

What will I be able to do that I couldn't do before?

: You'll help your team get on the same page faster, use simple frameworks to cut down on confusion, and make it easier for everyone to make decisions and solve problems together.

Where are we going next, and how does this fit in?

: Shared models enable coordination on what you should be building as a team. Next we will discuss how to turn code reviews into constructive feedback loops to test against your own mental models.
<!-- end storymap -->


## When Mental Models Collide

<!-- AI:BEGIN:mini-toc -->
## In this chapter
- See @sec-when-mental-models-collide
- See @sec-shared-mental-models
- See @sec-power-of-shared-templates
<!-- AI:END:mini-toc -->

<!-- AI:BEGIN:figure-placeholder -->
<!-- Figure placeholder: consider adding a visual for shared mental models or the color-coding example mentioned in the chapter -->
<!-- AI:END:figure-placeholder -->

The bigger the team, the more moving parts you introduce:

- Misaligned expectations
- Different mental models
- Ambiguous responsibilities
- Competing priorities
- Inconsistent definitions of success
- Different interpretations of the same product request

Technical mastery gets you in the door.
Communication mastery allows you to scale.

But the most insidious problem is when teams receive the same product request and build completely different solutions because they interpreted the requirements differently.

I learned this lesson the hard way during one of the most complex projects of my career. Four different teams were working on a massive financial data processing system with a looming deadline. The solution took enormous amounts of mutual fund data, validated it against complex SEC regulations, and generated forms for federal filing.

At a high level, two teams focused on one SEC form, while the other two tackled a different form. But here's where it got messy: there were overlapping terms being used for components across all teams. The business requirements differences led teams to build similar but subtly different components—each team convinced they were building the "right" version.

Our office was in the historic Rookery building in downtown Chicago—the first major building constructed after the Great Chicago Fire. Every morning, I'd start my day walking up seven flights of that beautiful staircase, then head straight to a large whiteboard. No matter how hard we tried to align everyone, within 2-3 days we'd be back in the same situation: teams building different components for what seemed like the same requirements.

I drew out all the components on the whiteboard. There were over 60 different pieces. I knew it was too complex to discuss and expect people to understand. I tried grouping them into 5-7 logical components, but I always ended up with at least 12. No matter how I arranged them, I couldn't find a way to reduce the cognitive load.

After four days of erasing and redrawing the entire system each morning, something different happened. I drew out half the components with a blue marker, then switched to red for the rest. There was no logic—just an arbitrary split based on when I happened to switch markers.

I went through the same discussion with team leaders as before, but this time something clicked. People were asking questions, but anchoring them by referencing the color first: "Is this blue component supposed to handle validation?" "How does the red data flow connect here?"

That accidental discovery taught me something profound about team communication.

## Shared Mental Models: The Hidden Operating System

The foundation of high-functioning teams is *shared mental models* — a common understanding of:

- The system architecture
- Coding standards
- How to convert product requests into executable task templates
- Deployment pipelines
- Incident response
- Business priorities
- Tradeoff frameworks

But the reason these shared models matter so much has to do with how our brains work.

> Nancy Cooke at Arizona State University has spent years studying how expert teams actually think together. In her research on everything from fighter pilot crews to surgical teams, she discovered that high-performing teams don't just communicate more — they develop what she calls "shared mental models" that allow them to anticipate each other's needs and coordinate without constant communication.

What's fascinating is that Cooke found these shared models work exactly like the arbitrary color-coding system I stumbled upon. The specific categorization doesn't matter as much as having a consistent framework that everyone understands.

Human working memory is limited. Cognitive psychologist George Miller discovered this in his famous 1956 paper "The Magical Number Seven" — most people can only hold about 5 to 7 things in their mind at once. Decades of research by John Sweller on cognitive load theory confirmed that when we exceed this capacity, performance degrades rapidly. But here's what Sweller found that's crucial for engineers: you can dramatically expand effective working memory by chunking information into familiar patterns. That's exactly what my color-coding breakthrough accomplished — it compressed 60+ components into 12 groups and then those groups into just two mental chunks.

Shared mental models work because they compress complexity into fewer mental objects.

> It's like going to the grocery store without a list.

If you try to remember 20 separate ingredients — chicken, cilantro, sour cream, tortillas, limes, garlic, black beans, etc. — you'll likely forget something. But if you instead remember:

*"I'm making tacos and a side salad,"*

your brain instantly activates a cascade of pre-loaded associations. You know what ingredients belong to tacos and what belongs to the salad. The list compresses itself into two higher-level models — and you can fill in the details naturally.

Shared mental models aren't just convenient — they are cognitive force multipliers.

> *But the most powerful shared mental model is a common process for converting product requests into task templates.*

## The Power of Shared Task Templates

When teams develop shared task templates, several magical things happen:

### The Real Magic: Automatic Understanding

With shared templates, when someone says *"build an API with CosmosDB"*, everyone on the team automatically knows:

**Technology Stack:**

- ASP.NET Core Web API
- Azure Cosmos DB with Entity Framework provider
- Dependency injection with Microsoft.Extensions.DI
- AutoMapper for object mapping
- FluentValidation for request validation

**Architecture Patterns:**

- Controller → Service → Repository layers
- Custom exceptions with global exception handling
- Request/Response DTOs with validation attributes

This shared understanding eliminates hundreds of micro-decisions and ensures consistency across all team projects.

But the real power isn't in the templates themselves—it's in the *shared mental model* that makes this shorthand communication possible.

## The Mental Model Alignment Framework

The user has provided a lot of content. The assistant has to convert many remaining .pml files to .md with consistent storymap blocks. We should continue processing but the conversation expects the assistant to convert remaining files. The attachments include Decision_Making_Under_Uncertainty.pml, Requirements_Gathering.pml, Conclusion.pml, Communication_and_Team_Models.pml, Code_Review.pml, Technical_Leadership.pml, Visual_Thinking.pml. We have started converting some. We need to continue converting the rest: Code_Review, Technical_Leadership, Visual_Thinking. Continue conversion. (This part is internal commentary accidentally included.)