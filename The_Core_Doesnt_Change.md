# Adapt Confidently to AI Tools

Filename: The_Core_Doesnt_Change.md

<!-- begin storymap -->
Why do I want to read this?

: You're concerned about how AI and automation might affect your career as a software engineer. You've seen the headlines about AI writing code and replacing developers, and you want clarity on which skills remain valuable.

What will I learn?

: Why the fundamental thinking skills you've built become more valuable as AI tools advance, and how to leverage AI while focusing on uniquely human strengths.

What will I be able to do that I couldn't do before?

: Adapt confidently to new AI tools, prioritize high-value learning, and position yourself to thrive as the industry evolves.

Where are we going next, and how does this fit in?

: This chapter is the culmination of our journey: the mental models and practices from earlier chapters remain the core of good engineering practice even as tools change.

<!-- end storymap -->

Software engineering is always changing. It is easy to feel overwhelmed trying to chase every new framework or language. But the biggest shifts haven't been about syntax or libraries---they have been in the way we communicate with computers.

<!-- AI:BEGIN:mini-toc -->
## In this chapter
- See @sec-from-task-templates-to-prompt-templates
- See @sec-building-ai-prompts
- See @sec-working-with-your-team
<!-- AI:END:mini-toc -->

At first, we didn't have programming languages at all. There were stacks of punch cards. Each card carried a single instruction and fed into a computer in a specific order. If the cards got out of order, your whole program would fail. The process was so slow and fragile that computers were mostly confined to research purposes.

Then came assembly language. For the first time, programmers could type instructions instead of feeding cards. They were still using hardware-level commands like MOV or PUSH, but they gained a massive leap in efficiency.

This pattern has repeated itself numerous times. Each leap didn't just make programming more convenient---it made programming itself an order of magnitude faster. As development costs dropped, demand for software increased exponentially. More industries adopted technology, expectations of capabilities rose, and the number of software engineers grew.

In this chapter, you'll learn how to apply the same approaches you've built---task templates and mental models---to a new way of communicating with computers. AI code generation offers the ability to start with natural language that then creates languages that can be compiled into instructions. The tools are changing, but the core thinking remains the same.

We've seen how punch cards transitioned into assembly but let’s take a deeper dive into other times in software engineering history. Assembly moved us away from punch cards, but we still needed to write hardware level instructions line by line.

Let's say you wanted to add two numbers with assembly.

First you had to know where in memory each number was stored.

~~~
MOV AX, [num1]   ; Load num1 into register AX  
ADD AX, [num2]   ; Add num2 to AX  
MOV [result], AX ; Store the result
~~~

Writing even a simple program required deep hardware knowledge:

* Which registers were available and what could get overwritten
* Different options for memory addressing modes (direct, indirect, offset-based)
* Stack frame structure to identify where return addresses would go
* Instruction time to avoid performance issues
* Bit-level operations where you may have to shift, mask, or XOR values manually

Many engineers started with pencil and paper, writing out instructions before typing them in. It was a process of trial and error. If one instruction was wrong, the program might crash with little information in terms of logging or reason for failures.

Then came compilers.

Instead of manually managing registers and stack pointers, you could write:

~~~
int add(int a, int b) {
    return a + b;
}
~~~

Suddenly, you didn't need to know the hex address of every variable. You didn't have to count how many bytes were pushed on the stack. The compiler did all that.

You were still programming, but it changed the way you communicated with the computer to be a more human readable approach.

It wasn't just easier. It was faster. Much faster.

Not everyone was convinced. Many engineers worried compiled code would run slower than handwritten assembly.

John Backus, the lead of the FORTRAN project at IBM, later said “our greatest triumph was convincing programmers that compiled code could run as fast as hand-written assembly.” [^backus1978]

And the pattern didn't stop with compilers. Every major shift in how we communicate with computers has followed the same cycle: first skepticism, then adoption, then a large increase in demand.

Consider object-oriented programming (OOP). For decades, software engineers wrote in a procedural style, one function after another. OOP introduced a new way to describe systems using objects and properties, closer to how people describe real-world things. Early critics dismissed it as overly complex and unnecessary, but once it caught on, OOP became the dominant paradigm for decades.

Then came frameworks and ORMs. Instead of writing the core orchestration of code, frameworks like Rails, Django and ASP.NET let engineers focus on business logic. ORMs replaced raw SQL with higher-level queries. Initially, people worried that these abstractions would hide too much complexity or encourage bad habits. Instead the speed of development dramatically accelerated and raised the baseline for what a quick and simple application could deliver.

