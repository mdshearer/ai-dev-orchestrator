# Handoff Prompt: Transform ai-dev-orchestrator into Universal Workflow Template

## Mission
Transform the existing `ai-dev-orchestrator` repository into a **universal, domain-agnostic workflow orchestration framework** that enables small teams and solo practitioners to build high-quality work in ANY domain using AI assistance with constitutional governance and specialized personas.

## Vision
The current repo proves that structured, persona-based AI workflows work brilliantly for software development. The core insight: **Constitution + Personas + Phased Workflow + Artifact-Driven Iteration = Consistent Quality**. This pattern is domain-agnostic and should work for grant writing, content creation, product design, marketing campaigns, research papers, and more.

## What Makes This Universal

### Core Pattern (Stays the Same Across Domains)
1. **Constitution** - Non-negotiable principles and standards
2. **4-6 Specialized Personas** - Experts who check and balance each other
3. **4-Phase Workflow** - Strategy → Creation → Refinement → Finalization
4. **Artifact-Driven** - Every phase produces versioned, reviewable outputs
5. **Methodical Iteration** - Version control enables transparent revisions

### What Changes Per Domain
- Constitution contents (tech stack → brand voice, security → compliance, etc.)
- Persona roles (developer → writer, QA → fact-checker, etc.)
- Prompt specifics (code review → narrative review, API design → content brief, etc.)
- Quality metrics (test coverage → readability score, performance → SEO score, etc.)

## Target Users
**Primary:** Small teams (2-10 people) in agencies, consultancies, studios, non-profits
**Secondary:** Solo practitioners (freelancers, independent consultants, entrepreneurs)
**Use Case:** Teams that need consistent quality but can't afford large specialized departments

## Project Structure

Create this new structure while preserving existing software-development content:

