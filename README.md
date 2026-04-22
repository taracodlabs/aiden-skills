# Aiden Skills Library

Curated skill catalog for [DevOS — Aiden](https://github.com/taracodlabs/aiden),
the local-first AI operating system.

Each skill is a single `SKILL.md` file with YAML frontmatter
(name, category, description, platform, version, tags).
No runtime code here — the library is a catalog that Aiden
can browse, install, and enable on demand.

---

## Skills by category

| Category | Count | Skills |
| -------- | ----- | ------ |
| Security / OSINT | 10 | haveibeenpwned, crt-sh, urlscan, shodan, virustotal, cveapi, explainshell, censys, greynoise, ssllabs |
| Developer | 7 | arxiv, github-auth, github-issues, github-pr-workflow, github-repo-management, claude-code, codex |
| General | 7 | deep-research, morning-briefing, competitor-analysis, content-planner, code-ship, file-organiser, pdf-research |
| Creative | 2 | ascii-art, gif-search |
| Research | 2 | systematic-debugging, test-driven-development |
| Other | 4 | excalidraw, architecture-diagram, research-paper-writing, securityheaders |

**Total: 32 skills** (see [`INDEX.json`](INDEX.json) for full metadata)

---

## Install via Aiden

From the Aiden CLI or chat:

```
/skills explore <topic>
/skills install <skill-id>
/skills enable <skill-id>
```

---

## Skill frontmatter format

```yaml
---
name: my-skill
description: One-line description of what this skill does
category: security | developer | research | creative | general
platform: any | windows | linux
version: 1.0.0
tags: tag1, tag2, tag3
env_required:
  - MY_API_KEY
---
```

---

## Contribute a skill

1. Fork this repo
2. Add `<skill-id>/SKILL.md` with valid frontmatter (see format above)
3. Open a PR — CI validates frontmatter structure
4. Once merged, `/skills explore` users will discover your skill

Only submit skills that are:
- **Cross-platform** (or clearly labeled `platform: windows/linux`)
- **Self-contained** (no external state or project-specific assumptions)
- **Generally useful** (not repo-specific or moat features)

NSE trading, Windows admin, and India-specific skills are intentionally
**not** in this library — they remain in the main
[aiden](https://github.com/taracodlabs/aiden) repo.

---

## Links

- **Main repo:** https://github.com/taracodlabs/aiden
- **Releases + installers:** https://github.com/taracodlabs/aiden-releases
- **Landing page:** https://aiden.taracod.com
- **Discord:** https://discord.gg/gMZ3hUnQTm

---

Licensed MIT. Individual skills may have their own license notes
in their `SKILL.md`. Built by [Taracod](https://taracod.com).