# HADI Technology — Claude Code Plugin Marketplace

AI-powered workflow plugins by [HADI Technology](https://haditechnology.com). Meeting intelligence, automation, and structured development tooling for professionals — installable directly in Claude Code.

This repository is a **plugin marketplace catalog**. It contains no plugin code itself; it points Claude Code to the individual plugin repositories listed below.

## Add the marketplace

```
/plugin marketplace add hadi-technology/hadi-plugins
```

Then browse and install plugins with:

```
/plugin
```

## Available plugins

| Plugin | Description | Source |
|--------|-------------|--------|
| **hadi-meetingops** | Operationalize your Zoom meetings — smart summaries, meeting prep, cross-meeting intelligence, and action item tracking. | [HADI-MeetingOps](https://github.com/hadi-technology/HADI-MeetingOps) |
| **phased-workflow** | Structured development methodology: Plan → Review → Approve → Implement → QA. Five phased skills enforcing four-eyes review and evidence-before-claims. | [phased-workflow](https://github.com/hadi-technology/phased-workflow) |
| **hadi-skills** | A collection of standalone AI workflow skills. Includes `/ob` — cache-first codebase orientation. | [hadi-skills](https://github.com/hadi-technology/hadi-skills) |

## How it works

The catalog lives in [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json). Each entry names a plugin and the git repository it ships from. When you add this marketplace, Claude Code reads that manifest and lets you install any listed plugin from its own repo.

## License

© HADI Technology. See individual plugin repositories for their respective licenses.
