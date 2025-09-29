# Shared Cognition

<!-- Merged from Think_Together.md + Code_Review.md -->

## Premise
Teams scale judgment when knowledge moves from individuals to a continuously updated shared model.

## Pillars
1. Visual Alignment (architecture sketches / sequence diagrams)
2. Intent-Rich Reviews (why before what)
3. Structured Feedback (risk > clarity > style)
4. Knowledge Retention (capture decisions & rationale)
5. Practice Loops (recurring calibration drills)

## Review Operating Model
| Stage | Focus | Artifact |
|-------|-------|----------|
| Pre-PR | Intent doc / lightweight context | Intent Block (problem, approach, tradeoffs) |
| PR Open | Risk surfaces first | PR description checklist |
| Review Window | 24h focused batch | Reviewer rotation |
| Merge | Gate: risk + correctness | Auto CI + required reviewers |
| Post-Merge | Learning capture | Decision log / snippet library |

## Comment Taxonomy
- Risk: data loss, security, scaling
- Logic: correctness / edge cases
- Clarity: naming, structure
- Maintainability: coupling, duplication
- Style: non-blocking aesthetics

Enforce top-down ordering; lower categories cannot block if higher ones resolved.

## Shared Artifacts
- Decision Journal: date, context, options, choice, expected outcome
- Snippet Library: canonical examples (flags, background jobs, retries)
- Diagram Shelf: versioned architecture visuals

## Calibration Rituals
Weekly 20-min “Delta Review”: sample merged PR; classify comments; ask “automation or template?”
Monthly Architecture Retro: update diagrams & retire stale ones.

## Example
Recommendation tiles PR includes: intent, risk hotspots (job idempotency, fallback), metrics plan, test matrix.
Feedback compressed to 12 comments; 2 risk, 4 logic, rest informational.

## Closing Bridge
Once cognition is distributed, we shift to spreading adoption at org scale: Adoption Playbook next.
