# Inkline

A design skill for Claude: a quiet, editorial style for personal and project sites. It uses one column, one typeface (Space Mono), one accent colour, hairline dividers, numbered sections, and lets the numbers do the bragging.

Once installed, ask Claude for a portfolio, project page, landing page, one-pager or slides "in the Inkline style" (or just "clean and minimal, monospace") and it follows the rules in `skills/inkline/SKILL.md`.

## What's inside

```
skills/inkline/
  SKILL.md                 the design rules, type scale, layout patterns, checklist
  assets/tokens.css        colours (light + dark), font, spacing, base classes, entrance animation
  references/patterns.html canonical markup for nav, hero, sections, entries, stat rows, contact
```

## Install

### Claude Code

```
/plugin marketplace add OWNER/inkline
/plugin install inkline@inkline
```

Or copy `skills/inkline/` into `~/.claude/skills/` (all projects) or `.claude/skills/` (one project).

### Claude apps (claude.ai, desktop)

Download `inkline.skill` from the latest [release](../../releases), then add it from the Skills section of your Claude settings.

## Preview

Open `skills/inkline/references/patterns.html` in a browser to see every pattern in light or dark mode.

## License

MIT
