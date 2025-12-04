# Universal Workflow Pattern - Visual Guide

## The Core Pattern (Works Everywhere)

```
┌─────────────────────────────────────────────────────────────────┐
│                     CONSTITUTION                                 │
│  (Non-negotiable principles that govern all work)               │
│                                                                  │
│  Software:     Tech stack, security, coding standards           │
│  Grant:        Funder rules, compliance, writing style          │
│  Content:      Brand voice, SEO rules, style guide              │
│  Design:       Design system, accessibility, brand guidelines   │
│  [Any Domain]: Core principles + quality standards              │
└─────────────────────────────────────────────────────────────────┘
                               ↓
┌─────────────────────────────────────────────────────────────────┐
│                   4-6 SPECIALIZED PERSONAS                       │
│         (Each brings expertise, they check/balance each other)  │
│                                                                  │
│  Persona 1: STRATEGIST    - Analyzes, plans, defines direction  │
│  Persona 2: CREATOR       - Builds/writes the main deliverable  │
│  Persona 3: SPECIALIST    - Deep expertise (budget, SEO, etc.)  │
│  Persona 4: REVIEWER      - Quality checks, finds issues        │
│  Persona 5: FINALIZER     - Polishes, documents, ships          │
│                                                                  │
│  SOFTWARE:  Product Owner → Architect → Dev → QA → Writer       │
│  GRANT:     Strategist → Writer → Budget → Compliance → Editor  │
│  CONTENT:   Strategist → Writer → SEO → Fact-Check → Editor     │
└─────────────────────────────────────────────────────────────────┘
                               ↓
┌─────────────────────────────────────────────────────────────────┐
│                    4-PHASE WORKFLOW                              │
│                                                                  │
│  Phase 1: STRATEGY/PLANNING                                     │
│    Input:  User need, requirements, context                     │
│    Output: Strategic doc (PRD, Grant Outline, Content Brief)    │
│    Gate:   ✅ Strategy approved → advance                       │
│                                                                  │
│  Phase 2: CREATION/IMPLEMENTATION                               │
│    Input:  Phase 1 artifacts                                    │
│    Output: Main deliverable (Code, Grant Narrative, Article)    │
│    Gate:   ✅ Core work complete → advance                      │
│                                                                  │
│  Phase 3: REVIEW/REFINEMENT                                     │
│    Input:  Phase 2 artifacts                                    │
│    Output: Review reports, revised versions                     │
│    Gate:   ✅ Critical issues fixed → advance                   │
│                                                                  │
│  Phase 4: FINALIZATION/DOCUMENTATION                            │
│    Input:  Phase 3 artifacts                                    │
│    Output: Polished, documented, ready-to-ship                  │
│    Gate:   ✅ Quality standards met → SHIP                      │
└─────────────────────────────────────────────────────────────────┘
                               ↓
┌─────────────────────────────────────────────────────────────────┐
│              ARTIFACT-DRIVEN ITERATION                           │
│        (Version control enables methodical revisions)           │
│                                                                  │
│  artifacts/                                                     │
│    ├── 01-strategy-v1.md          (First draft)                │
│    ├── 01-strategy-v2.md          (After feedback)             │
│    ├── 02-creation-draft-v1.md    (Initial work)               │
│    ├── 02-creation-draft-v2.md    (Specialist revisions)       │
│    ├── 02-creation-draft-v3.md    (Reviewer feedback)          │
│    ├── 03-review-report.md        (Issues found)               │
│    ├── 04-final-version.md        (Polished output)            │
│    └── workflow-log.md            (Iteration history)          │
│                                                                  │
│  KEY: Every phase produces REVIEWABLE, VERSIONED files          │
│       Not just "AI said something" in chat                      │
└─────────────────────────────────────────────────────────────────┘
```

## Domain Translation Matrix

