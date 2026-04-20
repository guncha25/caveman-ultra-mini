# caveman-ultra-mini

Ultra-terse response style for coding agents. Cuts filler, preserves technical meaning, reduces tokens.

## Features
- Always-on ultra-caveman style
- Installable skill (`npx skills add`)
- Auto-activation:
  - Claude Code via `CLAUDE.md`
  - GitHub Copilot via `AGENTS.md` + `.github/copilot-instructions.md`
- Claude custom slash commands:
  - `/caveman`
  - `/caveman-help`
- Copilot CLI support via `/agent` (select installed agent)

## Repo Layout
```
skills/
  caveman-ultra-mini/
    SKILL.md
  caveman-help/
    SKILL.md

.claude/commands/
  caveman.md
  caveman-help.md

CLAUDE.md
AGENTS.md
.github/copilot-instructions.md
```

## Install

### Claude Code
```bash
npx skills add YOUR_USERNAME/caveman-ultra-mini --skill caveman-ultra-mini -a claude-code
```

### GitHub Copilot (CLI)
```bash
npx skills add YOUR_USERNAME/caveman-ultra-mini --skill caveman-ultra-mini -a github-copilot
```

### List available skills
```bash
npx skills add YOUR_USERNAME/caveman-ultra-mini --list
```

## Usage

### Claude Code
- Open repo → style auto-applies via `CLAUDE.md`
- Optional:
  - `/caveman` to enable
  - `/caveman-help` for quick reference

### Copilot CLI
- Start interactive mode
- Run `/agent` → select `caveman-ultra-mini`
- Or prompt explicitly: `Use caveman-ultra-mini to explain this error`

## Behavior (Ultra Caveman)
- Keep meaning. Cut words.
- No filler/pleasantries/hedging.
- Fragments OK. Short words preferred.
- Abbrev when obvious: cfg, env, req, res, auth, DB, fn, impl.
- Arrows for cause/effect: `X -> Y`.
- Preserve code/commands/errors/logs exactly.
- Ask only if blocked by missing critical info.

### Format
`[issue] -> [cause] -> [fix]`

### Examples
- `Heap low -> OOM. Increase --max-old-space-size.`
- `Auth fail -> token expired. Refresh token.`
- `Build break -> missing env var API_KEY.`

## Disable
Say: `normal mode` or `stop caveman`.

## Notes
- Claude custom slash commands live in `.claude/commands/`.
- Copilot uses repo instructions + `/agent` for activation.