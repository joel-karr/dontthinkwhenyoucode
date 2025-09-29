# Requirements & Alignment

<!-- Merged from Requirements_Gathering.md + Business_Alignment.md -->

The tension of the pending question can be felt by everyone in the small conference room. The lead product manager, Maya, is already bracing for pushback, but she asks it anyways. 

How long will "IT" take?

The question itself is extremely simple, but it represents so many unknown variables that it overwhelms the four software engineers in the room. 

Maya had spent days trying to document every detail of what was needed. She had pixel perfect mockups that showed exactly how the new feature should look. There were flow diagrams that should each action for different types of users. The new feature would allow users the ability to easily see other restaurants they may want to try based on their previous purchase history. It would instantly boost revenue for the company and  



As the sofware team nervously glances around to each other, one person decides to speak up.

A software engineer named Eric finally gives into the pressure and responds with the same safe question that they always use. 

"When do we need it by?"

## Friction Signals
- Rework after “misunderstood” feature
- Estimates swing wildly after stakeholder review
- Delivered feature under-used or low adoption

## Core Flow
1. Surface Intent (goal / actor / change)
2. Expose Constraints & Assumptions
3. Define Value Slice (measurable outcome)
4. Map to Task Templates (initial build set)
5. Identify Unknowns (research spikes)
6. Alignment Check (stakeholder reflection)

## Framework Snapshot
| Layer | Question | Output Artifact |
|-------|----------|-----------------|
| Intent | What problem matters now? | Problem Statement |
| Outcome | How will we know it worked? | Success Metric |
| Constraints | What must / must not change? | Constraint List |
| Slice | What is smallest deliverable value? | Release Slice |
| Execution | What templates & unknowns? | Build Plan |

## Example (Restaurant Recommendations)
Problem: Users not discovering new restaurants; repeat purchase plateau.
Metric: +10% cross-category orders / 60 days.
Slice: Show 3 “Because you liked X” tiles on order confirmation page.
Templates: CRUD (recommendation seed), Background job (similarity calc), API (serve suggestions).
Unknowns: similarity algorithm, freshness threshold.

## Closing Bridge
Next: Apply proportional effort discipline (Right-Sized Engineering). 
