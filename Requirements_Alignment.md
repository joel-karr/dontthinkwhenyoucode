# Requirements & Alignment

<!-- Merged from Requirements_Gathering.md + Business_Alignment.md -->

## Purpose
Unify problem clarification with value targeting so downstream execution (templates, estimation) is anchored to business impact.

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
