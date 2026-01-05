# Architecture Decisions

Significant technical decisions and their rationale.

---

## 2025-01-05: Split Global vs Project Learnings
- **Decision:** Separate learnings into global (`~/.claude/learnings/`) and project-specific (`.claude/learnings/`)
- **Rationale:** Some learnings apply everywhere (TypeScript patterns), others are project-specific (this project uses Zustand)
- **Alternatives rejected:** Single global location (loses project context), single project location (can't share cross-project)

---

<!-- New decisions will be appended below -->