```
ai-workflow-orchestrator/  (rename from ai-dev-orchestrator)
│
├── README.md                           # NEW: Meta-framework intro
├── QUICKSTART.md                       # NEW: Domain selection → Setup
├── CONTRIBUTING.md                     # NEW: How to add domains
│
├── 00-core-framework/                  # NEW: Universal principles
│   ├── README.md                       # Framework overview
│   ├── universal-constitution-guide.md # How to build constitutions
│   ├── persona-pattern-guide.md        # How personas work
│   ├── workflow-patterns.md            # Linear, iterative, parallel, hybrid
│   ├── artifact-management.md          # Version control, iteration strategies
│   ├── quality-metrics-framework.md    # How to measure success per domain
│   └── cross-persona-dialogue.md       # How personas iterate together
│
├── 01-domain-libraries/                # Domain-specific implementations
│   │
│   ├── software-development/           # MIGRATE: Existing content goes here
│   │   ├── README.md                   # Domain overview
│   │   ├── CONSTITUTION.md             # Current CONSTITUTION-TEMPLATE.md
│   │   ├── personas/                   # Current personas/ folder
│   │   ├── prompts/                    # Current prompts/ folder
│   │   ├── workflow/                   # Current workflow/ folder
│   │   ├── templates/                  # Current templates/ folder
│   │   ├── examples/                   # Current examples/ folder
│   │   └── guides/                     # Current guides/ folder
│   │
│   ├── grant-writing/                  # NEW: Complete grant workflow
│   │   ├── README.md
│   │   ├── CONSTITUTION.md             # Funder requirements, compliance, style
│   │   ├── personas/
│   │   │   ├── 01-grant-strategist.md
│   │   │   ├── 02-grant-writer.md
│   │   │   ├── 03-budget-analyst.md
│   │   │   ├── 04-compliance-reviewer.md
│   │   │   └── 05-grant-editor.md
│   │   ├── prompts/
│   │   │   ├── phase-1-strategy/
│   │   │   │   ├── 1.1-rfp-analysis.md
│   │   │   │   ├── 1.2-grant-outline.md
│   │   │   │   └── 1.3-evidence-gaps.md
│   │   │   ├── phase-2-development/
│   │   │   │   ├── 2.1-narrative-sections.md
│   │   │   │   ├── 2.2-budget-development.md
│   │   │   │   └── 2.3-attachment-checklist.md
│   │   │   ├── phase-3-review/
│   │   │   │   ├── 3.1-compliance-check.md
│   │   │   │   ├── 3.2-narrative-review.md
│   │   │   │   └── 3.3-budget-validation.md
│   │   │   └── phase-4-finalization/
│   │   │       ├── 4.1-executive-summary.md
│   │   │       └── 4.2-submission-checklist.md
│   │   ├── workflow/
│   │   │   ├── workflow-overview.md
│   │   │   └── iteration-strategies.md
│   │   └── examples/
│   │       └── community-health-grant/
│   │           ├── CONSTITUTION.md
│   │           ├── artifacts/
│   │           │   ├── 01-strategy-outline.md
│   │           │   ├── 02-narrative-draft.md
│   │           │   ├── 03-budget-v2.xlsx
│   │           │   └── workflow-log.md
│   │           └── README.md
│   │
│   ├── content-writing/                # NEW: Complete content workflow
│   │   ├── README.md
│   │   ├── CONSTITUTION.md             # Brand voice, SEO, style guide
│   │   ├── personas/
│   │   │   ├── 01-content-strategist.md
│   │   │   ├── 02-content-writer.md
│   │   │   ├── 03-seo-specialist.md
│   │   │   ├── 04-fact-checker.md
│   │   │   └── 05-editor.md
│   │   ├── prompts/
│   │   │   ├── phase-1-planning/
│   │   │   │   ├── 1.1-content-brief.md
│   │   │   │   ├── 1.2-keyword-research.md
│   │   │   │   └── 1.3-outline-creation.md
│   │   │   ├── phase-2-creation/
│   │   │   │   ├── 2.1-first-draft.md
│   │   │   │   └── 2.2-media-sourcing.md
│   │   │   ├── phase-3-refinement/
│   │   │   │   ├── 3.1-seo-optimization.md
│   │   │   │   ├── 3.2-fact-checking.md
│   │   │   │   └── 3.3-editing.md
│   │   │   └── phase-4-publishing/
│   │   │       ├── 4.1-meta-optimization.md
│   │   │       └── 4.2-distribution-plan.md
│   │   ├── workflow/
│   │   │   └── workflow-overview.md
│   │   └── examples/
│   │       └── saas-blog-article/
│   │           ├── CONSTITUTION.md
│   │           ├── artifacts/
│   │           │   ├── 01-content-brief.md
│   │           │   ├── 02-draft-v3.md
│   │           │   ├── 03-seo-report.md
│   │           │   └── 04-final-published.md
│   │           └── README.md
│   │
│   └── README.md                       # Domain selection guide
│
├── 02-persona-library/                 # NEW: Build your own personas
│   ├── README.md                       # How to create custom personas
│   ├── strategist-template.md          # Fill-in-the-blank persona template
│   ├── creator-template.md
│   ├── specialist-template.md
│   ├── reviewer-template.md
│   ├── finalizer-template.md
│   └── persona-examples.md             # 10+ example personas across domains
│
├── 03-workflow-patterns/               # NEW: Different workflow structures
│   ├── README.md                       # When to use each pattern
│   ├── linear-workflow.md              # Step 1 → 2 → 3 → 4 (content, grants)
│   ├── iterative-workflow.md           # Build → Test → Revise → Repeat (design, dev)
│   ├── parallel-tracks-workflow.md     # Multiple workstreams (complex projects)
│   ├── hybrid-workflow.md              # Mix of patterns
│   └── workflow-selector.md            # Decision tree for choosing
│
├── 04-prompt-generator/                # NEW: Auto-generate domain prompts
│   ├── README.md                       # How to use the generator
│   ├── generator-guide.md              # Step-by-step instructions
│   ├── prompt-template.md              # Universal prompt structure
│   ├── variable-library.md             # Common variables by domain
│   └── examples/
│       ├── generated-grant-prompt.md
│       └── generated-design-prompt.md
│
├── 05-quality-metrics/                 # NEW: Domain-specific quality
│   ├── README.md
│   ├── software-metrics.md             # Tests, coverage, security, performance
│   ├── grant-metrics.md                # Compliance, score rubric, competitiveness
│   ├── content-metrics.md              # SEO, readability, brand alignment
│   └── custom-metrics-template.md
│
└── 06-guides/                          # NEW: Cross-cutting guides
    ├── choosing-your-domain.md
    ├── customizing-personas.md
    ├── artifact-version-control.md
    ├── iteration-strategies.md
    ├── team-collaboration.md
    └── solo-practitioner-tips.md
```

## Detailed Instructions by Section

### 1. Core Framework (00-core-framework/)

