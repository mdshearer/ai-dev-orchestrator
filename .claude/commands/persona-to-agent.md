# Persona to Agent Converter

Convert persona definitions into Claude subagent files that can be invoked as specialized agents.

## Your Task

Scan the current repository for persona or workflow definitions, then generate Claude subagent files in `.claude/agents/`.

## Process

### Step 1: Discover Persona Definitions

Search for persona definitions in common locations:
- `personas/` directory
- `prompts/` directory
- `agents/` directory (if not already Claude agents)
- `workflows/` directory
- Any markdown files with "persona", "agent", or "role" in the name

Use Glob and Grep to find:
```
**/persona*.md
**/agent*.md
**/prompts/**/*.md
**/workflows/**/*.md
```

### Step 2: Analyze Structure

For each potential persona file found, identify:
- **Name**: The persona/agent name (e.g., "Strategist", "Researcher")
- **Role**: What this persona does
- **Phase**: Where in the workflow it operates (if applicable)
- **Inputs**: What files/context it needs
- **Outputs**: What artifact it produces
- **Rules/Constraints**: Key rules it must follow

### Step 3: Present Findings

Show the user what was found:

```
Found [N] potential personas:

1. [Name] - [Brief description]
   Source: [file path]

2. [Name] - [Brief description]
   Source: [file path]
```

Ask which ones to convert (default: all).

### Step 4: Generate Agent Files

For each selected persona, create a file in `.claude/agents/[name].md` with this structure:

```markdown
# [Name] Agent

You are the **[Name]** persona. [One-sentence role description].

## Your Role

**Phase:** [Phase name or N/A]
**Analog:** [Real-world role analog]
**Output:** [Primary output file]

[2-3 sentence description of core purpose]

---

## Core Responsibilities

1. **[Responsibility 1]** - [Description]
2. **[Responsibility 2]** - [Description]
3. **[Responsibility 3]** - [Description]
[etc.]

---

## Critical Rules

1. **[Rule 1]** - [Details]
2. **[Rule 2]** - [Details]
[Extract key rules from source material]

---

## Input Requirements

**Required Files:**
- [file1.md] - [Purpose]
- [file2.md] - [Purpose]

**Optional Files:**
- [file3.md] - [When needed]

---

## Output Format

Create a file named `[output-filename].md` with this structure:

[Include template/schema from source, or generate appropriate one]

---

## Quality Checklist

Before completing, verify:

- [ ] [Checkpoint 1]
- [ ] [Checkpoint 2]
- [ ] [Checkpoint 3]

---

## Handoff

When complete, [describe handoff to next persona/step if applicable].

---

*[Any closing reminder or key principle]*
```

### Step 5: Adapt to Context

When generating agents, look for repo-specific context:
- **CLAUDE.md** or **README.md** - For project context
- **EDITORIAL-CONSTITUTION.md** or similar - For governance rules
- **templates/** - For output schemas
- **voice-samples/** or **examples/** - For style reference

Reference these in the agent files where relevant.

### Step 6: Create Directory and Files

1. Create `.claude/agents/` if it doesn't exist
2. Write each agent file
3. Report what was created

### Step 7: Offer Next Steps

After creating agents, offer:
- "Commit these files?"
- "Create an orchestrator/workflow agent?"
- "Add to .claude/settings.json?"

---

## Customization Options

If the user provides arguments, use them:

- `/persona-to-agent personas/` - Only scan specific directory
- `/persona-to-agent --include-constitution` - Embed governance doc in each agent
- `/persona-to-agent researcher,writer` - Only convert specific personas

---

## Example Transformations

### Input: A prompt template file

```markdown
# Prompt: Researcher - Gather Facts

You are a researcher. Find verified data...

**Rules:**
1. All stats need sources
2. No fabrication

**Output:** research-dossier.md
```

### Output: Agent definition

```markdown
# Researcher Agent

You are the **Researcher** persona. Your role is to gather verified facts and data.

## Your Role
**Output:** `research-dossier.md`

## Core Responsibilities
1. **Find Verified Data** - All statistics must have source URLs
2. **No Fabrication** - Mark unverified claims as [UNVERIFIED]

## Output Format
Create `research-dossier.md` with verified data points...

[etc.]
```

---

## Key Principles

1. **Preserve Intent** - Capture the original persona's purpose
2. **Make Self-Contained** - Each agent should work independently
3. **Include Context** - Reference repo-specific files where relevant
4. **Enable Handoffs** - Describe how to pass work to next agent
5. **Add Quality Gates** - Include checklists for self-validation
