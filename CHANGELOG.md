# Changelog

All notable changes to the AI-Dev-Orchestrator project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [2.0.0] - 2025-12-29

### Breaking Changes
- **TypeScript Required on Frontend**: Constitution templates now mandate TypeScript (strict mode) across the entire stack. Projects using JavaScript-only frontend should migrate or use v1.x templates.

### Added
- **Type Sharing Section**: Explicit guidance on sharing types between frontend and backend via `shared/schema.ts`
- **AI Model Assumptions**: New section documenting which AI models the framework is designed for
- **Version History Requirement**: Constitutions must now include revision history table

### Changed
- **Simplicity Principle Clarified**: Expanded to explain what simplicity means AND doesn't mean
- **Testing Requirements**: Now include specific coverage thresholds instead of vague "adequate testing"
- **Frontend Language Guidance**: Updated from optional TypeScript to mandatory TypeScript with strict mode

### Rationale
These changes are based on 6+ months of real-world usage in the OKM (Optimi Knowledge Manager) project. Key learnings:

1. **TypeScript prohibition was outdated**: Based on 2023-era AI limitations (GPT-3.5, early Claude). Current models (Claude Sonnet 4+, GPT-4+) excel at TypeScript and the type safety significantly reduces bugs.

2. **Type sharing prevents bugs**: Projects with shared schema types between frontend/backend had significantly fewer API integration bugs.

3. **Vague testing requirements led to undertesting**: Specific thresholds give teams clear targets.

4. **"Simplicity" was misinterpreted**: Teams avoided useful tools (TypeScript, Zod) thinking it violated simplicity principles. Clarified that simplicity means proven, well-documented tools, not avoiding powerful features.

---

## [1.0.0] - 2025-01-15

### Added
- Initial release of AI-Dev-Orchestrator
- 15 copy-paste prompts for AI-assisted development
- 5 AI personas (Product Owner, Architect, Developer, QA, Writer)
- Constitution template
- 4-phase workflow
- Guides for Cursor, Claude Code, and Replit
- Comprehensive documentation and examples
