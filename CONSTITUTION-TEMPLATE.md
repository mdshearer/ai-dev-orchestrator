# Project Constitution Template

> **INSTRUCTIONS:** Copy this file to the root of your new project and customize it. This document contains the non-negotiable principles and standards for your project. All AI-generated code, documentation, and analysis MUST adhere to these rules.

---

## 1. Core Principles (The "Why")

**Function over Aesthetics**
- This is an [internal tool / web app / API / etc.]. Speed, reliability, simplicity, and ease of use are prioritized over complex visual design or animations.
- Aesthetic design is subservient to function.

**User is Sovereign**
- All features must be driven by explicit user needs. We "Start with user needs".
- No features are built without clear user stories or acceptance criteria.

**Simplicity Beats Complexity**
- Avoid over-engineering. Prefer simple, maintainable solutions over complex or "clever" ones.
- When in doubt, choose the simpler approach.
- YAGNI (You Aren't Gonna Need It) - don't build features speculatively.

**Accessibility is Mandatory**
- All UI components and user flows must be accessible (WCAG 2.1 AA minimum).
- All interactive elements must be keyboard-navigable.
- All images must have alt text.
- Color contrast must meet accessibility standards.

---

## 2. Technical Stack (The "What")

### Mandated Technologies

**Frontend:**
- Framework: [e.g., React 18+, Vue 3, Svelte, Next.js]
- Language: [e.g., TypeScript (strict mode)]
- Styling: [e.g., Tailwind CSS, CSS Modules, Styled Components]
- State Management: [e.g., Zustand, Redux Toolkit, Pinia]

**Backend:**
- Framework: [e.g., FastAPI, Express.js, Django, Flask]
- Language: [e.g., Python 3.11+, Node.js 20+, Go 1.21+]
- API Style: [e.g., REST, GraphQL, gRPC]

**Database:**
- Primary: [e.g., PostgreSQL 15+, MongoDB 7+, SQLite]
- Caching: [e.g., Redis, Memcached, N/A]

**Infrastructure:**
- Platform: [e.g., Docker, AWS Lambda, Vercel, Railway]
- CI/CD: [e.g., GitHub Actions, GitLab CI, CircleCI]

### Prohibited Technologies

- ❌ [e.g., jQuery - use modern vanilla JS or framework]
- ❌ [e.g., Bootstrap - use Tailwind CSS]
- ❌ [e.g., Class components in React - use functional components with hooks]
- ❌ [e.g., Mongoose - use raw MongoDB driver or Prisma]

---

## 3. Coding Standards (The "How")

### Language & Style

**Language Version:**
- [e.g., TypeScript 5+ (strict mode enabled)]
- [e.g., Python 3.11+ with type hints]

**Style Guide:**
- [e.g., Airbnb JavaScript Style Guide]
- [e.g., PEP 8 for Python]
- [e.g., Effective Go for Go]

**Linting & Formatting:**
- Linter: [e.g., ESLint, Pylint, golangci-lint]
- Formatter: [e.g., Prettier, Black, gofmt]
- All code must pass linting before commit.

### Naming Conventions

**Variables & Functions:**
- JavaScript/TypeScript: `camelCase` (e.g., `getUserData`, `isValid`)
- Python: `snake_case` (e.g., `get_user_data`, `is_valid`)
- Go: `camelCase` (exported: `PascalCase`)

**Classes & Types:**
- All languages: `PascalCase` (e.g., `UserService`, `ApiResponse`)

**Constants:**
- JavaScript/TypeScript: `UPPER_SNAKE_CASE` (e.g., `API_BASE_URL`)
- Python: `UPPER_SNAKE_CASE` (e.g., `MAX_RETRIES`)

**Files:**
- Components: `PascalCase.tsx` (e.g., `UserProfile.tsx`)
- Utilities: `kebab-case.ts` (e.g., `api-client.ts`)
- Python modules: `snake_case.py` (e.g., `user_service.py`)

### Code Organization

**File Structure:**
```
[Define your project structure here, e.g.,
src/
  components/     # React components
  services/       # Business logic
  utils/          # Utility functions
  types/          # TypeScript types
  api/            # API route handlers
tests/
  unit/
  integration/
]
```

**Import Order:**
1. External dependencies (e.g., `react`, `express`)
2. Internal absolute imports (e.g., `@/components`)
3. Relative imports (e.g., `./utils`)
4. Type imports (TypeScript)

### Comments & Documentation

**Required Comments:**
- All public functions, classes, and methods must have documentation headers.
  - JavaScript/TypeScript: JSDoc format
  - Python: Google-style or NumPy-style docstrings
  - Go: GoDoc format

**Comment Quality:**
- Comments must explain the **why** (intent), not the **what** (syntax).
- ❌ Bad: `// Loop through users`
- ✅ Good: `// Filter out inactive users to reduce API payload size`

**Inline Comments:**
- Use sparingly, only for complex logic or business rules.
- Place comments above the code they describe.

### Error Handling

**API Responses:**
- All API endpoints must return consistent error structures:
```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "User-friendly error message",
    "details": { /* optional field-specific errors */ }
  }
}
```

**Exception Handling:**
- Never use bare `try/catch` or `try/except` blocks without specific error handling.
- Log all errors with context (user ID, request ID, timestamp).
- Never expose stack traces or internal errors to end users.

### Testing Requirements

**Coverage:**
- Minimum code coverage: [e.g., 80%]
- All critical paths (auth, payments, data mutations) must have tests.

**Test Types:**
- Unit tests: [e.g., Jest, pytest, Go testing]
- Integration tests: [e.g., Supertest, pytest with fixtures]
- E2E tests: [e.g., Playwright, Cypress] (optional for internal tools)

---

## 4. Security & Compliance (The "Musts")

### Data Handling

**Personal Identifiable Information (PII):**
- ❌ Never log PII (emails, names, addresses, phone numbers).
- ❌ Never store PII in plain text.
- ✅ Always encrypt PII at rest.
- ✅ Always use HTTPS for data in transit.

**Secrets Management:**
- ❌ Never hardcode secrets, API keys, or credentials.
- ✅ All secrets must be stored in environment variables.
- ✅ Use a secrets manager in production (e.g., AWS Secrets Manager, HashiCorp Vault).

### Authentication & Authorization

**Authentication:**
- Method: [e.g., OAuth 2.0 with JWT tokens, Auth0, Firebase Auth]
- Session duration: [e.g., 24 hours with refresh tokens]
- Password requirements: [e.g., min 12 characters, must include special characters]

**Authorization:**
- All API endpoints must verify user permissions before execution.
- Use role-based access control (RBAC) or attribute-based access control (ABAC).

### Input Validation

**All user input must be validated:**
- ✅ Validate on both client and server side.
- ✅ Sanitize all inputs to prevent XSS attacks.
- ✅ Use parameterized queries to prevent SQL injection.
- ✅ Validate file uploads (type, size, content).

### Security Headers

**All HTTP responses must include:**
- `Content-Security-Policy`
- `X-Frame-Options: DENY`
- `X-Content-Type-Options: nosniff`
- `Strict-Transport-Security` (HSTS)

---

## 5. Git & Version Control

### Commit Messages

**Format:**
```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, no logic change)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Build process, dependencies, tooling

**Examples:**
```
feat(auth): add OAuth2 login flow

Implemented Google and GitHub OAuth2 providers using Passport.js.
Users can now sign in with their existing accounts.

Closes #123
```

### Branch Strategy

**Main Branches:**
- `main` (or `master`): Production-ready code
- `develop`: Integration branch for features

**Feature Branches:**
- Format: `feature/<ticket-id>-<short-description>` (e.g., `feature/USER-123-oauth-login`)
- Always branch from `develop`
- Merge back to `develop` via Pull Request

**Hotfix Branches:**
- Format: `hotfix/<issue-description>` (e.g., `hotfix/fix-login-crash`)
- Branch from `main`
- Merge to both `main` and `develop`

### Pull Request Requirements

**Before submitting:**
- ✅ All tests pass
- ✅ Code passes linting
- ✅ No merge conflicts
- ✅ PR description includes context and screenshots (if UI change)

**Review Process:**
- Minimum reviewers: [e.g., 1 for small changes, 2 for large changes]
- All comments must be resolved before merge

---

## 6. Performance Standards

### API Performance

**Response Times:**
- Target: 95th percentile < [e.g., 200ms]
- Maximum: [e.g., 2 seconds]

**Database Queries:**
- Avoid N+1 queries (use eager loading, joins, or batching).
- All queries must use indexes for frequently accessed fields.
- Limit query result sets (pagination required for lists).

### Frontend Performance

**Bundle Size:**
- Target: Initial bundle < [e.g., 200KB gzipped]
- Code splitting required for routes.

**Images:**
- All images must be optimized (WebP format preferred).
- Use lazy loading for images below the fold.
- Provide responsive images with `srcset`.

**Core Web Vitals Targets:**
- LCP (Largest Contentful Paint): < 2.5s
- FID (First Input Delay): < 100ms
- CLS (Cumulative Layout Shift): < 0.1

---

## 7. Deployment & Operations

### Environment Strategy

**Environments:**
- `development`: Local development
- `staging`: Pre-production testing
- `production`: Live environment

**Environment Variables:**
- Never commit `.env` files to version control.
- Use `.env.example` as a template with dummy values.

### Monitoring & Logging

**Required Logging:**
- All API requests (method, path, status code, duration)
- All errors with stack traces and context
- All authentication events (login, logout, failed attempts)

**Log Levels:**
- `DEBUG`: Detailed information for debugging
- `INFO`: General informational messages
- `WARN`: Warning messages (non-critical issues)
- `ERROR`: Error messages (requires attention)

**Monitoring:**
- Service: [e.g., Sentry, Datadog, New Relic, CloudWatch]
- Alerts for: [e.g., error rate > 1%, API latency > 2s, 5xx errors]

---

## 8. AI Coding Assistant Instructions

**When generating code for this project, you must:**

1. **Always reference this CONSTITUTION.md file** before writing any code.
2. **Ask clarifying questions** if the requirements conflict with these standards.
3. **Explain your reasoning** when making architectural decisions.
4. **Prioritize simplicity** over complexity or "clever" solutions.
5. **Include tests** for all new features or bug fixes.
6. **Add meaningful comments** that explain the "why", not the "what".
7. **Follow the established patterns** in the existing codebase.
8. **Never skip error handling** or input validation.
9. **Always consider security implications** of your code.
10. **Use the technical stack** defined in Section 2 - no substitutions without approval.

---

## Revision History

| Date | Version | Changes | Author |
|------|---------|---------|--------|
| [YYYY-MM-DD] | 1.0 | Initial constitution | [Your Name] |

---

**Last Updated:** [YYYY-MM-DD]
