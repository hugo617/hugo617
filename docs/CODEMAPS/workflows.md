<!-- Generated: 2026-05-19 | Files scanned: 2 | Token estimate: ~350 -->

# GitHub Actions Workflows

## snake.yml — Generate Snake Animation

```
Trigger:  cron (daily midnight UTC) + manual (workflow_dispatch)
Timeout:  10 minutes
Perms:    contents: write
```

### Pipeline

```
checkout@v4
    │
    ▼
Platane/snk/svg-only@v3
    ├── Input:  github_user_name=hugo617
    └── Output: dist/github-snake.svg (light)
               dist/github-snake-dark.svg (dark palette)
    │
    ▼
crazy-max/ghaction-github-pages@v4
    ├── target_branch: output
    ├── build_dir: dist
    └── auth: GITHUB_TOKEN (auto-provided)
```

## 3d-contrib.yml — 3D Contribution Calendar

```
Trigger:  cron (daily midnight UTC) + manual (workflow_dispatch)
Timeout:  10 minutes
Perms:    contents: write
```

### Pipeline

```
checkout@v3
    │
    ▼
yoshi389111/github-profile-3d-contrib@0.7.0
    ├── USERNAME: hugo617
    ├── MAX_REPOS: 100
    ├── EXCLUDE: andrej-karpathy-skills, cc-glm-status
    └── Deploys to: 3d-contribution/ branch
```

## Branch Strategy

| Branch | Contents | Updated By |
|--------|----------|------------|
| `main` | README.md, .github/workflows/, docs/ | Developer push |
| `output` | github-snake.svg, github-snake-dark.svg | snake.yml |
| `3d-contribution` | city-night-profile.svg, city-day-profile.svg | 3d-contrib.yml |

## First-Time Setup

After pushing to GitHub:
1. Go to Actions tab → select each workflow → "Run workflow"
2. Verify SVGs appear on `output` and `3d-contribution` branches
3. Refresh profile page to see rendered snake and 3D calendar
