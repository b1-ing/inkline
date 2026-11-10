---
name: inkline
description: Inkline, a quiet editorial design style for personal and project sites. It uses a single column, Space Mono only, warm off-white or ink backgrounds, one deep blue accent, hairline dividers, numbered sections, a date column, and numbers as the highlights. Use this skill whenever the user asks for the "Inkline" style, or for a clean, minimal, monospace or "engineering notebook" look, for portfolio sites, personal homepages, project or research pages, landing pages, mockups, CV or résumé pages, one-pagers, slides or UI components. Also use it when they ask to make something match an existing Inkline page, even if they don't name the style.
---

# Inkline

A design language that reads like a well-typeset engineering notebook: one monospace typeface, one narrow column, lots of whitespace, and evidence (numbers, results) doing the talking instead of decoration.

Files in this skill:
- `assets/tokens.css` — colours (light + dark), font import, column, spacing, base classes, entrance animation. Start every build by copying or inlining this.
- `references/patterns.html` — canonical markup for each pattern below (nav, hero, section header, entry, finding-led entry, stat row, list row, contact). Read it before building anything with more than two sections, and adapt from it rather than inventing new patterns.

## Principles

1. **One column.** Everything (nav, hero, sections, footer) shares a single 720px centred column with 24px side padding, so every left edge lines up. Never widen one section on its own.
2. **One typeface.** Space Mono only, 400 and 700 plus 400 italic. Hierarchy comes from size, weight and colour, never from a second font.
3. **One accent.** Deep signal blue (`#1F4FD8` light / `#7FA2FF` dark) for links, key numbers and at most one highlighted phrase per hero. A burnt-orange `--attention` (#C2410C) exists only for a single "odd one out" moment (an attacker, a warning) — use it rarely or not at all.
4. **Let numbers brag.** Put concrete figures in a mono stat row with `·` separators and the numbers in accent: `3 agents · 17 tools · 90% correctness`. Avoid adjectives like "passionate" or "innovative".
5. **Hairlines, not boxes.** Separate sections with a 1px `--border` top rule and 48px padding. No drop shadows, no gradients, no left accent bars, no coloured card backgrounds. Cards (`--surface`, 1px border, 10px radius) are reserved for genuinely separate objects like a featured project or a screenshot frame.
6. **Quiet motion.** Hero items rise in once, staggered; everything else is static or fades up 8px once on scroll. Always disabled under `prefers-reduced-motion`. No parallax, typing effects, particles or cursor trails.

## Tokens

| Token | Light | Dark |
| --- | --- | --- |
| `--bg` | #FAFAF7 | #0F1115 |
| `--surface` | #FFFFFF | #171A20 |
| `--text` | #1A1A1A | #E8E6E1 |
| `--muted` | #5E5E59 | #A3A097 |
| `--border` | #E6E4DE | #2A2E36 |
| `--accent` | #1F4FD8 | #7FA2FF |
| `--accent-soft` | #E8EEFC | #1C2540 |

Dark mode follows `prefers-color-scheme` and can be forced with `data-theme` on `<html>`; both are wired in `tokens.css`. Always design and check both.

## Type scale

| Role | Size | Weight / style |
| --- | --- | --- |
| Name / page title | 52px (40px on phones), line-height 1.1, letter-spacing -0.03em | 700 |
| Section heading | 26px, letter-spacing -0.02em, preceded by a muted 13px number (`01`, `02`…) | 700 |
| Tagline | 18px, max 56ch | 400 |
| Item title | 17–18px | 700 |
| Body | 15px, line-height 1.7 | 400 |
| Finding / pull sentence | 17px | italic |
| Metadata, dates, captions | 13px, letter-spacing 0.02em, `--muted` | 400 |
| Tags | 12px pill on `--accent-soft` | 400 |

## Layout patterns

- **Nav:** 64px tall, bold initials left, 13px links and a 44px round theme toggle right, hairline below. Collapse links into a menu under ~640px.
- **Hero:** ~104px top padding. Text stack (location/meta line → name → tagline → short first-person summary in muted → accent text links) with an optional ~220px round photo on the right that wraps below on phones.
- **Section:** numbered heading, then content with 24–36px gaps.
- **Entry:** 140px muted date column + content (title, one sentence, stat row, muted tool list). Built with flex-wrap so the date stacks above the content on narrow screens — no media query needed.
- **Finding-led entry** (research, case studies): title, meta line, the result as one italic sentence, 2–3 bullets, tags.
- **List row** (awards, publications): hairline-separated rows using the same date column, bold title plus one muted line.
- **Featured project:** browser-frame screenshot card, then title + stat row on one line, description, accent "Live site →" / "GitHub →" links.
- **Contact:** muted one-liner about what you're open to, then the email large (30px bold, accent).
- **Footer:** hairline, 12px muted copyright.

## Adapting to other formats

- **Slides:** same tokens and font; one idea per slide, left-aligned, slide number in the corner as a muted `01`; big numbers in accent as the visual.
- **Documents / one-pagers:** same column logic at print width, numbered section headings, date column for timelines.
- **Small components:** reuse the tag, stat row and hairline rules; don't add new colours.

## Checklist before delivering

- All left edges align to the one column.
- Only Space Mono, only the tokens above.
- Accent used for links, key numbers and at most one hero phrase.
- Contrast AA in both themes; visible accent focus rings; 44px touch targets.
- Works at 360px, 768px and 1440px.
- Motion respects `prefers-reduced-motion`.
- Every claim is concrete; placeholders are in `[brackets]`, never invented facts.