**universal-constitution-guide.md** should include:
- Template structure with fill-in-the-blanks
- Examples from all 3 domains showing same sections adapted
- Common sections: Core Principles, Standards, Constraints, Quality Criteria
- Domain-specific additions: Tech Stack (software), Funder Requirements (grants), Brand Voice (content)

**persona-pattern-guide.md** should explain:
- Why 4-6 personas (not too few, not too many)
- Common persona archetypes: Strategist, Creator, Specialist, Reviewer, Finalizer
- How to adapt archetypes to your domain
- Persona definition template with required sections

**workflow-patterns.md** should describe:
- 4 workflow patterns with visual diagrams
- Decision tree for selecting pattern
- Examples of each pattern in different domains
- How to mix patterns (hybrid approach)

**artifact-management.md** should cover:
- Naming conventions (phase-artifact-version.md)
- Version control strategies
- Cross-persona review process
- Iteration documentation
- Git integration best practices

**quality-metrics-framework.md** should provide:
- How to define "done" in your domain
- Objective vs subjective metrics
- Review checklists by phase
- How to score/prioritize issues (CRITICAL, HIGH, MEDIUM, LOW)

**cross-persona-dialogue.md** should explain:
- How personas "talk" via artifact reviews
- Review comment format in markdown
- Resolution documentation
- Example dialogues from 3 domains

### 2. Domain Libraries - Grant Writing (NEW)

**Key Differences from Software Dev:**

**Constitution Focus:**
- Funder priorities and requirements (vs tech stack)
- Compliance and eligibility rules (vs security standards)
- Writing style and tone (formal, persuasive)
- Budget constraints and allowable costs
- Submission requirements (forms, certifications, formatting)

**Personas:**
1. **Grant Strategist** - Analyzes RFP, identifies winning themes, competitive positioning
2. **Grant Writer** - Drafts narrative sections (need, methodology, evaluation, sustainability)
3. **Budget Analyst** - Creates itemized budgets, justifications, matching funds
4. **Compliance Reviewer** - Checks eligibility, required attachments, regulations, deadlines
5. **Grant Editor** - Reviews for persuasiveness, clarity, consistency, proofing

**Workflow Pattern:** Linear with iterative refinement
- Can't skip ahead (need strategy before writing)
- Heavy cross-persona review (writer ↔ budget analyst)
- Hard deadline (submission date)

**Quality Metrics:**
- Compliance checklist (100% required items)
- Score rubric alignment (0-100 based on RFP criteria)
- Competitiveness assessment (vs typical funded proposals)
- Budget justification completeness
- Evidence strength (data, citations, testimonials)

**Example Prompts to Create:**

`1.1-rfp-analysis.md`:
```markdown
You are a Grant Strategist analyzing an RFP.

**Input:** RFP document, organizational background
**Output:** artifacts/01-rfp-analysis.md

Analyze:
1. Funder priorities (rank 1-5)
2. Evaluation criteria and point values
3. Eligibility requirements
4. Required vs optional components
5. Winning themes and messaging opportunities
6. Red flags or risks

Format as structured report with recommendations.
```

`2.1-narrative-sections.md`:
```markdown
You are a Grant Writer creating narrative sections.

**Input:**
- artifacts/01-rfp-analysis.md
- CONSTITUTION.md (writing style, organizational voice)
- Evidence library (data, testimonials, research)

**Output:** artifacts/02-narrative-draft.md

Write sections:
- Statement of Need (30%)
- Project Design/Methodology (30%)
- Evaluation Plan (20%)
- Organizational Capacity (10%)
- Sustainability Plan (10%)

Use persuasive, evidence-based writing.
Align with funder priorities from RFP analysis.
```

`3.1-compliance-check.md`:
```markdown
You are a Compliance Reviewer conducting final audit.

**Input:**
- artifacts/02-narrative-draft.md
- artifacts/03-budget.xlsx
- RFP requirements checklist

**Output:** artifacts/compliance-report.md

Check:
- [ ] All required sections present
- [ ] Page/word limits met
- [ ] Required attachments included
- [ ] Eligibility criteria satisfied
- [ ] Budget math correct
- [ ] Narrative ↔ Budget alignment

Flag CRITICAL issues that would disqualify proposal.
```

