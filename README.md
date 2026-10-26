# How to Actually Not Build a Website — templates

Every file and prompt from the Jeyd bot video **How to Actually Not Build a Website**. Steal them.

Video: <YOUTUBE LINK>  ·  Channel: https://www.youtube.com/@jeydbot
The result (Flowly, a fictional startup): https://grassy-zenith-54ht.here.now/

## What's here

```
templates/            blank files to copy into your project
  BRIEF.md
  AGENTS.md           rename to CLAUDE.md if you use Claude Code
  refs/NOTES.md
  refs/SOURCES.md
example-flowly/       the filled-in files used for Flowly in the video
prompts/
  01-build.md         the build prompt
  02-corrections.md   the follow-up prompts, round by round
CHECKLIST.md          the whole route on one page
```

## The route

1. **Set up the folder**
   ```bash
   mkdir -p myproject/refs && cd myproject
   cp -r path/to/this-repo/templates/* .
   ```
2. **References.** Pick one designer you love, or 3 to 5 sites with one shared feel. Where to look: [Awwwards](https://www.awwwards.com/websites/), [Recent (formerly Godly)](https://recent.design), [Land-book](https://land-book.com), [Mobbin](https://mobbin.com), [Dribbble](https://dribbble.com/shots). Screenshot into `refs/`, log each in `refs/SOURCES.md`, then write `refs/NOTES.md`.
3. **Brief.** Fill `BRIEF.md` like you're briefing a human art director. Only real facts.
4. **Rules.** Keep `AGENTS.md` (or `CLAUDE.md`).
5. **Design skill.** Needs Node 22+ and Chrome, Edge or Chromium.
   ```bash
   npx skills add https://github.com/Leonxlnx/taste-skill --skill "design-taste-frontend"
   ```
   Full repo: https://github.com/Leonxlnx/taste-skill. It lands in `.claude/skills/` (Claude Code) or `.agents/skills/` (Codex). Alternatives: [Impeccable](https://github.com/pbakaus/impeccable), [Hallmark](https://github.com/nutlope/hallmark).
6. **Build.** Paste `prompts/01-build.md`.
7. **Browser loop.** Never accept round 1. Use `prompts/02-corrections.md` as patterns. Optional browser check: [Playwright MCP](https://github.com/microsoft/playwright-mcp)
   ```bash
   claude mcp add playwright npx @playwright/mcp@latest      # Claude Code
   codex mcp add playwright npx "@playwright/mcp@latest"     # Codex
   ```
8. **Ship it free** with [here.now](https://here.now):
   ```bash
   npx skills add heredotnow/skill --skill here-now -g
   ```
   Then tell your agent: "publish this folder to here.now". Without an account the link expires after 24 hours; a free account or the claim link keeps it.

## Everything mentioned in the video

### Design skills
- **Taste Skill** (the one used in the video): https://github.com/Leonxlnx/taste-skill
  ```bash
  npx skills add https://github.com/Leonxlnx/taste-skill --skill "design-taste-frontend"
  ```
  Claude Code plugin instead: `/plugin marketplace add Leonxlnx/taste-skill` then `/plugin install taste-skill@taste-skill`.
  Codex plugin instead: `codex plugin marketplace add Leonxlnx/taste-skill` then `codex plugin add taste-skill@taste-skill` (start a new session afterwards).
  A full build takes roughly 30-45 minutes and a few hundred thousand tokens (per its README). It checks your page at 3 widths.
- **Impeccable**: https://github.com/pbakaus/impeccable
  ```bash
  npx impeccable install            # then /impeccable init in your agent
  npx impeccable detect index.html  # lint any page, no AI needed
  ```
- **Hallmark**: https://github.com/nutlope/hallmark (checks your page at 8 widths, Node 18+)
  ```bash
  npx skills add nutlope/hallmark -g
  ```

### Shipping
- **here.now skill**: https://github.com/heredotnow/skill · docs https://here.now/docs · pricing https://here.now/pricing.md
  ```bash
  npx skills add heredotnow/skill --skill here-now -g
  ```

### Browser checks
- **Playwright MCP**: https://github.com/microsoft/playwright-mcp
- **Playwright CLI** (more token-efficient, per the Playwright README): https://github.com/microsoft/playwright-cli

### The skills installer
- `npx skills`: https://github.com/vercel-labs/skills · browse skills at https://skills.sh

### Agent docs (skills + instruction files)
- Claude Code: https://code.claude.com/docs/en/skills · https://code.claude.com/docs/en/memory
- Codex: https://developers.openai.com/codex/skills · https://developers.openai.com/codex/guides/agents-md
- OpenCode: https://opencode.ai/docs/skills · https://opencode.ai/docs/rules

## Notes

- Flowly is fictional sample content: company, people and prices are made up for the episode.
- Flowly's visual direction came from studying the editorial work of Syed Saboor (https://saboor.studio/). Nothing was copied; all rights stay with him and his clients. Reference screenshots are not included in this repo.

Built your own? Drop the live link in the video comments.
