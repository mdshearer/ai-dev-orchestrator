# Implementation Plan: AI Workflow Orchestrator (New Repo)

## Project Overview

Create a new public repo `ai-workflow-orchestrator` that transforms the existing software-only framework into a **universal, domain-agnostic workflow orchestration system** for structured AI collaboration.

**Launch Scope:** 2 domains (software-development + content-writing)
**Future:** Grant-writing domain (v2)

---

## Key Decisions

✅ **Repo name:** `ai-workflow-orchestrator`
✅ **Initial domains:** Software-development (migrate existing) + Content-writing (create new)
✅ **Planning docs:** Include in `/docs/architecture/` (archived but accessible)
✅ **Approach:** Start simple, add depth incrementally
✅ **Target users:** Solo practitioners and small teams (2-10 people)

---

## New Repository Structure

```
ai-workflow-orchestrator/
│
├── README.md                          # NEW: One-pager + comparison table + quick links
├── QUICKSTART.md                      # NEW: 5-minute quick start guide
├── CONTRIBUTING.md                    # NEW: How to add domains (v2)
├── LICENSE                            # COPY: MIT License
│
├── docs/                              # NEW: Meta documentation
│   ├── architecture/                  # Archived planning docs
│   │   ├── HANDOFF-UNIVERSAL-TEMPLATE.md
│   │   ├── UNIVERSAL-PATTERN-VISUAL.md
│   │   └── DESIGN-DECISIONS.md        # NEW: ADR-style decisions
│   │
│   └── guides/                        # NEW: Cross-domain guides
│       ├── choosing-your-domain.md
│       ├── working-solo.md
│       ├── working-with-teams.md
│       └── customizing-personas.md
│
├── domains/                           # NEW: Domain-specific implementations
│   │
│   ├── README.md                      # NEW: Domain selection guide
│   │
│   ├── software-development/          # MIGRATE: Existing content
│   │   ├── README.md                  # NEW: Domain overview
│   │   ├── personas/                  # MIGRATE: Current personas/
│   │   ├── prompts/                   # MIGRATE: Current prompts/
│   │   ├── templates/                 # MIGRATE: Current templates/
│   │   ├── examples/                  # MIGRATE: Current examples/
│   │   ├── guides/                    # MIGRATE: Current guides/
│   │   └── workflow/                  # MIGRATE: Current workflow/
│   │
│   └── content-writing/               # CREATE NEW: Complete content domain
│       ├── README.md                  # Domain overview
│       ├── personas/                  # 5 personas (strategist, writer, seo, fact-checker, editor)
│       │   ├── 01-content-strategist.md
│       │   ├── 02-content-writer.md
│       │   ├── 03-seo-specialist.md
│       │   ├── 04-fact-checker.md
│       │   └── 05-editor.md
│       ├── prompts/                   # Phase-based prompts
│       │   ├── phase-1-planning/
│       │   │   ├── 1.1-content-brief.md
│       │   │   ├── 1.2-keyword-research.md
│       │   │   └── 1.3-outline-creation.md
│       │   ├── phase-2-creation/
│       │   │   ├── 2.1-first-draft.md
│       │   │   └── 2.2-media-planning.md
│       │   ├── phase-3-refinement/
│       │   │   ├── 3.1-seo-optimization.md
│       │   │   ├── 3.2-fact-checking.md
│       │   │   └── 3.3-editing.md
│       │   └── phase-4-publishing/
│       │       ├── 4.1-meta-optimization.md
│       │       └── 4.2-distribution-checklist.md
│       ├── templates/                 # Constitution templates by content type
│       │   ├── blog-constitution.md
│       │   ├── marketing-constitution.md
│       │   └── technical-constitution.md
│       ├── examples/                  # Example content projects
│       │   ├── saas-blog-post/
│       │   └── product-launch-post/
│       └── workflow/
│           └── workflow-overview.md
│
└── .github/
    └── ISSUE_TEMPLATE/
        └── new-domain-proposal.md     # For future community domains
```

---

## Implementation Phases

### Phase 1: Foundation (Priority 1)

**Create new repo structure and core docs**