**Example Artifact Workflow:**
```
01-rfp-analysis.md (Strategist)
  ↓
02-grant-outline.md (Strategist)
  ↓
03-narrative-draft-v1.md (Writer)
  ↓ (Budget Analyst reviews, finds gaps)
03-narrative-draft-v2.md (Writer addresses)
  ↓
04-budget-v1.xlsx (Budget Analyst)
  ↓ (Writer reviews, requests changes)
04-budget-v2.xlsx (Budget Analyst)
  ↓
05-compliance-report.md (Compliance Reviewer)
  ↓ (Issues found)
03-narrative-draft-v3.md + 04-budget-v3.xlsx (Revisions)
  ↓
06-executive-summary.md (Editor)
  ↓
07-submission-checklist.md (Compliance Reviewer)
```

### 3. Domain Libraries - Content Writing (NEW)

**Key Differences from Software Dev:**

**Constitution Focus:**
- Brand voice and tone guidelines (vs coding style)
- SEO requirements (keywords, meta descriptions, readability)
- Target audience definition (demographics, pain points)
- Content pillars and themes (strategic topics)
- Style guide (AP, Chicago, Oxford comma preferences)
- Publishing platform requirements (WordPress, Medium, etc.)

**Personas:**
1. **Content Strategist** - Defines topic, angle, keywords, target audience, goals
2. **Content Writer** - Creates engaging, on-brand first draft
3. **SEO Specialist** - Optimizes for search, technical SEO, internal linking
4. **Fact Checker** - Verifies claims, adds citations, ensures accuracy
5. **Editor** - Polishes voice, flow, clarity, CTA effectiveness

**Workflow Pattern:** Linear (with possible iteration between draft and editing)
- Strategy → Draft → Optimize → Publish
- Less iteration than grant writing (faster turnaround)
- Performance tracking post-publication

**Quality Metrics:**
- SEO score (keyword usage, meta tags, readability)
- Brand voice alignment (tone analyzer, vocabulary check)
- Factual accuracy (citations present, claims verified)
- Readability score (Flesch-Kincaid, grade level)
- Engagement prediction (headline analyzer, CTA clarity)

**Example Prompts to Create:**

`1.1-content-brief.md`:
```markdown
You are a Content Strategist creating a content brief.

**Input:**
- Topic/keyword
- CONSTITUTION.md (brand voice, audience, content pillars)
- Content calendar (context for series/campaigns)

**Output:** artifacts/01-content-brief.md

Include:
1. Target Audience (who, pain points, intent)
2. Primary Keyword + Secondary Keywords
3. Search Intent (informational, commercial, navigational)
4. Angle/Hook (unique perspective)
5. Outline (H2/H3 structure)
6. Internal Link Opportunities
7. CTA Strategy
8. Success Metrics (target traffic, engagement)

Align with brand content pillars.
```

`2.1-first-draft.md`:
```markdown
You are a Content Writer creating first draft.

**Input:**
- artifacts/01-content-brief.md
- CONSTITUTION.md (brand voice, style guide)

**Output:** artifacts/02-draft-v1.md

Write 1,200-1,800 words following:
- Hook readers in first 100 words
- Use brand voice (check CONSTITUTION.md)
- Include natural keyword usage
- Add subheadings per outline
- Write compelling meta description
- Include clear CTA

Prioritize clarity and engagement over keyword stuffing.
```

`3.1-seo-optimization.md`:
```markdown
You are an SEO Specialist optimizing content.

**Input:**
- artifacts/02-draft-v2.md (after edits)
- artifacts/01-content-brief.md (keyword targets)

**Output:** artifacts/03-seo-report.md + updated draft

Optimize:
- [ ] Primary keyword in title, H1, first 100 words
- [ ] Secondary keywords in H2s
- [ ] Meta description (150-160 chars, includes keyword)
- [ ] Image alt text (descriptive, includes keywords)
- [ ] Internal links (3-5 relevant articles)
- [ ] External links (2-3 authoritative sources)
- [ ] Readability score >60 (Flesch Reading Ease)
- [ ] Paragraph length <150 words
- [ ] Use of lists, bold, formatting

Flag issues, provide optimized version.
```

**Example Artifact Workflow:**
```
01-content-brief.md (Strategist)
  ↓
02-draft-v1.md (Writer)
  ↓ (Editor reviews, suggests changes)
02-draft-v2.md (Writer revises)
  ↓
03-seo-optimization-report.md (SEO Specialist)
  ↓ (SEO updates applied)
02-draft-v3.md (SEO optimized version)
  ↓
04-fact-check-report.md (Fact Checker)
  ↓ (Citations added)
02-draft-v4.md (Final version)
  ↓
05-meta-tags.md (SEO Specialist)
  ↓
06-distribution-plan.md (Strategist)
  ↓
PUBLISHED!
  ↓
07-performance-report.md (30 days later)
```

