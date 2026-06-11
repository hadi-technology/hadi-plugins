# CLAUDE.md — hadi-plugins

Agent-facing orientation for this repo. Read this before making changes.

## What this repo is

This is the **HADI Technology plugin marketplace catalog** for Claude Code. It contains **no plugin code** — only `.claude-plugin/marketplace.json`, a manifest that points Claude Code to the individual plugin repositories. Adding this marketplace (`/plugin marketplace add hadi-technology/hadi-plugins`) lets a user install any listed plugin from its own repo.

## Ecosystem map

| Repo | Role | Local path (if cloned) |
|------|------|------------------------|
| **hadi-plugins** (this repo) | The catalog. Lists every HADI plugin. | `/Users/Baba/hadi-plugins` |
| **HADI-MeetingOps** | Plugin — Zoom meeting intelligence | external only |
| **phased-workflow** | Plugin — Plan→Review→Implement→QA dev methodology (5 skills) | external only |
| **hadi-skills** | Plugin — grab-bag of standalone skills (`/ob`, etc.) | `/Users/Baba/hadi-skills` |

Each plugin is its **own repo**. Substantial products get their own repo; loose/general-purpose skills are bundled into **hadi-skills** rather than spawning a repo each.

## How to add a plugin to the catalog

Edit `.claude-plugin/marketplace.json` — add one object to the `plugins` array:

```json
{
  "name": "plugin-name",
  "description": "One-line description shown in /plugin.",
  "source": { "type": "git", "url": "https://github.com/hadi-technology/<repo>.git" }
}
```

`source` can also be a relative path (`"./plugins/foo"`) to bundle a plugin inside this repo, but the current convention is one external repo per plugin. After editing, also add a row to `README.md`'s plugin table, then commit + push. Nothing else is required — Claude Code re-reads the manifest.

## Conventions

- **Terminology:** this targets **Claude Code** (the CLI/app). Do not write "Claude Cowork" — that's an outdated name.
- **`.claude/` is gitignored** — it holds local agent artifacts (e.g. the `/ob` orientation cache), not published content.
- **Single marketplace file.** Never create `marketplace.json` variants or `.bak` files.