#### 1.1 Root README.md
- **One-pager visual:** ASCII diagram showing Constitution → Personas → Workflow → Artifacts
- **Comparison table:** "Ad-hoc AI prompting" vs "Constitutional workflow"
- **Quick links:** Choose your domain, 5-min quick start, examples
- **Who is this for:** Solo practitioners, small teams
- **What's included:** 2 domains, 10+ personas, 25+ prompts
- **Example:** Show before/after snippet (messy AI chat vs structured artifact workflow)

#### 1.2 QUICKSTART.md (5-minute guide)
```markdown
# 5-Minute Quick Start

## 1. Choose Your Domain (30 seconds)
- [Software Development](./domains/software-development/) - Apps, APIs, tools
- [Content Writing](./domains/content-writing/) - Blogs, articles, marketing

## 2. Copy Your Constitution (1 minute)
Pick a template from your domain's `templates/` folder:
- Software: internal-tool, client-app, or ai-agent
- Content: blog, marketing, or technical

Customize for your project (name, audience, constraints).

## 3. Start Phase 1: Planning (3 minutes)
Use the first persona prompt from `prompts/phase-1-planning/1.1-*`

Example for Content Writing:
1. Copy `prompts/phase-1-planning/1.1-content-brief.md`
2. Fill in context: topic, target audience, goals
3. Give to your AI (Claude Code, Cursor, copy-paste)
4. Review output in `artifacts/01-content-brief.md`

## 4. Continue Through Phases
Phase 1 (Planning) → Phase 2 (Creation) → Phase 3 (Review) → Phase 4 (Finalization)

See your domain's `workflow/workflow-overview.md` for the full process.

## Tips for Solo Practitioners
- You invoke each persona sequentially (strategist → creator → reviewer → finalizer)
- Each persona checks the previous persona's work
- You judge which feedback to accept/reject
- Version your artifacts (brief-v1.md, brief-v2.md, etc.)
```

#### 1.3 LICENSE
Copy MIT License from current repo

#### 1.4 domains/README.md (Domain selector)
```markdown
# Choose Your Domain

## Software Development
**Best for:** Web apps, mobile apps, APIs, tools, bots

**Personas:** Product Owner, Architect, Developer, QA Engineer, Technical Writer

**Workflow:** Iterative (build → test → refactor → repeat)

**[Get Started →](./software-development/)**

---

## Content Writing
**Best for:** Blog posts, marketing content, product docs, social media

**Personas:** Content Strategist, Writer, SEO Specialist, Fact Checker, Editor

**Workflow:** Linear (plan → draft → optimize → publish)

**[Get Started →](./content-writing/)**

---

## Grant Writing (Coming Soon)
**Best for:** Foundation grants, government proposals, corporate sponsorships

**Personas:** Grant Strategist, Writer, Budget Analyst, Compliance Reviewer, Editor

**Status:** Planned for v2
```

---

### Phase 2: Migrate Software-Development Domain (Priority 1)

**Copy and reorganize existing content**

#### 2.1 Copy Files
From `ai-dev-orchestrator` to `ai-workflow-orchestrator/domains/software-development/`:
- `personas/` → `personas/` (all 5 persona files + README)
- `prompts/` → `prompts/` (all phase folders + 16 prompts)
- `templates/` → `templates/` (3 constitution templates + README)
- `examples/` → `examples/` (3 example projects + sample outputs + README)
- `guides/` → `guides/` (3 tool setup guides)
- `workflow/` → `workflow/` (3 workflow docs)
- `quick-start/` → `quick-start/` (3 quick start docs - or integrate into main QUICKSTART.md)

