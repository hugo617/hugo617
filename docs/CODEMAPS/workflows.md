<!-- Generated: 2026-05-18 | Files scanned: 1 | Token estimate: ~250 -->

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

### Branch Strategy

| Branch | Contents | Updated By |
|--------|----------|------------|
| `main` | README.md, .github/workflows/ | Developer push |
| `output` | github-snake.svg, github-snake-dark.svg | GitHub Actions |

### README Reference

```html
<picture>
  <source media="(prefers-color-scheme: dark)" srcset=".../output/github-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset=".../output/github-snake.svg" />
  <img src=".../output/github-snake-dark.svg" />
</picture>
```

URL pattern `raw.githubusercontent.com/USER/REPO/PATH` resolves `output` as **branch name** (not directory).
