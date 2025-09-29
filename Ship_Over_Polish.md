# Ship Over Polish

<!-- Refocused from Embracing_Imperfection.md -->

## Core Idea
Momentum beats microscopic refinement; quality emerges from iteration velocity + feedback density.

## Anti-Patterns (Brief)
- Infinite PR nitpicks adding no user value
- Premature refactors before behavioral stability
- “Gold-plating” UI details pre product-market fit

## Decision Heuristics
| Scenario | Default Bias | Ship Trigger |
|----------|--------------|--------------|
| Net-new feature behind flag | Speed | Core path works end-to-end |
| Bug fix in hot path | Safety | Reproduction + test + patch green |
| Performance tuning | Evidence | Profiling shows top 1-2 bottlenecks |
| Refactor for clarity | Maintainability | Cognitive load > onboarding threshold |

## Scope Triage Ladder
Must (core value) → Should (risk mitigators) → Could (edge delight) → Won’t (log for later). Enforce in PR description; reject scope creep after “Must” locks.

## Definition of “Good Enough” Checklist
- User path success (happy path) validated
- Observability in place (basic logging/metrics)
- Reversible within one iteration
- Documented known gaps (CHANGELOG or issue)
- Tests cover critical failure modes

## Feedback Compression Tactics
- Dark launch + internal dogfood
- Feature flag % rollout with metrics guardrail
- 24h blast review window (timebox review)
- Post-merge polish queue (batch minor tweaks)

## Example
Feature: Recommendation tiles MVP.
Stop polishing when: tiles render, CTR tracked, fallback safe, algorithm job stable for 48h, instrumentation logs errors.

## Closing Bridge
With release momentum established, we address rapid judgment calls: next is Instant Decisions.