### 4. Persona Library (02-persona-library/)

**strategist-template.md** should include:
```markdown
# Persona Template: Strategist

## Fill in These Sections:

### Role Definition
[What does this strategist do in your domain?]

### Core Responsibilities
1. [Primary responsibility]
2. [Secondary responsibility]
...

### Expertise Areas
- [Domain knowledge area 1]
- [Domain knowledge area 2]
...

### When to Invoke This Persona
✅ Use when: [Trigger conditions]
❌ Don't use when: [Wrong scenarios]

### Artifacts Produced
**Primary Output:** [Main deliverable]
**Format:** [Markdown, PDF, Spreadsheet, etc.]
**Location:** artifacts/[naming convention]

### Success Criteria
✅ [Quality indicator 1]
✅ [Quality indicator 2]
...

### Common Pitfalls
❌ [What to avoid]
✅ [What to do instead]
```

Create similar templates for: Creator, Specialist, Reviewer, Finalizer

**persona-examples.md** should show 10+ examples:
- Research Strategist (for academic papers)
- Marketing Campaign Strategist
- Product Designer
- Technical Writer (different from grant/content editor)
- Data Analyst
- Video Editor
- Social Media Specialist
- Curriculum Designer
- Event Planner
- Research Methodology Specialist

Each with brief description showing how template was filled in.

### 5. Prompt Generator (04-prompt-generator/)

**generator-guide.md** should be a step-by-step wizard:
```markdown
# Prompt Generator: Step-by-Step

Answer these questions to generate a custom prompt:

## Step 1: Domain Information
1. What domain is this for? [software, grants, content, design, marketing, other]
2. If "other", describe: [___________]

## Step 2: Persona Information
3. Which persona is this prompt for? [strategist, creator, specialist, reviewer, finalizer]
4. Specific role name: [e.g., "SEO Specialist", "Budget Analyst"]

## Step 3: Workflow Phase
5. Which phase? [1-Planning, 2-Creation, 3-Review, 4-Finalization]
6. Specific task: [e.g., "Keyword Research", "Budget Validation"]

## Step 4: Inputs and Outputs
7. What artifacts does this persona READ? [list files]
8. What artifact does this persona CREATE? [single file output]
9. Output format: [Markdown, PDF, Spreadsheet, Presentation, etc.]

## Step 5: Quality Criteria
10. How do you measure success for this task?
    - Criterion 1: [___________]
    - Criterion 2: [___________]
    - Criterion 3: [___________]

## Step 6: Domain-Specific Rules
11. Any special constraints or requirements? [___________]

---

Based on your answers, here's your generated prompt:

[GENERATED PROMPT USING TEMPLATE]
```

**prompt-template.md** is the universal structure:
```markdown
# Prompt: {PERSONA_ROLE} - {TASK_NAME}

**Persona:** {ROLE_NAME}
**Phase:** {PHASE_NUMBER} - {PHASE_NAME}
**Purpose:** {ONE_SENTENCE_DESCRIPTION}

---

## When to Use This Prompt

✅ **Use when:** {TRIGGER_CONDITIONS}
❌ **Don't use when:** {WRONG_SCENARIOS}

---

## The Prompt Template

\```markdown
You are a {PERSONA_ROLE}. Your task is to {TASK_DESCRIPTION}.

**Rules:**
1. You must adhere to all principles in CONSTITUTION.md
2. {DOMAIN_SPECIFIC_RULE_1}
3. {DOMAIN_SPECIFIC_RULE_2}
4. Output must be in {FORMAT} format
5. If requirements are unclear, ASK questions before proceeding

**Input Artifacts to Read:**
- {INPUT_FILE_1}
- {INPUT_FILE_2}
- CONSTITUTION.md

**Output Artifact to Create:**
- File: artifacts/{OUTPUT_FILENAME}
- Format: {OUTPUT_FORMAT}
- Location: {DIRECTORY}

**Context:**
{CONTEXT_VARIABLES_TO_FILL}

---

**Task Details:**
{SPECIFIC_INSTRUCTIONS}

---

**Quality Checklist:**
- [ ] {QUALITY_CRITERION_1}
- [ ] {QUALITY_CRITERION_2}
- [ ] {QUALITY_CRITERION_3}
- [ ] Aligns with CONSTITUTION.md principles
- [ ] All required sections complete

\```

---

## Review Criteria

Before accepting output, verify:
1. {REVIEW_CRITERION_1}
2. {REVIEW_CRITERION_2}
3. {REVIEW_CRITERION_3}

---

## Example Output Structure

\```markdown
{SHOW_EXAMPLE_OF_EXPECTED_OUTPUT}
\```

---

## Related Prompts
- **Previous:** [{PREVIOUS_PROMPT}](./{PREVIOUS_FILE})
- **Next:** [{NEXT_PROMPT}](./{NEXT_FILE})
```

