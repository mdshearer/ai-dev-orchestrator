# Claude Code Setup Guide for AI-Dev-Orchestrator

[Claude Code](https://code.claude.com) is Anthropic's official CLI tool for Claude. It's powerful for developers who prefer command-line workflows and want deep integration with their terminal.

## Installation

### macOS/Linux
```bash
brew install anthropics/claude-code/claude-code
```

Or use the installer:
```bash
curl -fsSL https://code.claude.com/install.sh | sh
```

### Windows
Download from [code.claude.com](https://code.claude.com) or use:
```powershell
winget install Anthropic.ClaudeCode
```

### Verify Installation
```bash
claude --version
```

## Authentication

1. **Get your API key**:
   - Visit [console.anthropic.com](https://console.anthropic.com)
   - Create an API key
   - Copy it

2. **Configure Claude Code**:
   ```bash
   claude auth
   ```
   - Paste your API key when prompted

## Project Setup

### Quick Start (Beginners)

For your first few features, set up minimal framework:

1. **Navigate to your project**:
   ```bash
   cd ~/my-project
   ```

2. **Initialize Claude Code** (if not already):
   ```bash
   claude init
   ```

3. **Create framework directory**:
   ```bash
   mkdir -p ai-framework/quick-start
   ```

4. **Copy Quick Start files**:
   ```bash
   # Adjust path to where you cloned ai-dev-orchestrator
   cp -r ~/ai-dev-orchestrator/quick-start/* ./ai-framework/quick-start/
   cp ~/ai-dev-orchestrator/CONSTITUTION-TEMPLATE.md ./ai-framework/
   ```

5. **Customize your Constitution**:
   ```bash
   cp ai-framework/CONSTITUTION-TEMPLATE.md CONSTITUTION.md
   # Edit CONSTITUTION.md with your preferred editor
   ```

### Standard Flow (Intermediate)

For the 8-file core workflow:

```bash
mkdir -p ai-framework/prompts ai-framework/personas

# Copy prompts
cp -r ~/ai-dev-orchestrator/prompts/phase-1-planning ./ai-framework/prompts/
cp -r ~/ai-dev-orchestrator/prompts/phase-2-implementation ./ai-framework/prompts/
cp -r ~/ai-dev-orchestrator/prompts/phase-3-review ./ai-framework/prompts/

# Copy personas
cp ~/ai-dev-orchestrator/personas/product-owner.md ./ai-framework/personas/
cp ~/ai-dev-orchestrator/personas/solutions-architect.md ./ai-framework/personas/
cp ~/ai-dev-orchestrator/personas/qa-engineer.md ./ai-framework/personas/

# Copy Constitution template
cp ~/ai-dev-orchestrator/CONSTITUTION-TEMPLATE.md CONSTITUTION.md
```

### Full Framework (Advanced)

For production systems with all features:

```bash
# Copy entire framework
cp -r ~/ai-dev-orchestrator ./ai-framework

# Customize Constitution
cp ./ai-framework/CONSTITUTION-TEMPLATE.md CONSTITUTION.md
```

## Integration with CLAUDE.md

Claude Code looks for a `CLAUDE.md` file in your project root for context. This is perfect for ai-dev-orchestrator.

### Create Your CLAUDE.md

```bash
touch CLAUDE.md
```

**Example CLAUDE.md** (Quick Start):
```markdown
# Project: My Awesome App

## AI Development Framework

This project uses [ai-dev-orchestrator](https://github.com/yourusername/ai-dev-orchestrator) for AI-driven development.

### Key Files

- **CONSTITUTION.md**: Project coding standards, tech stack, security requirements
- **ai-framework/quick-start/**: Beginner-friendly workflow (PRD → Tasks → Implementation)

### Workflow

When building features, follow this process:

1. **Create PRD**: Reference `ai-framework/quick-start/simple-workflow.md`
2. **Generate Tasks**: Reference `ai-framework/quick-start/process-task-list.md`
3. **Implement**: One sub-task at a time, mark complete [x] immediately

### Important Rules

- **Always reference CONSTITUTION.md** for coding standards
- **One task at a time**: Never implement multiple sub-tasks without approval
- **Mark complete immediately**: Update task list after each sub-task
- **Test frequently**: Run tests after every 2-3 sub-tasks

## Tech Stack

[List your stack here - will be referenced from CONSTITUTION.md]

## Current Feature

[Update this section when starting a new feature]

Working on: User Authentication
- PRD: `docs/prds/user-auth-prd.md`
- Tasks: `docs/user-auth-tasks.md`
- Status: Implementing task 2.3 (Login API endpoint)
```

**Example CLAUDE.md** (Full Framework):
```markdown
# Project: Enterprise App

## AI Development Framework

This project uses the full [ai-dev-orchestrator](https://github.com/yourusername/ai-dev-orchestrator) framework.

### Framework Files

- **CONSTITUTION.md**: Project constitution (coding standards, tech stack, security)
- **ai-framework/prompts/**: 15+ specialized prompts for all phases
- **ai-framework/personas/**: 5 specialized AI personas
- **ai-framework/workflow/**: Workflow guides and selection tools

### Development Process

#### Phase 1: Planning
1. **PRD**: `ai-framework/prompts/phase-1-planning/1.1-product-owner-prd.md`
2. **Tech Spec**: `ai-framework/prompts/phase-1-planning/1.2-architect-tech-spec.md`
3. **Database Design** (if needed): `ai-framework/prompts/phase-1-planning/1.3-architect-database-design.md`
4. **API Design** (if needed): `ai-framework/prompts/phase-1-planning/1.4-architect-api-design.md`

#### Phase 2: Implementation
5. **Task List**: `ai-framework/prompts/phase-2-implementation/2.1-generate-task-list.md`
6. **Iterative Implementation**: `ai-framework/prompts/phase-2-implementation/2.2-iterative-implementation.md`

#### Phase 3: Review
7. **QA Review**: `ai-framework/prompts/phase-3-review/3.1-qa-comprehensive-review.md`
8. **Security Review** (if needed): `ai-framework/prompts/phase-3-review/3.2-security-focused-review.md`

#### Phase 4: Documentation
9. **README**: `ai-framework/prompts/phase-4-documentation/4.1-readme-generator.md`

### Important Rules

- Reference CONSTITUTION.md for all implementation decisions
- Use interactive mode for task generation (parent tasks first, then sub-tasks)
- Implement one sub-task at a time
- Run full test suite before marking parent tasks complete
- Commit after each completed parent task

## Current Sprint

[Update this section for the current work]

Feature: Payment Integration
- PRD: `docs/prds/payment-integration-prd.md`
- Tech Spec: `docs/payment-integration-tech-spec.md`
- Tasks: `docs/payment-integration-tasks.md`
- Status: Parent task 3 (API endpoints) - sub-task 3.2
```

## GitHub Integration & PR Comments

Claude Code integrates with the GitHub CLI (`gh`) to post comments and reviews directly to pull requests. This is essential for collaborative development.

### Prerequisites

1. **Install GitHub CLI**:
   ```bash
   # macOS
   brew install gh

   # Linux
   sudo apt install gh  # Debian/Ubuntu
   sudo dnf install gh  # Fedora

   # Windows
   winget install GitHub.cli
   ```

2. **Authenticate with GitHub**:
   ```bash
   gh auth login
   ```

### Posting PR Comments

Claude Code can automatically add comments to PRs using these commands:

```bash
# Add a general comment to a PR
gh pr comment <PR_NUMBER> --body "Your comment here"

# Add a code review with comments
gh pr review <PR_NUMBER> --comment --body "Review comments here"

# Approve a PR with comments
gh pr review <PR_NUMBER> --approve --body "LGTM! Approved with notes..."

# Request changes
gh pr review <PR_NUMBER> --request-changes --body "Please address these issues..."
```

### PR Review Workflow

When reviewing or creating PRs, Claude Code should:

1. **Analyze the changes**: `gh pr diff <PR_NUMBER>`
2. **Check PR details**: `gh pr view <PR_NUMBER>`
3. **Post structured review**: Use the format below

**Standard PR Comment Format:**
```markdown
## Code Review Summary

### Overview
[Brief description of what this PR does]

### Findings

#### Strengths
- [What was done well]

#### Issues Found
| Severity | File | Line | Issue | Suggestion |
|----------|------|------|-------|------------|
| 🔴 CRITICAL | `file.py` | 45 | Description | Fix suggestion |
| 🟠 HIGH | `file.py` | 67 | Description | Fix suggestion |
| 🟡 MEDIUM | `file.py` | 89 | Description | Fix suggestion |

### Recommendation
[APPROVE / REQUEST CHANGES / COMMENT]
```

### Configuring Claude Code to Always Comment on PRs

To ensure Claude Code always adds PR comments, add this to your project's `CLAUDE.md`:

```markdown
## PR Review Requirements

When working on pull requests:
1. ALWAYS post a review comment using `gh pr review` or `gh pr comment`
2. Use the standard review format (see ai-framework/guides/claude-code-setup.md)
3. Include specific file:line references for all issues
4. Categorize issues by severity (CRITICAL, HIGH, MEDIUM, LOW)
```

Or add to your global Claude configuration (see "Global Configuration" section below).

---

## Custom Commands (Slash Commands)

Claude Code supports custom slash commands. Create shortcuts for ai-dev-orchestrator workflows.

### Create .claude/commands Directory

```bash
mkdir -p .claude/commands
```

### Example Commands

**File: `.claude/commands/quick-prd.md`**
```markdown
Help me create a PRD following the quick start workflow.

Reference:
- CONSTITUTION.md (for tech stack and standards)
- ai-framework/quick-start/simple-workflow.md (for PRD format)

Ask me clarifying questions about:
- What problem this feature solves
- Who will use it
- What "done" looks like

Keep it simple - 3-5 core user stories max.
```

**File: `.claude/commands/generate-tasks.md`**
```markdown
Generate a task list for the current feature.

Reference:
- ai-framework/quick-start/process-task-list.md (for task format)
- The most recent PRD in docs/prds/
- CONSTITUTION.md (for technical context)

Use interactive mode:
1. Generate 5-7 parent tasks
2. Show them to me
3. Wait for "Go"
4. Then generate detailed sub-tasks

Format with checkboxes: - [ ] for incomplete, - [x] for complete
```

**File: `.claude/commands/implement-task.md`**
```markdown
Implement the next pending sub-task from the current task list.

Reference:
- The current task list in docs/ (find the most recent *-tasks.md file)
- CONSTITUTION.md (for coding standards)

Process:
1. Identify the next [ ] sub-task
2. Implement ONLY that sub-task
3. Mark it [x] when complete
4. Update the task list file
5. Ask: "Sub-task X.Y complete. Ready for X.Y+1?"

Do NOT implement multiple sub-tasks without asking.
```

**File: `.claude/commands/review-feature.md`**
```markdown
Review the feature I just implemented.

Reference:
- ai-framework/prompts/phase-3-review/3.1-qa-comprehensive-review.md
- CONSTITUTION.md (for standards compliance)
- The most recent task list in docs/ (to know what was implemented)

Check for:
- Bugs and edge cases
- Security vulnerabilities
- Performance issues
- Code quality and standards
- Missing tests
```

**File: `.claude/commands/pr-review.md`**
```markdown
Review the current PR and post a comment to GitHub.

Steps:
1. Get PR details: `gh pr view`
2. Get PR diff: `gh pr diff`
3. Analyze changes against CONSTITUTION.md
4. Review across 5 dimensions (quality, bugs, performance, readability, security)
5. Post review using `gh pr review` with the standard format

Output format for PR comment:
## Code Review Summary

### Overview
[Brief description of changes]

### Findings

#### Strengths
- [What was done well]

#### Issues Found
| Severity | File | Line | Issue | Suggestion |
|----------|------|------|-------|------------|
| [emoji] | `file` | line | desc | fix |

### Recommendation
[APPROVE / REQUEST CHANGES / COMMENT]

IMPORTANT: You MUST post this review to GitHub using `gh pr review --comment --body "..."` or `gh pr comment --body "..."`
```

**File: `.claude/commands/pr-comment.md`**
```markdown
Add a comment to the current PR summarizing work done.

Steps:
1. Get current PR: `gh pr view`
2. Summarize the changes made in this session
3. Post comment using `gh pr comment --body "..."`

Include:
- What was implemented/fixed
- Files changed
- Any follow-up items or notes for reviewers
```

### Using Custom Commands

In your Claude Code session:

```bash
# Start a new feature
claude chat /quick-prd

# Generate task list
claude chat /generate-tasks

# Implement tasks iteratively
claude chat /implement-task

# Review when done
claude chat /review-feature
```

## Recommended Workflows

### Workflow 1: Quick Start Feature

```bash
# Navigate to project
cd ~/my-project

# Start Claude Code
claude chat

# Step 1: Create PRD
You: I want to build [feature description].
     Reference CONSTITUTION.md and ai-framework/quick-start/simple-workflow.md
     to help me create a PRD.

# Step 2: Generate tasks
You: Using ai-framework/quick-start/process-task-list.md, generate a task list.
     Use interactive mode.

AI: [Generates parent tasks]
    Ready for sub-tasks? Reply "Go"

You: Go

AI: [Generates sub-tasks]

# Step 3: Implement
You: Implement sub-task 1.1 only. Reference CONSTITUTION.md.
     Mark [x] when complete.

AI: [Implements, marks complete]

You: Ready for 1.2

# Repeat step 3 for all sub-tasks
```

### Workflow 2: Standard (With Tech Spec)

```bash
claude chat

# Create PRD
You: Using ai-framework/prompts/phase-1-planning/1.1-product-owner-prd.md
     and CONSTITUTION.md, help me create a PRD for [feature]

# Create Tech Spec
You: Using ai-framework/prompts/phase-1-planning/1.2-architect-tech-spec.md,
     CONSTITUTION.md, and docs/prds/[feature]-prd.md,
     create a technical specification

# Generate tasks
You: Using ai-framework/prompts/phase-2-implementation/2.1-generate-task-list.md,
     docs/[feature]-tech-spec.md, and CONSTITUTION.md,
     generate a task list with interactive mode

# Implement
You: Using ai-framework/prompts/phase-2-implementation/2.2-iterative-implementation.md,
     docs/[feature]-tasks.md, and CONSTITUTION.md,
     implement task #1

# Review
You: Using ai-framework/prompts/phase-3-review/3.1-qa-comprehensive-review.md
     and CONSTITUTION.md, review the [feature] feature
```

## Best Practices for Claude Code + AI-Dev-Orchestrator

### DO:

✅ **Reference files explicitly** - Use full paths: `ai-framework/quick-start/simple-workflow.md`
✅ **Keep CLAUDE.md updated** - Include current feature status
✅ **Use custom commands** - Save time with `/quick-prd`, `/generate-tasks`, etc.
✅ **Commit regularly** - After each completed parent task
✅ **Review AI output** - Always check generated code before running
✅ **Stay in control** - Approve each sub-task before moving to the next

### DON'T:

❌ **Don't skip CONSTITUTION.md** - The AI needs your project context
❌ **Don't let AI run ahead** - Explicitly: "ONLY implement sub-task 1.1"
❌ **Don't work in long sessions** - Take breaks, review progress
❌ **Don't forget to test** - Run tests after every 2-3 sub-tasks
❌ **Don't mix features** - One feature per session/task list

## File Organization

Recommended structure for ai-dev-orchestrator with Claude Code:

```
my-project/
├── .claude/
│   └── commands/           # Custom slash commands
│       ├── quick-prd.md
│       ├── generate-tasks.md
│       └── implement-task.md
├── ai-framework/           # AI-dev-orchestrator files
│   ├── quick-start/
│   ├── prompts/
│   ├── personas/
│   └── workflow/
├── docs/
│   ├── prds/              # Product requirement docs
│   ├── tech-specs/        # Technical specifications
│   └── tasks/             # Task lists
├── src/                   # Your source code
├── tests/                 # Your tests
├── CLAUDE.md              # Claude Code context
├── CONSTITUTION.md        # Your project constitution
└── README.md
```

## Tips for Effective Use

### 1. Use Git Integration

Claude Code integrates with Git. After completing parent tasks:

```bash
# Claude can do this for you
You: All sub-tasks for parent task 2 are complete.
     Run tests, then commit with message:
     "feat: add user authentication API endpoints"

AI: [Runs tests, commits if passing]
```

### 2. Monitor Token Usage

Claude Code shows token usage. For budget-conscious development:

- **Use Haiku for simple tasks** (faster, cheaper)
- **Use Sonnet for implementation** (balanced)
- **Use Opus for complex planning** (best quality)

Set in your prompt:
```
[Use Haiku] Implement sub-task 1.1 - it's straightforward
[Use Opus] Design the database schema - this is complex
```

### 3. Leverage Context Windows

Claude has a large context window. You can include:
- CONSTITUTION.md
- Current PRD
- Current task list
- Related code files

All in one prompt!

### 4. Use Sessions

Continue work across sessions:

```bash
# Start new session
claude chat

# Resume previous session
claude chat --resume
```

Your CLAUDE.md file keeps the AI oriented to where you left off.

## Troubleshooting

### Issue: "Claude doesn't remember project context"
**Fix:** Update CLAUDE.md with current feature and reference it explicitly

### Issue: "File paths are wrong"
**Fix:** Show your structure: `tree -L 2` then paste output, ask again

### Issue: "AI generates too much at once"
**Fix:** Be firm: "Stop. Implement ONLY sub-task 1.1. Ask before 1.2."

### Issue: "Code doesn't match my standards"
**Fix:** Enhance CONSTITUTION.md with specific examples. Reference it in every prompt.

### Issue: "Token usage is too high"
**Fix:** Use custom commands to reduce repeated context. Reference files instead of pasting content.

## Example: Complete Feature with Claude Code

```bash
cd ~/my-project
claude chat

# Create PRD (5 minutes)
You: I want to add password reset functionality.
     Use CONSTITUTION.md and ai-framework/quick-start/simple-workflow.md
     to help me create a PRD.

AI: [Asks clarifying questions, generates PRD]

You: Save to docs/prds/password-reset-prd.md

# Generate tasks (5 minutes)
You: Using ai-framework/quick-start/process-task-list.md and the PRD,
     generate a task list. Interactive mode.

AI: [Generates 6 parent tasks]
    Ready for sub-tasks? Reply "Go"

You: Go

AI: [Generates 25 sub-tasks]

You: Save to docs/password-reset-tasks.md

# Implement (2-3 hours)
You: Reference CONSTITUTION.md and docs/password-reset-tasks.md.
     Implement sub-task 1.1 only. Mark [x] when done.

AI: [Implements, marks complete]

You: 1.1 looks good. Continue to 1.2

# ... repeat for all sub-tasks ...

# Review (15 minutes)
You: Using ai-framework/prompts/phase-3-review/3.1-qa-comprehensive-review.md
     and CONSTITUTION.md, review the password reset feature

AI: [Comprehensive review with findings]

You: Fix the issues you found

AI: [Fixes issues]

# Done!
You: Run tests, commit with message "feat: add password reset feature"
```

## Global Configuration (All Projects)

To make Claude Code behave consistently across ALL your projects, use global configuration files.

### Global CLAUDE.md

Create a global instructions file that applies to all projects:

**Location:** `~/.claude/CLAUDE.md`

```markdown
# Global Claude Code Instructions

## PR Comment Requirements

When working on any pull request:
1. ALWAYS post a review comment to GitHub using `gh pr review` or `gh pr comment`
2. Before completing work on a PR branch, summarize changes with `gh pr comment`
3. When reviewing PRs, use the standard review format with severity levels
4. Include specific file:line references for all issues found

## Standard PR Review Format

When posting PR reviews, use this format:

## Code Review Summary

### Overview
[Brief description of what this PR does]

### Findings

#### Strengths
- [What was done well]

#### Issues Found
| Severity | File | Line | Issue | Suggestion |
|----------|------|------|-------|------------|
| CRITICAL/HIGH/MEDIUM/LOW | `file` | line | description | fix |

### Recommendation
[APPROVE / REQUEST CHANGES / COMMENT]

## Git Workflow

- Always create descriptive commit messages
- Post PR comments when completing significant work
- Use `gh pr view` to check current PR context
```

### Global Settings

Claude Code also supports global settings in `~/.claude/settings.json`:

```json
{
  "permissions": {
    "allow": [
      "Bash(gh pr:*)",
      "Bash(gh issue:*)",
      "Bash(git:*)"
    ]
  }
}
```

### Verification

To verify your global config is working:

```bash
# Check if global CLAUDE.md exists
cat ~/.claude/CLAUDE.md

# Test gh authentication
gh auth status

# Test PR commands work
gh pr list
```

---

## Additional Resources

- [Claude Code Documentation](https://docs.anthropic.com/en/docs/claude-code)
- [AI-Dev-Orchestrator Main README](../README.md)
- [Quick Start Guide](../quick-start/README.md)
- [Anthropic Console](https://console.anthropic.com) (for API keys)

## Next Steps

1. **Install Claude Code** using the instructions above
2. **Set up your project** with Quick Start or Full Framework
3. **Create CLAUDE.md** to provide project context
4. **Create custom commands** for common workflows
5. **Build your first feature!**

---

**Ready to build with Claude Code?** Start with the [Quick Start Guide](../quick-start/README.md)! 🚀
