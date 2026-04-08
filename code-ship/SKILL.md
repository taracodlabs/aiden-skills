---
name: code-ship
description: Full code-to-production pipeline — scaffold, implement, test, fix errors, commit, and deploy. Use when the user asks to build something, ship a feature, create a project, or deploy code.
---

# Code Ship

Build, test, fix, and deploy code end-to-end. Not just write code — ship it.

## When to Use This Skill

- User says "build X", "create X", "ship X", "deploy X"
- User wants a full feature implementation from scratch
- User says "write code for X and make it work"
- User wants to go from idea → deployed product

## Pipeline

### Phase 1: Understand Requirements

Before writing any code:
1. What is being built? (feature, app, script, API, component)
2. What language/framework? (detect from project context or ask)
3. What's the output? (running app, deployed service, script file, PR)
4. Are there tests expected? (default: yes)
5. Where does it deploy? (Vercel, Cloudflare, Docker, local only)

### Phase 2: Scaffold

Create the file structure first. Don't write implementation yet.

```
project/
├── src/
│   ├── index.ts        # Entry point
│   ├── [feature]/      # Feature modules
│   └── utils/          # Shared utilities
├── tests/
│   └── [feature].test.ts
├── package.json
├── tsconfig.json
└── README.md
```

For existing projects: identify which files need to be created or modified. Don't touch files that aren't relevant.

### Phase 3: Implement

Write code following these principles:
- **Small files**: No file over 300 lines. Split if needed.
- **Types first**: Define interfaces/types before implementation.
- **Error handling**: Every async operation needs try/catch.
- **No hardcoded values**: Use environment variables or config.
- **Readable names**: `getUserById` not `getUsr` or `fn1`.

### Phase 4: Test

Write tests BEFORE claiming the implementation works.

```bash
# Run the test suite
npm test        # or pytest, go test, cargo test

# If tests fail, fix the code (not the tests)
# If tests pass, move to next phase
```

Minimum test coverage:
- Happy path: does it work with valid input?
- Edge case: empty input, null, undefined, boundary values
- Error path: what happens when it fails?

### Phase 5: Fix All Errors

Run the full check suite:

```bash
# TypeScript
npx tsc --noEmit        # Type check
npm run lint             # Lint
npm test                 # Tests

# Python
python -m pytest         # Tests
python -m mypy .         # Type check
python -m ruff check .   # Lint
```

If ANY check fails:
1. Read the error message carefully
2. Fix the root cause (not symptoms)
3. Re-run ALL checks (fixing one thing can break another)
4. Repeat until all green

**Never skip a failing test. Never modify test config to make tests pass.**

### Phase 6: Commit

```bash
git add -A
git commit -m "feat: [descriptive message]

- [what was built]
- [key implementation details]
- [tests: X passing]"
```

Follow conventional commits: `feat:`, `fix:`, `refactor:`, `test:`, `docs:`.

### Phase 7: Deploy (if requested)

**Vercel:**
```bash
npx vercel --prod
```

**Cloudflare Workers:**
```bash
npx wrangler deploy
```

**Docker:**
```bash
docker build -t [name] .
docker run -p 3000:3000 [name]
```

After deploy: verify the live URL responds correctly. Don't just deploy and assume.

## Error Recovery

When something breaks during any phase:

1. **Read the full error** — not just the first line
2. **Identify the root cause** — is it a dependency, a type error, a runtime issue?
3. **Fix at the source** — don't patch symptoms
4. **Re-run from Phase 4** — tests → lint → type check → all green
5. **If stuck after 3 attempts** — try a fundamentally different approach, don't keep tweaking the same broken code

## Quality Checklist (before declaring "done")

- [ ] All tests pass
- [ ] No TypeScript/lint errors
- [ ] No hardcoded secrets or API keys
- [ ] README updated with setup instructions
- [ ] Code committed with meaningful message
- [ ] Deployed and verified (if deployment was requested)
- [ ] User can see the result — don't just say "done", show the output
