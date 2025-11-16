# Replit AI Setup Guide for AI-Dev-Orchestrator

[Replit](https://replit.com) is a browser-based IDE with built-in AI, instant deployment, and integrated database. It's perfect for building internal tools and prototypes quickly without local setup.

## Why Replit for AI-Driven Development?

✅ **Zero Setup** - No installation, works in browser
✅ **Built-in AI** - Replit AI integrated directly in the IDE
✅ **Instant Deployment** - Your app is live as you build
✅ **Database Included** - PostgreSQL, Redis, or key-value store built-in
✅ **Perfect for Internal Tools** - Get something working fast
✅ **Great for Learning** - See results immediately

## Getting Started

### 1. Create Account

1. Visit [replit.com](https://replit.com)
2. Sign up (GitHub account recommended)
3. Consider **Replit Core** ($20/month) for:
   - Always-on apps
   - More powerful VMs
   - Private repos
   - Better AI features

### 2. Create a New Repl

**Option A: Start from Template**
1. Click "Create Repl"
2. Choose your stack:
   - **Node.js** (Next.js, Express, etc.)
   - **Python** (Flask, FastAPI, Django)
   - **Go** (Gin, Echo)
   - **Ruby** (Rails, Sinatra)
3. Name your project
4. Click "Create Repl"

**Option B: Import from GitHub**
1. Click "Create Repl"
2. Select "Import from GitHub"
3. Paste your repository URL
4. Replit will clone and set up automatically

### 3. Install AI-Dev-Orchestrator in Your Repl

Once your Repl is created:

#### Quick Start Setup

Click on "Shell" tab at the bottom and run:

```bash
# Create framework directory
mkdir -p ai-framework/quick-start

# Create a simple download script
cat > download-framework.sh << 'EOF'
#!/bin/bash
# Download ai-dev-orchestrator quick start files

BASE_URL="https://raw.githubusercontent.com/yourusername/ai-dev-orchestrator/main"

mkdir -p ai-framework/quick-start

curl -o ai-framework/quick-start/README.md $BASE_URL/quick-start/README.md
curl -o ai-framework/quick-start/simple-workflow.md $BASE_URL/quick-start/simple-workflow.md
curl -o ai-framework/quick-start/process-task-list.md $BASE_URL/quick-start/process-task-list.md
curl -o ai-framework/CONSTITUTION-TEMPLATE.md $BASE_URL/CONSTITUTION-TEMPLATE.md

echo "✅ Quick Start files downloaded!"
EOF

chmod +x download-framework.sh
./download-framework.sh
```

Or manually create the files by copying content from the repository.

#### Create Your Constitution

```bash
cp ai-framework/CONSTITUTION-TEMPLATE.md CONSTITUTION.md
```

Then edit `CONSTITUTION.md` in the Replit editor with your project details.

## Using Replit AI with AI-Dev-Orchestrator

### Replit AI Chat (Recommended)

Replit has a built-in AI chat panel on the left sidebar. This is perfect for ai-dev-orchestrator workflows.

**To open AI chat:**
- Click the AI icon in the left sidebar
- Or press `Ctrl+/` (Windows/Linux) or `Cmd+/` (Mac)

### Workflow 1: Quick Start Feature

#### Step 1: Create PRD

In the AI chat:
```
I want to build [describe your feature].

Please help me create a PRD following this process:
1. Read my CONSTITUTION.md for project context
2. Follow the format in ai-framework/quick-start/simple-workflow.md
3. Ask me clarifying questions about:
   - What problem this solves
   - Who will use it
   - What "done" looks like

Keep it simple - 3-5 core user stories for an internal tool.
```

The AI will ask questions and help you create a PRD. When done:
```
Save this PRD to docs/prds/[feature-name]-prd.md
```

#### Step 2: Generate Task List

```
Using the PRD we just created, generate a task list following
ai-framework/quick-start/process-task-list.md

Use interactive mode:
1. Show me 5-7 parent tasks first
2. Wait for my "Go"
3. Then generate detailed sub-tasks

Use checkbox format: - [ ] for incomplete, - [x] for complete
```

AI response:
```
Here are the parent tasks:
- [ ] 1. Set up database
- [ ] 2. Create API routes
- [ ] 3. Build UI components
- [ ] 4. Add authentication
- [ ] 5. Test and deploy

Ready for sub-tasks? Reply "Go"
```

You:
```
Go
```

When task list is generated:
```
Save this to docs/[feature-name]-tasks.md
```

#### Step 3: Implement Tasks

```
Reference CONSTITUTION.md and docs/[feature-name]-tasks.md

Implement sub-task 1.1 ONLY.
Mark it [x] when complete.
Show me what you changed.

Do NOT move to 1.2 without my approval.
```

After each sub-task:
```
Looks good. Continue to sub-task 1.2
```

### Workflow 2: Using Replit's @ File References

Replit AI supports `@filename` to reference files:

```
@CONSTITUTION.md
@ai-framework/quick-start/simple-workflow.md

I want to build a task management feature. Help me create a PRD.
```

```
@CONSTITUTION.md
@docs/tasks-prd.md
@ai-framework/quick-start/process-task-list.md

Generate a task list for this PRD. Use interactive mode.
```

```
@CONSTITUTION.md
@docs/tasks-tasks.md

Implement sub-task 2.1 - Create the API endpoint for creating tasks.
Mark [x] when done.
```

## Replit-Specific Features

### 1. Instant Preview

As you build, Replit shows a live preview:
- Web apps: Automatic preview in right panel
- APIs: Use the "Webview" to test endpoints
- Changes refresh automatically

**Pro Tip:** Keep preview open while implementing. See changes in real-time!

### 2. Built-in Database

Replit includes databases out-of-the-box:

**PostgreSQL (Recommended for most apps)**
```bash
# In Shell tab
replit database create postgres

# Connection string is in environment variables:
# DATABASE_URL
```

**Key-Value Store (Simple data)**
```python
# Python example
from replit import db

db["user_1"] = {"name": "Alice", "email": "alice@example.com"}
user = db["user_1"]
```

**Update CONSTITUTION.md** with your database choice so AI knows:
```markdown
## Technical Stack

**Database:** Replit PostgreSQL
**Connection:** Use DATABASE_URL environment variable
```

### 3. Environment Variables (Secrets)

For API keys and sensitive data:

1. Click "Tools" in left sidebar
2. Click "Secrets"
3. Add key-value pairs (e.g., `OPENAI_API_KEY=sk-...`)
4. Access in your code:
   ```javascript
   const apiKey = process.env.OPENAI_API_KEY
   ```

**Tell the AI:**
```
When you need to use API keys, reference environment variables.
Never hardcode secrets. Use process.env.VARIABLE_NAME
```

### 4. Deployment

Replit apps are automatically deployed:
- **Development URL**: Shows while developing (e.g., `your-app.username.repl.co`)
- **Always On**: Enable in settings (Replit Core required)
- **Custom Domain**: Link your own domain in settings

After implementing features:
```
Test the implementation at the Replit URL
```

### 5. Collaboration

Share your Repl for code review or pair programming:
1. Click "Share" button
2. Invite collaborators by email
3. They can view and edit in real-time

## Project Structure for Replit

Recommended folder structure:

```
YourRepl/
├── ai-framework/          # AI-dev-orchestrator files
│   ├── quick-start/
│   │   ├── README.md
│   │   ├── simple-workflow.md
│   │   └── process-task-list.md
│   └── CONSTITUTION-TEMPLATE.md
├── docs/                  # Your documentation
│   ├── prds/             # Product requirements
│   └── tasks/            # Task lists
├── src/                  # Source code (or app/, server/, etc.)
├── public/               # Static files (if web app)
├── tests/                # Tests
├── CONSTITUTION.md       # Your project constitution
├── README.md             # Project readme
└── .replit               # Replit configuration (auto-generated)
```

## Best Practices for Replit + AI-Dev-Orchestrator

### DO:

✅ **Use Replit AI chat** - It's built-in and optimized for Replit's environment
✅ **Reference CONSTITUTION.md always** - Context is key
✅ **Test in preview immediately** - Replit's live preview is your friend
✅ **Use built-in database** - No need for external services for internal tools
✅ **Commit to GitHub** - Use Replit's Git integration (left sidebar → Version Control)
✅ **One sub-task at a time** - Stay in control of what's being built

### DON'T:

❌ **Don't hardcode secrets** - Use Replit Secrets
❌ **Don't skip testing** - Check preview after every 2-3 sub-tasks
❌ **Don't let AI run ahead** - Explicitly: "ONLY sub-task 1.1"
❌ **Don't forget to save files** - Ctrl+S / Cmd+S (Replit auto-saves, but be sure)
❌ **Don't ignore errors in console** - Check Shell tab for backend errors

## Example: Building an Internal Tool on Replit

Let's build a "Team Task Tracker" from scratch:

### Setup (5 minutes)

1. **Create Repl**
   - Go to replit.com
   - Create Repl → Node.js (Express)
   - Name: "team-task-tracker"

2. **Install AI Framework** (Shell tab)
   ```bash
   mkdir -p ai-framework/quick-start docs/prds docs/tasks
   # Copy quick-start files (use download script from above)
   cp ai-framework/CONSTITUTION-TEMPLATE.md CONSTITUTION.md
   ```

3. **Edit CONSTITUTION.md**
   ```markdown
   ## Project: Team Task Tracker
   An internal tool for our team to track tasks.

   ## Technical Stack
   - Framework: Express.js (Node.js)
   - Database: Replit PostgreSQL
   - Frontend: EJS templates (server-side rendering)
   - Styling: Tailwind CSS via CDN
   - Auth: Simple session-based (no OAuth needed)

   ## User Context
   - Internal tool for 5-person team
   - Function over form (doesn't need to be pretty)
   - Fast iteration > perfection

   ## Security
   - Basic auth (username/password)
   - No sensitive data (just task descriptions)
   - HTTPS via Replit (automatic)
   ```

### Build (2-3 hours)

1. **Create PRD** (AI Chat)
   ```
   @CONSTITUTION.md
   @ai-framework/quick-start/simple-workflow.md

   I want to build a simple task tracker for my team where we can:
   - Create tasks with title and description
   - Assign tasks to team members
   - Mark tasks as complete
   - View all tasks

   Help me create a PRD.
   ```

   Save to `docs/prds/task-tracker-prd.md`

2. **Generate Tasks** (AI Chat)
   ```
   @CONSTITUTION.md
   @docs/prds/task-tracker-prd.md
   @ai-framework/quick-start/process-task-list.md

   Generate a task list. Use interactive mode.
   ```

   Save to `docs/task-tracker-tasks.md`

3. **Implement** (AI Chat, iteratively)
   ```
   @CONSTITUTION.md
   @docs/task-tracker-tasks.md

   Implement sub-task 1.1: Set up PostgreSQL database with tasks table
   Mark [x] when done.
   ```

   After each sub-task:
   - Check the preview
   - Test the feature
   - Approve next task: "Continue to 1.2"

4. **Test** (Preview panel)
   - Create a task
   - Assign it
   - Mark complete
   - Verify everything works

5. **Deploy**
   - Already live at your Repl URL!
   - Share with team: "Here's our task tracker: [URL]"

### Done! (2-3 hours from start to deployed app)

## Replit-Specific Tips

### Tip 1: Use the Shell for Testing

Open Shell tab to run commands:
```bash
# Test API endpoint
curl http://localhost:3000/api/tasks

# Check database
psql $DATABASE_URL -c "SELECT * FROM tasks;"

# Run tests
npm test
```

### Tip 2: Use Packager for Dependencies

Replit auto-detects dependencies, but you can also:
1. Click "Tools" → "Packages"
2. Search and add packages
3. Replit installs automatically

Or use Shell:
```bash
npm install express pg bcrypt
```

### Tip 3: Configure .replit File

The `.replit` file controls how your app runs:

```toml
run = "node src/index.js"

[env]
NODE_ENV = "development"

[nix]
channel = "stable-22_11"
```

### Tip 4: Debug with Replit Console

Open "Console" tab (bottom) to see:
- Server logs
- Error messages
- Database queries (if you log them)

### Tip 5: Use GitHub Integration

Connect to GitHub (left sidebar → Version Control):
1. Commits go to GitHub automatically
2. Can pull from GitHub
3. Great for backing up your work

**Tell the AI when to commit:**
```
All sub-tasks for parent task 2 are complete.
Commit changes to GitHub with message:
"feat: add task creation API endpoint"
```

## Limitations to Be Aware Of

⚠️ **Free tier limits:**
- Repl goes to sleep after inactivity (Always On requires Replit Core)
- Limited CPU and memory
- No custom domains on free tier

⚠️ **Not ideal for:**
- Production apps with high traffic
- Apps requiring specific server configuration
- Projects with large file uploads

✅ **Perfect for:**
- Internal tools (small teams)
- Prototypes and MVPs
- Learning and experimentation
- Side projects and demos

## Troubleshooting

### Issue: "App won't start"
**Fix:** Check Console tab for errors. Make sure `.replit` file has correct `run` command.

### Issue: "Database connection failed"
**Fix:** Make sure you created the database: `replit database create postgres`. Check `DATABASE_URL` in Shell: `echo $DATABASE_URL`

### Issue: "AI doesn't know my tech stack"
**Fix:** Always reference `@CONSTITUTION.md` in prompts. Update CONSTITUTION.md with Replit-specific details.

### Issue: "Changes don't show in preview"
**Fix:** Hard refresh the preview panel (click refresh icon). Check Console for errors.

### Issue: "Repl is slow"
**Fix:** Free tier has limited resources. Consider upgrading to Replit Core, or reduce complexity.

## Example CONSTITUTION.md for Replit

Here's a complete example tailored for Replit:

```markdown
# Project Constitution: [Your App Name]

## Overview
[Brief description of your app]

## Technical Stack

**Runtime:** Node.js 18 (Replit environment)
**Framework:** Express.js
**Database:** Replit PostgreSQL
  - Connection: Use `DATABASE_URL` environment variable
  - ORM: None (use `pg` library directly for simplicity)
**Frontend:** EJS templates (server-side rendering)
**Styling:** Tailwind CSS (via CDN)
**Authentication:** Express-session with in-memory store

## User Context
- **Users:** Internal team (5 people)
- **Use Case:** Internal tool for [purpose]
- **Priority:** Function over form - it just needs to work
- **Deployment:** Replit (always-on)

## Coding Standards

### File Structure
\`\`\`
src/
  ├── routes/       # Express routes
  ├── models/       # Database models
  ├── views/        # EJS templates
  └── index.js      # Entry point
\`\`\`

### Database Patterns
\`\`\`javascript
// Use pg library directly
const { Pool } = require('pg');
const pool = new Pool({ connectionString: process.env.DATABASE_URL });

// Always use parameterized queries (prevent SQL injection)
const result = await pool.query('SELECT * FROM users WHERE id = $1', [userId]);
\`\`\`

### Error Handling
\`\`\`javascript
// Always handle errors in async routes
app.get('/api/data', async (req, res) => {
  try {
    const data = await getData();
    res.json(data);
  } catch (error) {
    console.error('Error:', error);
    res.status(500).json({ error: 'Internal server error' });
  }
});
\`\`\`

### Environment Variables
- Store secrets in Replit Secrets (Tools → Secrets)
- Reference with `process.env.VARIABLE_NAME`
- Never hardcode API keys or passwords

## Security Requirements

**Authentication:**
- Simple username/password (stored as bcrypt hashes)
- Use express-session for session management

**Input Validation:**
- Validate all user inputs
- Use parameterized SQL queries (prevent injection)

**Data Protection:**
- HTTPS automatically via Replit
- Session cookies: httpOnly, secure (in production)

## Testing Approach

**Manual Testing:**
- Test in Replit preview after each feature
- Check Console tab for errors
- Test edge cases manually

**Automated Testing (optional):**
- Jest for unit tests (if time allows)
- Run with `npm test`

## Out of Scope

This is an internal tool, so we're NOT building:
- OAuth/social login (simple auth is fine)
- Mobile app (responsive web is enough)
- Real-time updates (polling is fine)
- Advanced caching (keep it simple)
- Microservices (monolith is fine)

## Success Criteria

✅ Team can create, assign, and complete tasks
✅ Data persists between sessions
✅ Works on desktop and mobile browsers
✅ No critical bugs or security vulnerabilities
✅ Deployed and accessible to team
```

## Next Steps

1. **Sign up for Replit** at [replit.com](https://replit.com)
2. **Create your first Repl** with your preferred stack
3. **Install ai-dev-orchestrator** Quick Start files
4. **Customize CONSTITUTION.md** for your project
5. **Build your first feature** using the Quick Start workflow!

## Additional Resources

- [Replit Documentation](https://docs.replit.com)
- [Replit Community](https://replit.com/community)
- [AI-Dev-Orchestrator Main README](../README.md)
- [Quick Start Guide](../quick-start/README.md)

---

**Ready to build on Replit?** Start with the [Quick Start Guide](../quick-start/README.md) and ship your first internal tool today! 🚀
