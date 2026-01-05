# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**[Your Project Name]** is [your project description].

**Tech Stack:**
- Backend: [Your backend - e.g., Node.js/Express, Python/Flask, etc.]
- Database: [Your database - e.g., PostgreSQL, MongoDB, etc.]
- Storage: [Your storage solution - e.g., AWS S3, local storage, etc.]
- Frontend: [Your frontend - e.g., React, Vue, vanilla HTML/CSS/JS, etc.]

**Customize this section with your project details:**

- Recent feature additions
- Key technologies
- Development environment
- Deployment information

## 🤖 ACTIVE AGENTS (Always Running in Background)

**SEVEN agents are ALWAYS ACTIVE and working automatically. See [AGENTS.md](./AGENTS.md) for full definitions.**

### Agent 1: Library Research Agent (AUTOMATIC)
**You MUST AUTOMATICALLY:**
- Check [APPROVED_GITHUB_LIBRARIES.md](./APPROVED_GITHUB_LIBRARIES.md) BEFORE any code implementation (if this file exists)
- Search GitHub (500+ stars) for existing solutions
- Evaluate 2-3 candidates with comparison
- Recommend libraries over custom code
- NEVER create new functions without this search process

### Agent 2: Learning & Onboarding Agent (AUTOMATIC)
**You MUST AUTOMATICALLY:**
- Explain concepts in beginner-friendly terms
- Provide code examples from codebase
- Link to learning resources
- Break down complex topics
- Suggest practical next steps

### Agent 3: Code Quality & Review Agent (AUTOMATIC)
**You MUST AUTOMATICALLY on EVERY code interaction:**
- Review for security vulnerabilities (SQL injection, secrets, auth)
- Check error handling and input validation
- Suggest performance improvements
- Enforce best practices
- Verify follows project patterns
- Check documentation

### Agent 4: API Endpoint Monitor Agent (AUTOMATIC)
**You MUST AUTOMATICALLY on EVERY API/endpoint interaction:**
- Scan and monitor all API endpoints
- Check endpoint health and validate responses
- Detect errors and missing error handling
- Validate status codes and response formats
- Check for security issues (auth, validation, SQL injection)
- Suggest fixes for endpoint issues
- Verify endpoints have tests

### Agent 5: Debugging Agent (AUTOMATIC)
**You MUST AUTOMATICALLY on EVERY error or debugging request:**
- Analyze error messages and stack traces
- Trace problems through codebase systematically
- Identify root causes (not just symptoms)
- Suggest systematic fixes with code examples
- Check for common framework-specific issues (Node.js/Express, Python/Flask, etc.)
- Provide debugging strategies
- Verify async/await usage and error handling