#### 2.2 Create software-development/README.md
```markdown
# Software Development Domain

Build production-ready software using AI with constitutional governance and specialized personas.

## What's Included
- **5 Personas:** Product Owner, Architect, Developer, QA, Technical Writer
- **16 Prompts:** Organized across 5 phases
- **3 Constitution Templates:** Internal tool, Client app, AI agent
- **3 Complete Examples:** Expense tracker, SaaS dashboard, Slack bot

## Quick Start
1. Choose a constitution template from `templates/`
2. Start with Phase 1: [Product Owner PRD](./prompts/phase-1-planning/1.1-product-owner-prd.md)
3. Follow the [Workflow Overview](./workflow/workflow-overview.md)

## Personas Overview
| # | Persona | Responsibility | When to Use |
|---|---------|----------------|-------------|
| 1 | Product Owner | Defines WHAT and WHY | Start of every project |
| 2 | Solutions Architect | Defines HOW | After PRD approved |
| 3 | Developer | Implements solution | After tech spec approved |
| 4 | QA Engineer | Validates quality | After implementation done |
| 5 | Technical Writer | Documents solution | After QA passes |

[View All Personas →](./personas/)

## Workflow
Phase 0: Complexity estimation
Phase 1: Planning (PRD → Tech Spec → Schema → API)
Phase 2: Implementation (Task list → Iterative coding)
Phase 3: Review (QA audit → Security → Refactoring)
Phase 4: Documentation (README → User guides)

[View Workflow Details →](./workflow/workflow-overview.md)
```

#### 2.3 Update Internal Links
Ensure all links within software-development/ docs point to correct relative paths

---

### Phase 3: Create Content-Writing Domain (Priority 1)

**Build complete content-writing domain mirroring software structure**

#### 3.1 Create content-writing/README.md
Similar structure to software-development/README.md but for content domain

#### 3.2 Create 5 Personas (content-writing/personas/)

**Based on HANDOFF doc specifications:**

1. **01-content-strategist.md**
   - Role: Topic selection, audience definition, keyword research, content brief creation
   - Outputs: Content brief, keyword strategy, outline structure
   - Example sections: Role Definition, Core Responsibilities, When to Invoke, Artifacts Produced, Success Criteria

2. **02-content-writer.md**
   - Role: First draft creation, storytelling, brand voice adherence
   - Outputs: Article draft (v1, v2, etc.)
   - Focus: Engagement, clarity, natural keyword usage

3. **03-seo-specialist.md**
   - Role: Keyword optimization, meta tags, readability, internal linking
   - Outputs: SEO report, optimized draft
   - Metrics: SEO score, keyword density, readability score

4. **04-fact-checker.md**
   - Role: Verify claims, add citations, ensure accuracy
   - Outputs: Fact-check report, corrected draft
   - Focus: Credibility, authoritative sources

5. **05-editor.md**
   - Role: Polish voice, flow, clarity, CTA effectiveness
   - Outputs: Final polished draft, publishing checklist
   - Focus: Brand consistency, reader experience

Each persona follows same template structure as software personas (~8-12 KB each)

#### 3.3 Create Phase-Based Prompts (content-writing/prompts/)

**12 prompts across 4 phases:**

**Phase 1: Planning**
- `1.1-content-brief.md` - Content Strategist creates brief (topic, audience, keywords, angle, outline)
- `1.2-keyword-research.md` - SEO Specialist researches keywords and search intent
- `1.3-outline-creation.md` - Content Strategist creates H2/H3 structure

**Phase 2: Creation**
- `2.1-first-draft.md` - Content Writer creates 1200-1800 word draft following outline
- `2.2-media-planning.md` - Content Strategist identifies image/video opportunities

**Phase 3: Refinement**
- `3.1-seo-optimization.md` - SEO Specialist optimizes keywords, meta, readability
- `3.2-fact-checking.md` - Fact Checker verifies claims and adds citations
- `3.3-editing.md` - Editor polishes voice, flow, clarity

**Phase 4: Publishing**
- `4.1-meta-optimization.md` - SEO Specialist creates meta title/description, alt text
- `4.2-distribution-checklist.md` - Content Strategist creates distribution plan

Each prompt follows universal prompt structure from UNIVERSAL-PATTERN-VISUAL.md:
- When to Use
- The Prompt (with Rules, Input Artifacts, Output Artifact, Context, Quality Checklist)
- Review Criteria
- Example Output Structure

#### 3.4 Create Constitution Templates (content-writing/templates/)

**3 templates by content type:**

1. **blog-constitution.md**
   - Target: Company blogs, thought leadership, SEO content
   - Principles: Brand voice, SEO standards, readability targets
   - Constraints: Word count ranges, keyword requirements, publishing frequency

