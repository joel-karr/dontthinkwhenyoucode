
# Align Work with Business Priorities

<!-- begin storymap -->
Why do I want to read this?

: You've put a lot of time and energy into building a great technical solution, only to find out that the users weren't excited. You want to know how to align the effort you are putting in with the needs of the business.

What will I learn?

: How to work with product to identify where they expect measurable value, then determine the optimal effort to capture that value without unnecessary complexity.

What will I be able to do that I couldn't do before?

: Look at technical decisions from a business perspective, propose solutions that directly support business goals, and position yourself to work on projects that matter.

Where are we going next, and how does this fit in?

: Next we'll examine gold-plating and how chasing perfection undermines business alignment.
<!-- end storymap -->


## Overview

This chapter explains how to convert product requests into predictable work, estimate effort using task templates, identify unknowns, and run productive conversations with product and stakeholders so you deliver the right thing with the right effort.



## Use Templates to Estimate Product Requests

Now that you have a library of task templates and know approximately how long each one takes, break product requests into combinations of those templates rather than treating them as one big unknown. Use high-confidence template estimates instead of padding.

### Example: Product Listing Page with Advanced Search

Break the request into known templates and estimate each:

- CRUD API (Product) — 8 hours
- Search API (Product) — 14 hours
- Background Job (Inventory) — 20 hours
- CSV Data Ingestion — 8 hours
- UI Listing Page — 14 hours

You know what you're building because you've built each piece before. Tying requests back to template names makes estimates measurable and repeatable.

## Identify Unknowns

Even with templates, some product requests include elements that don't fit your playbooks. Call these "unknowns"—things that need research, prototyping, or a custom approach.

### Example: Real-Time Inventory Updates

A product manager asks for real-time inventory on the listing page. Your standard CRUD API handles reads/writes, but it doesn't provide push updates. This is an unknown.

- Known templates: CRUD API (Product), Search API (Product), CSV Data Ingestion, UI Listing Page
- Unknowns / Research items: Is there a better approach than Background Job (Inventory) to provide real-time updates? WebSockets? SignalR? Event streaming? Caching strategies?

Time-box research (a few hours). The goal is to find a high-confidence approach, not to build a full proof-of-concept.



## Apply Templates to New Scenarios

This section explains how to apply a completed template to a new scenario and how to promote template use from estimation into implementation planning.

### How to apply a template to a new scenario

1. Map the requested feature to template names and estimate each piece.  
2. Identify any unknowns and time-box investigation.  
3. Discuss options with product using a clear framework (effort, risk, value).  
4. Select the option that maximizes business value for the least reliable effort and plan implementation using template steps.

### Example: Putting a Template into Practice

When you take a completed template into implementation, ensure your acceptance criteria map to the template's expected outputs. If the template requires data ingestion, confirm input formats and monitoring requirements before work begins. If a template assumes a background job, confirm SLA and retry behavior.



## Have Better Conversations About Solutions

Once you know what maps to templates and what doesn't, talk with product and stakeholders to align on the best approach. Ask plain questions—obvious or out-of-the-box—because questions shape the conversation and surface simpler alternatives.

### Ask Questions That Open Possibilities

- What problem are we actually trying to solve with real-time updates?  
- Is the goal to avoid overselling, to improve UX, or to support analytics?  
- Could we accept a short delay for items that are plentiful and only check frequently for low-stock items?  
- What is the acceptable staleness for inventory before it becomes a customer problem?

Example conversation:

You: "Can you help me understand the most important thing we are trying to solve with real-time inventory updates"  
Product: "We don't want customers ordering products that are out of stock."  
You: "So the goal is to prevent overselling. Could we only check inventory more frequently when stock is below a threshold, and otherwise update every five minutes?"

The product manager may accept a threshold-based approach if it meets the business goal — and that dramatically reduces engineering effort.

### Present Options, Not Problems

Offer multiple solutions with effort and risk levels so stakeholders can choose tradeoffs.

Option 1 (High confidence): Deliver the core product catalog with search and CSV import. Inventory updates occur once a day via a scheduled job.  
  - Estimated effort: 2 weeks  
  - Risk: Low — proven templates

Option 2 (Medium confidence): Add frequent inventory checks for low-stock items (threshold-based).  
  - Estimated effort: 2 weeks + 3 days  
  - Risk: Medium — mostly template work; small custom logic

Option 3 (Low confidence): Full real-time inventory with push updates.  
  - Estimated effort: 4–6 weeks  
  - Risk: High — new territory, larger unknowns

Framing choices this way converts negotiation into a decision about tradeoffs, not a debate about technical impossibility.

## Exercises

Pick a current product request and break it into template components with time estimates.  
Identify any unknowns and plan a 2–4 hour research spike.  
Prepare three options (high/medium/low confidence) and present them to a stakeholder for a decision.