### Agent 6: Code Validation Agent (AUTOMATIC)
**You MUST AUTOMATICALLY on EVERY code change:**
- Validate code changes work as expected
- Run relevant tests for changed files
- Check if changes break existing functionality
- Verify code compiles/runs without errors
- Report ALL errors found with DETAILED fix instructions
- Provide code examples (BEFORE/AFTER) for each error
- Prioritize errors by severity (Critical, High, Medium, Low)
- Explain WHY each error is a problem
- List ALL errors (don't stop at the first one)
- Recommend Husky (30k+ stars) + lint-staged (15k+ stars) for automation
- Suggest test coverage for new code
- Run tests before confirming code is ready

### Agent 7: Auto-Debugging Escalation Agent (AUTOMATIC)
**You MUST AUTOMATICALLY on EVERY debugging/fix attempt:**
- Track fix attempts (count failures)
- After 2 unsuccessful fix attempts: AUTOMATICALLY search web and GitHub for top 2 solutions, test both
- If top 2 solutions fail: AUTOMATICALLY search for 4 more solutions from web/GitHub/forums/chatboards, implement and test all 4 one by one
- If all 6 solutions fail: AUTOMATICALLY propose creative new solutions that haven't been tried
- Test each solution before moving to next
- Document all attempts and sources with URLs
- Stop as soon as problem is fixed
- NEVER give up - escalate through all phases systematically

---

## Development Rules (MANDATORY)

**⚠️ CRITICAL:** Before creating any new function, module, or feature, you MUST follow the GitHub-first development process:

1. **AUTOMATICALLY check [APPROVED_GITHUB_LIBRARIES.md](./APPROVED_GITHUB_LIBRARIES.md)** - Search for existing solutions FIRST (if this file exists)
2. **AUTOMATICALLY search GitHub** - Find highly-rated repos (>500 stars minimum)
3. **AUTOMATICALLY evaluate alternatives** - Compare 2-3 options before custom implementation
4. **AUTOMATICALLY recommend libraries** - Prefer existing solutions over custom code
5. **Only create custom code** - If no suitable libraries exist after thorough search

**Key Rule:** Never create new functions from scratch without first searching GitHub for existing solutions.

---

## Database Best Practices

**IMPORTANT:** When working with databases, follow best practices for your database type.

### For PostgreSQL Projects
- Use parameterized queries to prevent SQL injection
- Use transactions for multi-step operations
- Consider using an ORM (Prisma, TypeORM, Sequelize) for complex projects
- Follow PostgreSQL naming conventions
- Use appropriate indexes for performance

### For MongoDB Projects
- Use parameterized queries to prevent NoSQL injection
- Use transactions for multi-document operations
- Consider using Mongoose or similar ODM
- Follow MongoDB naming conventions
- Use appropriate indexes for performance

### For SQLite Projects
- Use parameterized queries
- Consider connection pooling
- Follow SQLite best practices for your use case

**Customize this section based on your database choice.**

---

## Git Workflow

**Claude Code should follow your project's git workflow. Customize this section as needed.**

### Commit Guidelines:
1. **Commit after completing features** - After implementing any new feature or fix
2. **Write clear commit messages** - Use conventional commit format if preferred
3. **Never commit sensitive data** - Check .gitignore before committing
4. **Keep commits atomic** - One logical change per commit

### Commit Message Format (Example):
```
<type>: <short description>

<optional longer description>
```

Types: feat, fix, docs, refactor, test, chore

### Files to Never Commit:
- `.env`, `.env.local` (credentials)
- `node_modules/`, `venv/`, `__pycache__/` (dependencies)
- Any `*.log` files
- Build artifacts and generated files

---

## Development Agents

**Seven specialized agents are available to assist with development:**

**Quick Start:** See [AGENTS-QUICK-START.md](./AGENTS-QUICK-START.md)  
**Full Documentation:** See [AGENTS.md](./AGENTS.md)

1. **Library Research Agent** - Finds and evaluates GitHub repositories before coding
2. **Learning & Onboarding Agent** - Helps new developers understand the codebase
3. **Code Quality & Review Agent** - Reviews code for quality, security, and best practices
4. **API Endpoint Monitor Agent** - Monitors API endpoints and detects errors
5. **Debugging Agent** - Helps debug errors and analyze issues
6. **Code Validation Agent** - Validates code changes and runs tests
7. **Auto-Debugging Escalation Agent** - Escalates debugging when fixes fail

**Usage:** Agents work automatically. Copy agent prompts from AGENTS.md for manual use with other AI assistants.

---

## Development Commands

**Customize this section with your project's specific commands:**

### Running the Application
```bash
# Add your start command here
# Example: npm start, python app.py, etc.
```

### Testing
```bash
# Add your test commands here
# Example: npm test, pytest, etc.
```

### Database Operations
```bash
# Add your database commands here
# Example: migrations, seeds, etc.
```

---

## Project Structure

**Customize this section to document your project structure:**

```
your-project/
├── src/              # Source code
├── tests/            # Test files
├── docs/             # Documentation
├── config/           # Configuration files
└── ...               # Other directories
```

---

## Environment Configuration

**Customize with your required environment variables:**

```bash
# Add your environment variables here
# Example:
# DATABASE_URL=
# API_KEY=
# NODE_ENV=development
```

---

## Development Workflow

**Customize with your project's workflow:**

1. Set up development environment
2. Install dependencies
3. Configure environment variables
4. Run the application
5. Make changes and test
6. Commit and push changes

---

## Testing Strategy

**Customize with your testing approach:**

- Unit tests
- Integration tests
- End-to-end tests
- Test coverage requirements

---

## Deployment Notes

**Customize with your deployment information:**

- Deployment platform
- Deployment commands
- Environment setup
- Production considerations

---

## Key Files Reference

**Customize with your project's important files:**

- Key configuration files
- Main entry points
- Important modules
- Documentation files

---

## Common Tasks

**Customize with common tasks for your project:**

### Add a New Feature
1. Create feature branch
2. Implement feature
3. Write tests
4. Update documentation
5. Create pull request

### Add a New API Endpoint
1. [Your steps here]

### Add a New Database Table
1. [Your steps here]

---

**Remember to customize all sections above with your project-specific information!**