2. **marketing-constitution.md**
   - Target: Landing pages, email campaigns, sales content
   - Principles: Conversion focus, brand alignment, CTA requirements
   - Constraints: Character limits, A/B testing requirements, compliance

3. **technical-constitution.md**
   - Target: Product docs, API guides, technical tutorials
   - Principles: Accuracy, clarity, code examples
   - Constraints: Technical accuracy, version control, audience skill level

Each template includes:
- Project Identity (name, audience, purpose)
- Core Principles (3-5 non-negotiables)
- Standards (quality bars)
- Constraints (limitations)
- Success Metrics (how to measure done)

#### 3.5 Create Examples (content-writing/examples/)

**2 complete example projects:**

1. **saas-blog-post/** (Example: "How to Choose Project Management Software")
   - `CONSTITUTION.md` - Blog constitution (SEO-focused, 1500 words, B2B SaaS)
   - `artifacts/01-content-brief.md` - Completed brief with keywords, outline
   - `artifacts/02-draft-v1.md` - First draft from writer
   - `artifacts/02-draft-v2.md` - After SEO optimization
   - `artifacts/03-fact-check-report.md` - Fact checker findings
   - `artifacts/02-draft-v3.md` - Final version after edits
   - `artifacts/04-meta-tags.md` - Meta title, description, alt text
   - `artifacts/workflow-log.md` - Shows iteration history and cross-persona dialogue
   - `README.md` - Explains the project and key decisions

2. **product-launch-post/** (Example: "Introducing [New Feature]")
   - Similar structure
   - Shows marketing-focused content with conversion goals
   - Demonstrates tighter constraints (word count, CTA requirements)

#### 3.6 Create Workflow Docs (content-writing/workflow/)

- `workflow-overview.md` - Visual diagram and phase descriptions for content domain

---

### Phase 4: Documentation & Guides (Priority 2)

#### 4.1 Create docs/guides/
- `choosing-your-domain.md` - Decision guide (flow chart: need software? content? grant?)
- `working-solo.md` - How solo practitioners use personas, avoid bias, version artifacts
- `working-with-teams.md` - How teams assign personas to people, collaboration tips
- `customizing-personas.md` - How to adapt personas for your needs

#### 4.2 Create docs/architecture/
Copy from current repo:
- `HANDOFF-UNIVERSAL-TEMPLATE.md`
- `UNIVERSAL-PATTERN-VISUAL.md`

Create new:
- `DESIGN-DECISIONS.md` - Why this structure, key trade-offs, future directions

---

### Phase 5: GitHub & Community Setup (Priority 3)

#### 5.1 Create .github/ISSUE_TEMPLATE/
- `new-domain-proposal.md` - Template for proposing new domains (grant-writing, marketing, design, etc.)

#### 5.2 Create CONTRIBUTING.md
- How to propose new domains
- Quality standards for domain submissions
- Persona template requirements
- Prompt structure requirements

---

## Content Writing Domain - Detailed Specs

### Persona Template Structure (for all 5 personas)

```markdown
# {Persona Name}

## Role Definition
[2-3 sentences: What this persona does in content creation]

## Core Responsibilities
1. [Primary responsibility]
2. [Secondary responsibility]
3. [Tertiary responsibility]

## Expertise Areas
- [Domain knowledge 1]
- [Domain knowledge 2]
- [Domain knowledge 3]

## When to Invoke This Persona

✅ **Use when:**
- [Trigger condition 1]
- [Trigger condition 2]

❌ **Don't use when:**
- [Wrong scenario 1]
- [Wrong scenario 2]

## Input Artifacts (What This Persona Reads)
- `CONSTITUTION.md` - Project principles and standards
- [Other artifacts from previous phases]

## Output Artifacts (What This Persona Creates)
- **Primary:** `artifacts/{filename}.md`
- **Format:** Markdown / Report / Checklist
- **Contents:** [Description of what goes in the output]

## Success Criteria

This persona's work is successful when:
✅ [Quality indicator 1]
✅ [Quality indicator 2]
✅ [Quality indicator 3]
✅ Aligns with all CONSTITUTION.md principles

## Quality Checklist

Before considering this persona's work complete:
- [ ] [Specific criterion 1]
- [ ] [Specific criterion 2]
- [ ] [Specific criterion 3]
- [ ] Constitutional alignment verified
- [ ] Ready for next persona

## Common Pitfalls

❌ **Pitfall:** [What to avoid]
✅ **Instead:** [What to do]

❌ **Pitfall:** [What to avoid]
✅ **Instead:** [What to do]

## Example Workflow

### Input:
```
[Show example input]
```

### Process:
[Step-by-step what the persona does]

### Output:
```
[Show example output structure]
```

## Related Personas
- **Previous:** [{Previous Persona}](./0X-previous.md) - [Why you need their output]
- **Next:** [{Next Persona}](./0X-next.md) - [What they'll do with your output]
```

---

## README.md - One-Pager Design

### Section 1: Visual Hook (Top of README)

```markdown
# AI Workflow Orchestrator

**Build high-quality work in any domain using AI with constitutional governance and specialized personas.**

```
┌─────────────────────────────────────────┐
│         YOUR CONSTITUTION               │
│    (Non-negotiable principles)          │
└─────────────────────────────────────────┘
                  ↓
┌─────────────────────────────────────────┐
│     4-6 SPECIALIZED PERSONAS            │
│  (Each checks the others' work)         │
└─────────────────────────────────────────┘
                  ↓
┌─────────────────────────────────────────┐
│       4-PHASE WORKFLOW                  │
│  Plan → Create → Review → Finalize      │
└─────────────────────────────────────────┘
                  ↓
┌─────────────────────────────────────────┐
│      VERSIONED ARTIFACTS                │
│   (Reviewable, trackable outputs)       │
└─────────────────────────────────────────┘
```

**Current Domains:** Software Development | Content Writing
**Coming Soon:** Grant Writing

---

## The Problem

**Traditional AI workflow:**
```
You: "Build me a landing page"
AI: [Generates 500 lines of code]
You: [Overwhelmed, can't iterate methodically]
```

**Constitutional workflow:**
```
You: "Build me a landing page. Start with product requirements."
Product Owner Persona → artifacts/01-prd.md (REVIEWABLE)

You: "Good, but emphasize conversion more."
Product Owner → artifacts/01-prd-v2.md (IMPROVED)

You: "Approved. Now create the technical design."
Architect Persona → artifacts/02-tech-spec.md (STRUCTURED)

[Continue through phases...]

Result: Transparent, methodical, version-controlled work
```

---

## Who Is This For?

✅ **Solo practitioners** who want quality checks without a team
✅ **Small teams (2-10 people)** who need specialized expertise without hiring
✅ **Anyone frustrated** with inconsistent AI outputs

---

## What's Included

- **2 Complete Domains** (software dev + content writing)
- **10+ Specialized Personas** (ready to use or customize)
- **25+ Phase-Based Prompts** (strategic, creation, review, finalization)
- **6+ Constitution Templates** (by project type)
- **5+ Example Projects** (with iteration history)

---

## Quick Start

### 1. [Choose Your Domain](./domains/)
- Software Development - Apps, APIs, tools
- Content Writing - Blogs, marketing, docs

### 2. [5-Minute Quick Start](./QUICKSTART.md)
Get up and running in 5 minutes

### 3. See Examples
- [Software: SaaS Dashboard](./domains/software-development/examples/client-app/)
- [Content: SaaS Blog Post](./domains/content-writing/examples/saas-blog-post/)
```

### Section 2: Comparison Table

```markdown
## Why This Works

| Approach | Traditional AI Prompting | Constitutional Workflow |
|----------|-------------------------|------------------------|
| **Process** | Ad-hoc, one-shot prompts | Structured 4-phase workflow |
| **Quality Control** | You catch all issues | Multiple personas review each other |
| **Iteration** | Re-prompt from scratch | Version-controlled artifacts (v1, v2, v3) |
| **Governance** | Implicit rules in prompts | Explicit CONSTITUTION.md file |
| **Transparency** | Chat history only | Reviewable artifact files |
| **Specialization** | Generic AI | Specialized personas (strategist, creator, reviewer) |
| **Accountability** | Hard to track decisions | Documented iteration history |
| **Team Collaboration** | Copy-paste chaos | Shared constitution + artifacts |

**Result:** Consistent quality, methodical iteration, transparent process
```

---

## Critical Files to Reference

When building content-writing domain, use these as templates:

**From current repo (software-development):**
- `/personas/01-product-owner.md` - Template for persona structure (~6 KB)
- `/personas/02-solutions-architect.md` - Template with more detail (~9 KB)
- `/prompts/phase-1-planning/1.1-product-owner-prd.md` - Prompt structure example
- `/templates/blog-constitution.md` - Constitution template structure
- `/examples/client-app/` - Example project with artifacts
- `/workflow/workflow-overview.md` - Workflow visualization

**From planning docs:**
- `HANDOFF-UNIVERSAL-TEMPLATE.md` lines 99-177 - Content writing personas and prompts
- `HANDOFF-UNIVERSAL-TEMPLATE.md` lines 337-462 - Detailed content writing specs
- `UNIVERSAL-PATTERN-VISUAL.md` lines 77-89 - Domain translation matrix

---

## Key Principles to Preserve

From existing ai-dev-orchestrator:

1. **Constitution as governance** - Non-negotiable principles prevent scope creep
2. **Persona-based specialization** - Not generic AI, specific expert roles
3. **Clear phase gates** - Don't skip phases (plan before building)
4. **Artifact-driven** - Files, not just conversation
5. **Human as orchestrator** - AI provides expertise, human judges
6. **Explicit over implicit** - Written specs, documented trade-offs

---

## Success Criteria

✅ Someone non-technical can understand the framework
✅ Both domains (software + content) are equally detailed
✅ 5-minute quick start actually takes 5 minutes
✅ Examples show real iteration (v1 → v2 → v3)
✅ README comparison table clearly shows value prop
✅ Solo practitioners have clear workflow

---

## Implementation Order

### Must Have (V1 Launch)
1. ✅ Root README with one-pager + comparison table
2. ✅ QUICKSTART.md (5-minute guide)
3. ✅ domains/README.md (domain selector)
4. ✅ software-development/ (migrate all existing content)
5. ✅ content-writing/ (5 personas, 12 prompts, 3 templates, 2 examples)

### Should Have (V1.1)
6. ✅ docs/guides/ (4 cross-domain guides)
7. ✅ docs/architecture/ (planning docs archived)
8. ✅ .github/ issue templates

### Nice to Have (V2)
9. ⏳ grant-writing domain (5 personas, 12 prompts, 3 templates, 2 examples)
10. ⏳ CONTRIBUTING.md (community domain proposals)
11. ⏳ More examples showing messy iteration

---

## Estimated Effort

**Phase 1 (Foundation):** 2-3 hours
- Root README, QUICKSTART, domain selector, LICENSE

**Phase 2 (Software Migration):** 1-2 hours
- Copy files, create domain README, update links

**Phase 3 (Content Domain):** 6-8 hours
- 5 personas (~2 hours)
- 12 prompts (~3 hours)
- 3 templates (~1 hour)
- 2 examples with artifacts (~2 hours)

**Phase 4 (Docs & Guides):** 2-3 hours
- Cross-domain guides, architecture docs

**Phase 5 (GitHub Setup):** 1 hour
- Issue templates, contribution guidelines

**Total for V1:** 12-17 hours

---

## Next Steps After Plan Approval

1. Create new repo `ai-workflow-orchestrator` on GitHub
2. Initialize with README stub and LICENSE
3. Execute Phase 1 (Foundation files)
4. Execute Phase 2 (Software migration)
5. Execute Phase 3 (Content domain creation)
6. Execute Phase 4 (Documentation)
7. Execute Phase 5 (GitHub setup)
8. Final review and polish
9. Public launch

---

## Open Questions

None - all clarifications received:
- ✅ Repo name: ai-workflow-orchestrator
- ✅ Initial scope: Software + Content (2 domains)
- ✅ Planning docs: Include in /docs/architecture/
- ✅ Approach: Start simple, depth later
