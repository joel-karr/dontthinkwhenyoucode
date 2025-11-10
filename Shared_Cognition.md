# Shared Cognition

<!-- Fully merged: Think_Together.md + Code_Review.md (narrative + framework) -->
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

## Premise
Teams scale judgment when knowledge moves from individuals to a continuously updated shared model. Shared cognition reduces misinterpretation, prevents duplicate invention, and turns implicit expertise into reusable operational leverage.

## Pillars
1. Visual Alignment (architecture sketches / sequence diagrams)
2. Intent-Rich Reviews (why before what)
3. Structured Feedback (risk > clarity > style)
4. Knowledge Retention (capture decisions & rationale)
5. Practice Loops (recurring calibration drills)
6. Cognitive Compression (task templates & shared abstractions)

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

## Case Study: When Mental Models Collide (The Rookery)
A large regulatory filing platform effort split across four teams drifted into parallel, incompatible implementations. Over 60 named components emerged—each group convinced their interpretation was “correct.” Daily whiteboard attempts failed until an accidental color split (half blue / half red) allowed everyone to anchor questions consistently. The color choice had zero intrinsic logic—but it chunked complexity into two mental buckets, making alignment possible. The lesson: the specific taxonomy matters less than a consistent shared one.

### Friction Patterns Observed
- Repeated re-explanation of the same architecture
- Divergent naming for near-identical modules
- Late discovery of overlapping responsibilities
- Velocity collapse due to refactors to reconcile assumptions

### Intervention Principles
| Problem | Intervention | Why It Worked |
|---------|-------------|---------------|
| Excess cognitive load | Arbitrary 2-color grouping | Forced chunking & shared referencing |
| Semantic drift | Daily fast redraw + recap | Reinforced canonical model |
| Unowned overlap | Visual clustering discussion | Created explicit ownership boundaries |

---

## Cognitive Load & Chunking
Human working memory comfortably juggles only a handful of independent concepts. Classic research (Miller’s 7±2; refined by decades of cognitive load theory, e.g. Sweller) shows performance degrades once we exceed that limit. Chunking compresses multiple low-level details into a single higher-order pattern. Shared mental models are team-scale chunking: they turn 60 modules → 12 clusters → 2 colors.

| Raw | Chunked | Effect |
|-----|---------|--------|
| 60 standalone components | 12 logical groups | Reduced search space |
| 12 groups | 2 color sets | Faster cross-team referencing |
| Ad-hoc vocabulary | Canonical labels | Lower alignment latency |

Takeaway: Optimize for fewer, stable cognitive handles—not exhaustive precision in early phases.

---

## Task Templates as Cognitive Compression
Shared task templates (e.g., CRUD API, Background Job, Search Index, Ingestion Pipeline) encode default architecture, tooling, guardrails, and effort bands. Saying “CRUD + Background Job + API slice” invokes dozens of implied decisions (error handling, retry semantics, validation patterns) without negotiation.

### Template Shorthand Example (API + CosmosDB)
Implicitly conveys:
- Layers: Controller → Service → Repository
- Patterns: DTO mapping, validation, central exception filter
- Tooling: ASP.NET Core, FluentValidation, AutoMapper
- Operational: idempotent writes, standard telemetry hooks

This removes hundreds of micro-decisions and enables parallelism: engineers can advance implementation confidently before synchronous meetings catch up.

---

## Mental Model Alignment Framework
| Layer | Goal | Primary Question | Artifact |
|-------|------|------------------|----------|
| Vocabulary | Shared naming | “What do we call this?” | Glossary / diagram legend |
| Structure | Shared shape | “How do parts relate?” | System sketch / context map |
| Execution | Shared patterns | “What is the default way?” | Task templates / playbooks |
| Review | Shared evaluation | “What matters first?” | Comment taxonomy / checklists |
| Memory | Shared retention | “Where does this live?” | Decision log / snippet shelf |
| Evolution | Shared refinement | “What’s stale?” | Calibration ritual notes |

---

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

Enforce top-down ordering; lower categories cannot block if higher categories are resolved.

## Shared Artifacts
- Decision Journal: date, context, options, choice, expected outcome
- Snippet Library: canonical examples (flags, background jobs, retries)
- Diagram Shelf: versioned architecture visuals
- Template Catalog: standardized task patterns + effort ranges

## Calibration Rituals
Weekly 20‑min “Delta Review”: sample a merged PR; classify comment distribution; ask “automation or template?”  
Monthly Architecture Retro: update diagrams; retire stale ones; verify emergent patterns promoted or deprecated.

## Example
Recommendation tiles PR includes: intent, risk hotspots (job idempotency, fallback), metrics plan, test matrix. Feedback compressed to 12 comments: 2 risk, 4 logic, remainder informational—demonstrating taxonomy discipline.

---

## Migration Note
This chapter now contains the full narrative previously in `Think_Together.md`. That file remains only as a thin redirect until removal or archival.

## Closing Bridge
Once cognition is distributed, we shift to spreading adoption at org scale: Adoption Playbook next.