Next came IntelliSense and autocomplete which brought further assistance into the Integrated Developer Environment (IDE). There was some initial pushback that software engineers should know the underlying interfaces they were accessing, and it would be highly error prone to suggest methods. It not only saved time in typing, but it also removed the need to memorize or research every method signature and allowed software engineers to focus on architecture and problem solving. 

Package managers like NuGet and NPM replaced the need for teams to copy libraries or rebuild common functionality from scratch. Skeptics warned about "dependency hell" or insecure code. But the package managers quickly evolved to include versioning and security scans. Software engineers told the system what packages they needed, and what took hours was reduced to seconds. The increase in efficiency reduced the cost of software development and again increased the overall demand for custom solutions.

Cloud systems and infrastructure as code was another huge leap in efficiency. Acquiring hardware and configuring servers once took weeks of back-and-forth communication between departments or external companies. With the introduction of tools like Terraform and cloud services, software engineers could define what they needed in code and set up hardware in a matter of minutes. Initially, it lacked the oversight of best practices and governance typically done by a data center engineer but as the controls evolved, it provided a massive leap in productivity.

Each time, the same pattern emerged:

* Communication with computers changed
* Engineers became exponentially more efficient
* Expectations for software skyrocketed
* Demand for software engineers grew

The numbers back it up. In the 1970's there were fewer than 100,000 programmers working in the U.S. By 1990, that number had grown to around 568,000. By 2010, the Bureau of Labor Statistics counted more than 1.4 million software engineering roles in the U.S. alone. In 2025, that number is closer to 1.8 million and global estimates are over 26 million professional software engineers.

Every time building software became easier, the world responded with a demand for even more software engineers. Efficiency hasn't shrunk the industry, it has expanded it.

AI code generation may look like the most disruptive change yet. The headlines echo familiar fears we've heard before like "Junior developers aren't needed" or "Kids shouldn't bother learning to code".

But history tells us a different story. From compilers to OOP to IntelliSense, every leap in how we communicate with computers engineers becomes more productive, expectations increase, and demand for software grows.

AI is not an exception.

AI code generation can feel like magic at first. You type a few words in natural language and suddenly a block of code appears on the screen. But that same magic can quickly become frustrating.

When prompts are too vague, the AI attempts to fill in the gaps with its own assumptions. Sometimes it guesses right. Other times it invents solutions that are completely misaligned with your goals. Instead of saving time, you waste more of it untangling the mess.

That's why many software engineers describe AI as a black box. You don't always know what it's doing under the hood and the results can feel unpredictable. However, if you learn how to communicate with AI through prompts, it can be another major leap in efficiency.

And that's where the skills you've already built come in. In chapter 3 on Task Templates, we created repeatable steps to build predictable software. Those templates can be adjusted to be perfect AI prompts giving AI clarity and boundaries.

The tools are new, but the mental models and approaches are the same.

## From Task Templates to Prompt Templates {#sec-from-task-templates-to-prompt-templates}

Let's use an example template from Chapter 3 Task Templates[xxx](#sec.buildtasktemplates). This template was designed in order to give enough information for a software engineer to understand exactly what was needed. General best practices and standard design details are not included in our original task template.

*Template Name:* Standard CRUD API for DOMAIN_ENTITY with Event Sourcing

*Technology Stack:* ASP.NET Core, Dapr, MediatR, Entity Framework

*Development Tasks:*

 Create domain entity classes
 Set up Entity Framework DbContext and configure entity mappings
 Implement command/query handlers
 Create a REST API controller 
 Set up Request/Response DTOs and AutoMapper profiles for data mapping
 Add FluentValidation rules
 Configure JWT Bearer authentication and authorization policies

Task templates create a repeatable approach with proven designs. Once you have practiced them enough, it becomes an exercise of how fast you can type. If you compare how task templates have been structured, they provide an excellent framework to build AI prompts.

Build a standard CRUD API for DOMAIN_ENTITY using C# and .NET 8 with ASP.NET Core, Dapr, MediatR, and Entity Framework Core.  

Requirements:  
 Create domain entity classes in a clean domain layer  
 Set up Entity Framework DbContext and configure entity mappings with Fluent API  
 Implement MediatR command and query handlers for create, read, update, and delete operations  
 Expose a REST API controller with endpoints for CRUD operations following REST conventions  
 Use Request/Response DTOs and AutoMapper profiles for mapping between entities and DTOs  
 Add FluentValidation rules for input validation  
 Configure JWT Bearer authentication with authorization policies for secured endpoints  
 Include example unit tests for handlers and controllers using xUnit and Moq  