| Element | Software Dev | Grant Writing | Content Writing | Product Design |
|---------|--------------|---------------|-----------------|----------------|
| **Constitution Core** | Tech stack, security | Funder rules, compliance | Brand voice, SEO | Design system, a11y |
| **Strategist** | Product Owner | Grant Strategist | Content Strategist | Design Strategist |
| **Creator** | Developer | Grant Writer | Content Writer | UX/Visual Designer |
| **Specialist 1** | Architect | Budget Analyst | SEO Specialist | Accessibility Expert |
| **Specialist 2** | - | Compliance Reviewer | Fact Checker | - |
| **Reviewer** | QA Engineer | Grant Editor | Content Editor | Design Reviewer |
| **Phase 1 Output** | PRD, Tech Spec | RFP Analysis, Outline | Content Brief | Design Brief, Wireframes |
| **Phase 2 Output** | Source Code | Grant Narrative, Budget | Article Draft | High-Fidelity Mockups |
| **Phase 3 Output** | Code Review Report | Compliance Report | SEO + Edit Report | A11y Audit, Critique |
| **Phase 4 Output** | README, Docs | Executive Summary | Meta Tags, Distribution | Design Specs, Handoff |
| **Quality Metrics** | Test coverage, security | Compliance %, score rubric | SEO score, readability | WCAG compliance, consistency |

## Workflow Pattern Selection

```
┌─────────────────────────────────────────────────────────────────┐
│  QUESTION 1: Is there a hard deadline?                          │
│                                                                  │
│  YES (grant deadline, publish date)                             │
│    → Consider LINEAR workflow                                   │
│                                                                  │
│  NO (ongoing improvement)                                       │
│    → Consider ITERATIVE workflow                                │
└─────────────────────────────────────────────────────────────────┘
                               ↓
┌─────────────────────────────────────────────────────────────────┐
│  QUESTION 2: Multiple specialists needed simultaneously?        │
│                                                                  │
│  YES (writer + budget analyst both working)                     │
│    → Consider PARALLEL TRACKS workflow                          │
│                                                                  │
│  NO (one person/persona at a time)                              │
│    → Consider LINEAR workflow                                   │
└─────────────────────────────────────────────────────────────────┘
                               ↓
┌─────────────────────────────────────────────────────────────────┐
│  QUESTION 3: Will you test/review and revise multiple times?    │
│                                                                  │
│  YES (design testing, feature iteration)                        │
│    → Consider ITERATIVE or HYBRID workflow                      │
│                                                                  │
│  NO (one pass with reviews)                                     │
│    → Consider LINEAR workflow                                   │
└─────────────────────────────────────────────────────────────────┘

RESULT:
- LINEAR: Grant writing, content publishing, straightforward projects
- ITERATIVE: Software development, product design, research
- PARALLEL: Complex grants, large features, multi-discipline work
- HYBRID: Mix of above (most realistic for complex work)
```

## Cross-Persona Dialogue Example

```markdown
## Artifact: 02-grant-narrative-draft-v1.md

### Budget Analyst Review (Phase 2)
> **Issue:** Line 147 mentions "comprehensive staff training program"
> but I don't see a budget allocation for this.
> **Question:** Should I add a training line item? If so, what scope?
> **Impact:** HIGH - RFP requires budget-narrative alignment

### Grant Writer Response
> **Resolution:** Yes, add training budget line.
> **Details:**
> - 4 full-day workshops @ $2,500 each = $10,000
> - Materials and venue = $2,000
> - Total = $12,000
> **Action:** Updated narrative (v2) with detailed training description
> at lines 147-165 to justify this budget.

### Budget Analyst Confirmation
> ✅ Added line item 3.2: "Staff Training & Development - $12,000"
> ✅ Justification aligns with narrative lines 147-165
> ✅ Updated artifacts/03-budget-v2.xlsx

### Compliance Reviewer Note
> ✅ Training costs are allowable per RFP Section 4.3
> ✅ Narrative-budget alignment verified
```

**KEY INSIGHT:** Each review/question is documented in the artifact or
workflow-log.md. This creates transparent, traceable iteration.

## Prompt Structure (Universal)

```markdown
# Prompt: [PERSONA] - [TASK]

**Persona:** [Role Name]
**Phase:** [1-4] - [Phase Name]
**Purpose:** [One sentence]

## When to Use
✅ Use when: [Trigger]
❌ Don't use when: [Wrong time]

## The Prompt
You are a [PERSONA]. Your task is to [TASK].

**Rules:**
1. Follow CONSTITUTION.md
2. [Domain-specific rules]
3. Output: [Format]
4. If unclear: ASK questions

**Input Artifacts:**
- [File 1]
- [File 2]
- CONSTITUTION.md

**Output Artifact:**
- artifacts/[filename]

**Context:**
[Variables to fill in]

**Quality Checklist:**
- [ ] [Criterion 1]
- [ ] [Criterion 2]
- [ ] Aligns with CONSTITUTION.md

## Example Output
[Show structure]
```