### 6. Quality Metrics (05-quality-metrics/)

**grant-metrics.md** example:
```markdown
# Quality Metrics: Grant Writing

## Phase 1: Strategy - Scoring Rubric

| Criterion | Weight | How to Measure | Target |
|-----------|--------|----------------|--------|
| RFP Alignment | 30% | Funder priorities mapped to org strengths | 90%+ |
| Competitiveness | 25% | Comparable to funded proposals | High |
| Feasibility | 20% | Realistic timeline, budget, capacity | 100% |
| Innovation | 15% | Unique approach vs typical proposals | Medium-High |
| Evidence Strength | 10% | Data, research, testimonials present | Strong |

## Phase 2: Development - Quality Checklist

### Narrative Quality
- [ ] Statement of Need: Data-driven, compelling (Score: 1-5)
- [ ] Methodology: Detailed, realistic, evidence-based (Score: 1-5)
- [ ] Evaluation: Measurable outcomes, clear methods (Score: 1-5)
- [ ] Sustainability: Concrete plan beyond grant period (Score: 1-5)

### Budget Quality
- [ ] All line items justified in narrative
- [ ] Math is correct (sum, percentages)
- [ ] Matches funder allowable costs
- [ ] Includes required cost-sharing/match
- [ ] Reasonable for proposed scope

## Phase 3: Review - Critical Issues

### CRITICAL (Must Fix)
- Eligibility requirements not met
- Required sections missing
- Budget math errors
- Page/word limits exceeded
- Deadline would be missed

### HIGH (Should Fix)
- Weak evidence in key sections
- Budget-narrative misalignment
- Missing required attachments
- Score rubric gaps (low scores)

### MEDIUM (Consider Fixing)
- Opportunities to strengthen narrative
- Additional evidence available
- Formatting improvements
- Clarity issues

## Success Metrics

### Pre-Submission
- Compliance checklist: 100% complete
- Peer review score: 85%+ (if reviewers available)
- Budget accuracy: 100%
- Estimated competitive score: 80%+ of max points

### Post-Submission
- Funded: YES/NO
- If funded: Award amount vs requested
- If declined: Reviewer feedback analysis
- Lessons learned documentation
```

Create similar detailed metrics for software and content domains.

### 7. New README.md (Root Level)

