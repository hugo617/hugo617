<!-- Generated: 2026-05-19 | Files scanned: 1 | Token estimate: ~350 -->

# Profile README Structure

## Sections (top → bottom)

| # | Section | External Services |
|---|---------|-------------------|
| 1 | **Header** — capsule-render waving gradient + name/title | `capsule-render.vercel.app` |
| 2 | **Typing SVG** — rotating taglines (h3) | `readme-typing-svg.demolab.com` |
| 3 | **Contact Badges** — Email, GitHub, Views | `img.shields.io`, `komarev.com` |
| 4 | **Neofetch Terminal** — bash-style bio + donut chart (right) | `github-readme-stats.vercel.app` (top-langs) |
| 5 | **Featured Projects** — 4 pin cards + collapsible table (6 more) | `github-readme-stats.vercel.app` (pin) |
| 6 | **GitHub Stats** — Stats card + Streak card | `github-readme-stats`, `streak-stats.demolab.com` |
| 7 | **Tech Stack** — skill icons row | `skillicons.dev` |
| 8 | **Contribution Viz** — Snake + 3D Calendar (merged) | `raw.githubusercontent.com` |
| 9 | **Footer** — capsule-render waving | `capsule-render.vercel.app` |

## Design Tokens

```
bg_color:      0d1117 (GitHub dark)
title_color:   58A6FF (GitHub blue)
text_color:    c9d1d9 (GitHub light gray)
accent_color:  bc8cff (purple, streak/fire)
```

## Featured Repos (verified on GitHub)

| Repo | Description | Category |
|------|-------------|----------|
| `openclaw-admin` | AI Agent framework dashboard | AI Tooling |
| `hello-agents` | AI Agent fundamentals tutorial | AI Education |
| `claude-code-website` | Claude Code companion site | AI Tooling |
| `healthcare-admin` | Healthcare admin platform | Full Stack |
| `resume` | Next.js resume site | Full Stack |
| `andrej-karpathy-skills` | CLAUDE.md skills from Karpathy | AI Tooling |
| `devtools-mcp-website` | DevTools MCP companion site | AI Tooling |
| `hanzi-ai-study` | Chinese character AI learning | AI Education |
| `life_coach` | Life coaching tools | Misc |
| `md2docx` | Markdown to Word converter | Python Tool |

## Architecture Decisions

- Content-first: Featured Projects promoted above stats
- Substance over decoration: removed trophies, random quote, activity graph
- Reduced external requests from 22+ to ~14
- Snake + 3D Calendar require workflows to run before SVGs exist
