<!-- Generated: 2026-05-18 | Files scanned: 2 | Token estimate: ~200 -->

# Architecture

## Project Type

GitHub Profile README repository — renders on `github.com/hugo617`.

## File Tree

```
hugo617/
├── README.md                    # Profile README (rendered on profile page)
├── .github/workflows/snake.yml  # Daily snake animation generation
├── output/ (branch)             # Deployed by GitHub Actions
│   ├── github-snake.svg         # Light theme snake SVG
│   └── github-snake-dark.svg    # Dark theme snake SVG
└── docs/CODEMAPS/               # Project documentation
```

## Data Flow

```
Developer edits README.md
        │
        ▼
GitHub renders on profile page ──► External SVG/Badge services (on-demand)
        │                              │
        │                              ├── capsule-render (header/footer)
        │                              ├── readme-typing-svg (animation)
        │                              ├── github-readme-stats (cards, pins, langs)
        │                              ├── streak-stats (streak)
        │                              ├── skillicons.dev (icons)
        │                              └── komarev.com (views)
        │
GitHub Actions (cron daily)
        │
        ├── snake.yml: Platane/snk → gh-pages → `output` branch
        └── 3d-contrib.yml: yoshi389111 → `3d-contribution` branch
```

## Key Decisions

| Decision | Choice | Rationale |
|----------|--------|-----------|
| Content-first layout | Projects above stats | Visitors care about your work, not decorations |
| Snake deployment | `output` branch via gh-pages | Standard pattern, avoids main branch pollution |
| 3D Calendar | `3d-contribution` branch via action | Isometric contribution view, complements snake |
| Theme | `radical` dark (`bg_color=0d1117`) | Matches GitHub dark mode default |
| External service budget | ~14 requests | Down from 22+, faster load, fewer failure points |