Should include:
```markdown
# AI Workflow Orchestrator

**Build high-quality work in any domain using AI with constitutional governance and specialized personas.**

## What Is This?

A meta-framework for structured AI collaboration that works across domains:
- Software Development
- Grant Writing
- Content Creation
- Product Design
- Marketing Campaigns
- Research Papers
- ...and more

## The Core Idea

Instead of asking AI to "do everything," you:
1. Define a **Constitution** (your non-negotiable principles)
2. Work with **4-6 Specialized Personas** (strategist, creator, reviewer, etc.)
3. Follow a **4-Phase Workflow** (plan → create → refine → finalize)
4. Produce **Versioned Artifacts** at each step (enables methodical iteration)

**Result:** Consistent quality, transparent process, trackable revisions.

## Who Is This For?

- **Small teams** (2-10 people) who need specialized expertise without hiring
- **Solo practitioners** who want quality checks and balanced perspectives
- **Anyone** who's frustrated with inconsistent AI outputs

## Quick Start

### 1. Choose Your Domain
- [Software Development](./01-domain-libraries/software-development/) - Apps, APIs, tools
- [Grant Writing](./01-domain-libraries/grant-writing/) - Proposals, applications
- [Content Writing](./01-domain-libraries/content-writing/) - Blogs, articles, marketing

Don't see your domain? [Build your own →](./02-persona-library/)

### 2. Copy the Constitution
```bash
cp ./01-domain-libraries/{your-domain}/CONSTITUTION.md ./your-project/
# Customize for your specific project
```

### 3. Start Your First Workflow
Follow the domain's workflow-overview.md:
- Phase 1: Planning (use strategist prompts)
- Phase 2: Creation (use creator prompts)
- Phase 3: Review (use reviewer prompts)
- Phase 4: Finalization (use finalizer prompts)

## Why This Works

### ✅ Constitutional Governance
Non-negotiable principles prevent scope creep and maintain quality

### ✅ Specialized Personas
Multiple perspectives catch issues early (like a team review)

### ✅ Artifact-Driven Progress
Every phase produces reviewable output (not just "AI said something")

### ✅ Methodical Iteration
Version control enables transparent, trackable revisions

### ✅ Domain-Agnostic Pattern
Same framework works for code, writing, design, grants, marketing

## What's Included

- **3 Complete Domain Libraries** (software, grants, content)
- **20+ Personas** (ready to use or customize)
- **4 Workflow Patterns** (linear, iterative, parallel, hybrid)
- **Prompt Generator** (create custom prompts for your domain)
- **Quality Metrics** (measure success in any domain)

## Project Structure

```
ai-workflow-orchestrator/
├── 00-core-framework/          # Universal principles
├── 01-domain-libraries/        # Ready-to-use domains
├── 02-persona-library/         # Build custom personas
├── 03-workflow-patterns/       # Choose your workflow
├── 04-prompt-generator/        # Create custom prompts
├── 05-quality-metrics/         # Measure success
└── 06-guides/                  # How-to guides
```

[Continue with examples, FAQs, etc.]
```

## Development Approach

### Phase 1: Foundation
1. Create new repository structure (keep existing as /software-development/)
2. Write all core framework docs (00-core-framework/)
3. Create persona library templates (02-persona-library/)
4. Document workflow patterns (03-workflow-patterns/)

### Phase 2: New Domains
5. Build complete grant-writing domain library
6. Build complete content-writing domain library
7. Create example workflows for each

### Phase 3: Tools & Polish
8. Create prompt generator with examples
9. Write all quality metrics docs
10. Create comprehensive guides
11. Write new root README.md
12. Write QUICKSTART.md

## Key Success Criteria

✅ Someone unfamiliar with software can understand the framework
✅ All 3 domains are equally detailed (not just software)
✅ Prompt generator produces usable prompts for new domains
✅ Examples show real artifacts with iteration history
✅ Workflow patterns clearly show when to use each
✅ Quality metrics are measurable and domain-appropriate

## Important Patterns to Preserve

From the existing ai-dev-orchestrator:
- ✅ Constitution as non-negotiable governance
- ✅ Persona-based specialization (not generic AI)
- ✅ Clear phase gates (don't skip phases)
- ✅ Artifact-driven (files, not just conversation)
- ✅ Human as orchestrator (AI provides expertise, human judges)
- ✅ Explicit over implicit (written specs, documented trade-offs)

## Target Timeline

**Phase 1 (Foundation):** 3-4 hours
**Phase 2 (New Domains):** 6-8 hours
**Phase 3 (Tools & Polish):** 4-5 hours

**Total:** 13-17 hours of focused work

## Questions to Consider During Development

1. Are the grant writing and content writing domains as detailed as software?
2. Do the persona templates make it easy to create custom personas?
3. Does the prompt generator actually work (can someone follow it)?
4. Are quality metrics specific and measurable?
5. Can a non-technical person understand and use this?
6. Do the examples show real iteration (not just final outputs)?
7. Is it clear when to use linear vs iterative workflows?

## Final Deliverables

1. Complete repository structure (all folders, all files)
2. 3 domain libraries with full personas, prompts, workflows, examples
3. Persona builder templates
4. Prompt generator
5. Quality metrics for each domain
6. Comprehensive guides
7. Root README.md and QUICKSTART.md

## Notes

- Preserve all existing software development content (just reorganize it)
- Each domain should feel equally "complete" (not software-heavy)
- Examples should show messy iteration, not just perfect outputs
- Quality metrics should be specific to domain (not generic)
- Workflow patterns should have clear decision trees
- Prompt generator should produce ready-to-use prompts

---

**Ready to build? Let's create a universal framework that transforms how people work with AI across all domains.**
