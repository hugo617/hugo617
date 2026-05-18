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
        │                              ├── github-readme-stats (cards)
        │                              ├── streak-stats (streak)
        │                              ├── activity-graph (graph)
        │                              ├── github-profile-trophy
        │                              ├── skillicons.dev (icons)
        │                              └── komarev.com (views)
        │
GitHub Actions (cron daily)
        │
        ├── Platane/snk/svg-only@v3 ──► Generate snake SVGs
        └── ghaction-github-pages@v4 ► Deploy to `output` branch
```

## Key Decisions

| Decision | Choice | Rationale |
|----------|--------|-----------|
| Snake deployment | Separate `output` branch via gh-pages | Standard pattern, avoids main branch pollution |
| Theme | `radical` dark (`bg_color=0d1117`) | Matches GitHub dark mode default |
| Stats host | vercel.app (readme-stats, streak-stats, activity-graph) | Reliable, free, no self-hosting |
