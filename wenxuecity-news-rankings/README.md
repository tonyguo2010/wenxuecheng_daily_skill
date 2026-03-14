# Wenxuecity News Rankings Skill

Fetch and format Wenxuecity News 24-hour rankings from https://www.wenxuecity.com/news/:

- `24小时热点排行`
- `24小时讨论排行`

## Run

Windows (PowerShell):

```powershell
py scripts\fetch_rankings.py --format md
```

Linux/macOS:

```bash
python3 scripts/fetch_rankings.py --format md
```

## Common flags

- `--top N` (default: 15; use `--top 0` for all)
- `--format md|json`
- `--pretty` (JSON)
- `--output FILE`

