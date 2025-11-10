# Requirements & Alignment

The tension of the pending question can be felt by everyone in the small conference room. The lead product manager, Maya, is already bracing for pushback, but she asks it anyway:

How long will "IT" take?

The question is simple, but it bundles uncertainty about scope, value, constraints, assumptions, sequencing, and execution risk. The four engineers feel the weight immediately. Maya spent days assembling pixel‑perfect mocks and user flows. The feature – personalized restaurant recommendations after purchase – promises a revenue lift, and the product leader is eager to commit to a timeline to share with the executives of the company.

Eric finally breaks the silence with the reflexive defensive move:

"When do we need it by?"

This chapter exists so that question is no longer your first reaction. Instead, you create a fast, structured path from vague request → aligned plan → confident execution.

---

## Friction Signals
- Rework after “misunderstood” feature
- Estimates swing wildly after stakeholder review
- Delivered feature under-used or low adoption
- Late discovery of hidden constraints (compliance, data freshness, SLAs)
- Conversations collapse into date negotiation instead of outcome shaping

## Core Flow
1. Surface Intent (goal / actor / change)
2. Expose Constraints & Assumptions
3. Define Value Slice (measurable outcome)
4. Map to Task Templates (initial build set)
5. Identify Unknowns (research spikes)
6. Alignment Check (stakeholder reflection / option selection)

## Framework Snapshot
| Layer | Question | Output Artifact |
|-------|----------|-----------------|
| Intent | What problem matters now? | Problem Statement |
| Outcome | How will we know it worked? | Success Metric |
| Constraints | What must / must not change? | Constraint List |
| Slice | What is smallest deliverable value? | Release Slice |
| Execution | What templates & unknowns? | Build Plan |
| Alignment | Are stakeholders choosing explicit tradeoffs? | Option Matrix |

## Example (Restaurant Recommendations)
Problem: Users not discovering new restaurants; repeat purchase plateau.
Metric: +10% cross‑category orders in 60 days.
Slice: Show 3 “Because you liked X” tiles on order confirmation page.
Templates: CRUD (recommendation seed), Background Job (similarity calc), API (serve suggestions), UI Component (tile block).
Unknowns: similarity algorithm approach, freshness threshold for recalculation.

---

## Use Templates to Estimate Product Requests
Once you have a library of task templates (with typical effort bands), you decompose a request into named, repeatable units instead of treating it as one opaque guess. The estimate becomes the sum of familiar parts—not a padded risk hedge.

### Example: Product Listing Page with Advanced Search
Break the request:
- CRUD API (Product) — 8h
- Search API (Product) — 14h
- Background Job (Inventory) — 20h
- CSV Data Ingestion — 8h
- UI Listing Page — 14h

You now talk in concrete building blocks stakeholders can challenge (“Do we really need the background job in v1?”) rather than in a mystical lump (“That’s probably 6–8 weeks”).

### Anti-Patterns
| Smell | Instead Do |
|-------|------------|
| One giant “feature” estimate | Break into template line items |
| Add 30% “just in case” | Isolate true unknowns + spike |
| Debate hours vs days | Align on scope units first |

---

## Identify Unknowns
Templates don’t cover everything. Explicitly label the parts that (a) require discovery, (b) rely on an unproven integration, or (c) have ambiguous constraints. Unknowns get a time‑boxed spike—typically 2–4 hours—to produce a decision, not a prototype.

### Unknown Qualifiers
| Type | Trigger | Output |
|------|---------|--------|
| Technical | New pattern / scale concern | Approach choice & risk note |
| Product | Ambiguous need / metric gap | Clarified success statement |
| Operational | SLA / compliance unclear | Constraint list update |

If something remains fuzzy after the spike, downgrade its confidence in the option matrix instead of silently inflating the whole estimate.

---

## Apply Templates to New Scenarios
Workflow when mapping a fresh request:
1. Translate request narrative → candidate templates.
2. Mark residual pieces as Unknowns; schedule spikes.
3. Produce a first‑pass Build Plan: templates + effort + risk notes.
4. Validate value slice: Does this smallest slice still advance the metric?
5. Present structured options (see next section).

### Putting a Template into Practice
Ensure acceptance criteria map directly to template outputs. If a template requires a background job, confirm schedule, retry semantics, and monitoring before implementation begins. This prevents “we’ll figure that part out later” debt.

---

## Have Better Conversations About Solutions
Alignment is accelerated by questions that collapse assumptions. You’re not pushing back—you’re co‑designing value shape.

### Ask Questions That Open Possibilities
| Prompt | Purpose |
|--------|---------|
| “What problem are we really solving?” | Re-center on outcome |
| “What’s acceptable staleness?” | Quantify freshness constraint |
| “Could a threshold-based approach work first?” | Offer cheaper step |
| “What metric should move first?” | Tie scope to measurement |

Example dialogue:
> Engineer: “Is preventing overselling the primary goal?”  
> PM: “Yes.”  
> Engineer: “Then we could update low‑stock items frequently and batch everything else.”  
Result: scope narrows without undermining the outcome.

### Present Options, Not Problems
Offer 2–3 clearly differentiated choices with effort + risk + confidence. This reframes negotiation from “Can you do it faster?” to “Which tradeoff do you choose?”

| Option | Description | Effort | Risk | Confidence |
|--------|-------------|--------|------|------------|
| 1 | Core catalog + daily inventory batch | 2 wks | Low | High |
| 2 | Threshold-based frequent checks (low stock) | 2 wks + 3d | Medium | Med‑High |
| 3 | Full real-time push updates | 4–6 wks | High | Low |

Document the chosen option along with discarded ones—future scope creep attempts now have historical context.

---

## Alignment Checklist (Lite)
- [ ] Intent statement written & agreed
- [ ] Success metric baseline + target captured
- [ ] Constraints enumerated & accepted
- [ ] Smallest value slice validated
- [ ] Template list + unknown spikes scheduled
- [ ] Option matrix reviewed; decision recorded
- [ ] Build plan fed into tracking system

---

## Exercises
1. Take an active request: decompose into template line items + unknown list.  
2. Write an explicit intent + success metric; trim any scope not serving them.  
3. Produce a 3‑option matrix (baseline / enhanced / aspirational).  
4. Time‑box one unknown spike and record the decision artifact.  
5. Revisit a past “miss” and retro-map where the framework broke.

---

## Closing Bridge
Next: Apply proportional effort discipline (Right-Sized Engineering).