Follow best practices for clean architecture, maintainability, scalability, and security. Organize code into appropriate projects (Domain, Application, Infrastructure, API).

The task template and the AI prompt are almost identical, but we added some additional directions for the AI engine. The mental work hasn't changed. You still decide the patterns and the guardrails. But now, instead of spending hours typing code, you can spend minutes.

In the next section, we’ll walk through creating a prompt from a task template---and see how to adjust it when things don’t go as expected.

## Building AI Prompts {#sec-building-ai-prompts}

<!-- AI:BEGIN:figure-placeholder -->
<!-- Figure placeholder: consider adding a visual mapping from task templates to AI prompts -->
<!-- AI:END:figure-placeholder -->

If you just copy and paste your original templates into an AI code generator, you likely will get unpredictable results. However, if we make a bit of effort, we can add effective AI prompts to all your templates.

### Step 1: Review a Task Template

Choose one task template from your playbook, something that you know well enough that you can spot any mistakes in the code quickly. 

Imagine reading the tasks from your template aloud to someone brand new to coding. What parts might be confusing for them because they lack enough detail? Update your tasks to make those assumptions explicit.

#### Example: Background Job Template

Here is an original task template:

*Template Name:* Background Job

*Technology Stack:* Azure Function, Dapr, MediatR

*Development Tasks:*

 Create .NET Worker Service project with dependency injection configuration
 Set up hosted service class
 Implement command handlers with business logic and error handling
 Configure Polly retry policies and circuit breaker patterns
 Add structured logging with correlation IDs
 Handle dead letter queue scenarios with retry logic

Let's add some additional assumptions:

 Create .NET 8.0 Worker Service project with dependency injection configuration
 Deploy using GitHub Actions with infrastructure provisioned via Terraform
 Include unit tests should be included using xUnit and Moq
 Configure logging with Serilog in a consistent JSON format for ingestion into Azure Monitor

### Step 2: Translate into a Prompt

At this point you could hand the template to a developer and they’d know what to do. But if you want to accelerate work with AI tools, you’ll need to phrase it in a way the AI can interpret. That’s where translating into a prompt adds value.

AI chat can help us translate our information into a prompt. Prompt wording directly affects the quality of the AI’s output. By rephrasing your template into a structured request, you give the AI clearer context, which reduces trial and error and helps it generate code that matches your team’s standards.

You can try prompting a chat with "Can you create a prompt to give AI Code Gen to build this template?" 

Paste your task template information into the chat and you might get something back like this:

Build a background job using a .NET 8 Worker Service project with Azure Functions, Dapr, and MediatR.

    Requirements:

     Configure dependency injection and set up a hosted service class
     Implement MediatR command handlers with business logic and error handling
     Configure Polly retry policies with circuit breaker patterns
     Handle dead letter queue scenarios with retry logic
     Add structured logging using Serilog with correlation IDs in JSON format
      for ingestion into Azure Monitor
     Include unit tests with xUnit and Moq for success, failure, and retry cases
     Deployment should be set up using GitHub Actions with infrastructure 
     provisioned via Terraform

    Follow Clean Architecture principles (Domain, Application, Infrastructure layers). 
    Code should be production-ready, secure, and maintainable.

### Step 3: Execute the Prompt

Run the new prompt in an AI code generator to see what we get back. Review the output like you are doing a pull request code review. 

* Does it follow clean architecture?
* Is the naming convention matching your teams’ best practices?
* Are there any potential performance bottle necks?

Take note of anything that didn't come out as expected. Those notes become your next round of prompt edits.

### Step 4: Iterate

You likely won't get perfect results on the first try. Iterate until the AI's output is good enough that it could pass a standard code review. The goal isn't to get code identical to what you'd write, but to reduce your effort to a quick review and a few minor edits.

Over time, you'll fully update your task template playbook so that all of your templates have an associated AI prompt to start with.

### Up Next: Working with Your Team

You’ve now seen how the same task templates that guided your work can guide AI as well. With AI, your bottleneck is no longer the speed you type, but your ability to structure problems well. That’s individual mastery in the AI era. Next, we’ll turn our attention outward: how to bring these same systems into your team.

<!-- AI:BEGIN:end-matter -->
## Exercises
- Convert one task template into an AI prompt and run two iterations, noting improvements.
- Review an AI-generated implementation from the prompt and produce a short checklist of issues to fix.

<!-- AI:END:end-matter -->

[^backus1978]: Backus, J. (1978). *The history of FORTRAN I, and FORTRAN II*. ACM SIGPLAN Notices, 13(8), 165–180.