## Quality Metrics Framework

```
┌─────────────────────────────────────────────────────────────────┐
│  Define "DONE" in Your Domain                                    │
│                                                                  │
│  SOFTWARE:                                                       │
│    ✅ All tests pass (unit, integration)                        │
│    ✅ Code coverage ≥80%                                         │
│    ✅ No CRITICAL/HIGH security issues                          │
│    ✅ Performance benchmarks met                                │
│    ✅ Documentation complete                                    │
│                                                                  │
│  GRANT:                                                          │
│    ✅ Compliance checklist 100%                                 │
│    ✅ Score rubric alignment ≥85%                               │
│    ✅ Budget-narrative alignment verified                       │
│    ✅ All required attachments present                          │
│    ✅ Peer review score ≥80%                                    │
│                                                                  │
│  CONTENT:                                                        │
│    ✅ SEO score ≥85/100                                         │
│    ✅ Readability (Flesch) ≥60                                  │
│    ✅ Brand voice alignment (audit)                             │
│    ✅ All claims fact-checked                                   │
│    ✅ Meta tags optimized                                       │
│                                                                  │
│  [YOUR DOMAIN]:                                                  │
│    ✅ [Measurable criterion 1]                                  │
│    ✅ [Measurable criterion 2]                                  │
│    ✅ [Measurable criterion 3]                                  │
└─────────────────────────────────────────────────────────────────┘
```

## Issue Severity (Universal)

```
CRITICAL 🔴
- Work is fundamentally broken
- Would cause rejection/failure
- Legal/compliance violation
- Must fix before advancing

Examples:
- Software: Security vulnerability, broken functionality
- Grant: Eligibility not met, missing required section
- Content: Factually incorrect, brand violation
- Design: Fails accessibility requirements

HIGH 🟠
- Significant quality issues
- Would likely cause problems
- Reduces competitiveness
- Should fix before advancing

Examples:
- Software: Performance issues, poor error handling
- Grant: Weak evidence, budget gaps
- Content: Poor SEO, unclear messaging
- Design: Inconsistent with design system

MEDIUM 🟡
- Quality improvements available
- Wouldn't block shipping
- Good to address if time permits
- Consider fixing

Examples:
- Software: Code organization, documentation gaps
- Grant: Opportunities to strengthen narrative
- Content: Additional keywords, formatting
- Design: Polish, micro-interactions

LOW 🟢
- Nice-to-have improvements
- Negligible impact
- Address in future iterations
- Not urgent

Examples:
- Software: Code style preferences
- Grant: Wording alternatives
- Content: Minor style tweaks
- Design: Optional enhancements
```

## The Key Insight

**Current State (Problematic):**
```
User: "Build me a grant proposal"
AI: [Generates 10 pages]
User: [Overwhelmed, can't iterate methodically]
```

**Constitutional Workflow (Better):**
```
User: "We need a grant proposal. Let's start with strategy."
  ↓
Strategist Persona → artifacts/01-rfp-analysis.md (REVIEWABLE)
  ↓
User: "Good, but emphasize youth engagement more"
  ↓
Strategist → artifacts/01-rfp-analysis-v2.md (IMPROVED)
  ↓
User: "Approved. Now draft the narrative."
  ↓
Writer Persona → artifacts/02-narrative-v1.md (REVIEWABLE)
  ↓
Budget Analyst: "Lines 45-67 need budget support" (DIALOGUE)
  ↓
Writer → artifacts/02-narrative-v2.md (REVISED)
Budget Analyst → artifacts/03-budget-v1.xlsx (ALIGNED)
  ↓
User: "Both look good. Run compliance check."
  ↓
Compliance Reviewer → artifacts/04-compliance-report.md
  (Finds 2 CRITICAL issues) (CAUGHT EARLY!)
  ↓
[Fix issues]
  ↓
User: "All green. Finalize and submit."
```

**Result:** Transparent, methodical, version-controlled, quality-checked work.

---

**This pattern works for ANY domain because the fundamentals are universal:**
- Principles govern work (Constitution)
- Experts provide perspectives (Personas)
- Phases enforce quality gates (Workflow)
- Artifacts enable iteration (Version Control)
- Humans orchestrate (Decision Making)
