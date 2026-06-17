# pulse-design-system-sync

A portable agent **skill** that keeps the Pulse design system in sync across its
three layers — Markdown rules/contracts, the React/CSS implementation, and the
single-file handoff HTML used for Figma iteration.

It works in **both Codex CLI and Claude Code** from the same folder. The skill
contract lives in `SKILL.md` (shared); `agents/openai.yaml` is Codex-only
interface metadata that Claude Code simply ignores.

## Files

| File | Used by | Purpose |
| --- | --- | --- |
| `SKILL.md` | Codex + Claude | Name, description (routing), and the workflow the agent follows. |
| `references/workflow.md` | Codex + Claude | Layer responsibilities, sync matrix, intake flow, roadmap order. Loaded on demand. |
| `agents/openai.yaml` | Codex only | Display name / short description / default prompt for the Codex UI. Harmless to Claude. |

## Install

The skill name (`pulse-design-system-sync`) must match the folder name in each
location.

### Codex CLI

```sh
# clone or copy this repo into the Codex skills dir
git clone https://github.com/xuan-ryu/pulse-design-system-sync.skill.git \
  ~/.codex/skills/pulse-design-system-sync
```

### Claude Code

Personal (available in every project):

```sh
git clone https://github.com/xuan-ryu/pulse-design-system-sync.skill.git \
  ~/.claude/skills/pulse-design-system-sync
```

Or project-scoped (committed with a repo): copy the folder to
`.claude/skills/pulse-design-system-sync/` inside that project.

> Tip: to keep one working copy in sync with both tools, clone once and symlink
> it into `~/.codex/skills/` and `~/.claude/skills/`.

## Activation

After installing, start a **new session** so the tool picks up the skill. Then
trigger it with requests like "update the design system", "sync this to the
component library", or "reflect this in the handoff HTML".
