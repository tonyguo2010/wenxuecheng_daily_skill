# wenxuecity-news-rankings (OpenClaw/Codex skill)

This repo contains a skill that fetches and formats Wenxuecity News 24-hour rankings from:

- https://www.wenxuecity.com/news/

It extracts:

- `24小时热点排行` (24-hour hot ranking)
- `24小时讨论排行` (24-hour discussion ranking)

## Skill location

- Skill folder: `wenxuecity-news-rankings/`
- Entry script: `wenxuecity-news-rankings/scripts/fetch_rankings.py`

## Requirements

- Python 3.10+ (standard library only; no extra dependencies)
- Network access to `www.wenxuecity.com`

## Usage

Windows (PowerShell):

```powershell
cd wenxuecity-news-rankings
py scripts\fetch_rankings.py --format md
```

Linux/macOS (bash/zsh):

```bash
cd wenxuecity-news-rankings
python3 scripts/fetch_rankings.py --format md
```

Output JSON:

```bash
python3 scripts/fetch_rankings.py --format json --pretty --output rankings.json
```

## Options

- `--top N`: keep only top N items (default: 15; use `--top 0` for all available)
- `--format md|json`: output format
- `--include-images`: include `image_url` in JSON and embed images in Markdown
- `--output FILE`: write output to a file

## Notes

- The source page may expose fewer items than requested (e.g., hot ranking sometimes shows only 5 entries). The script outputs what is available.

## Deploy to OpenClaw (example)

If your OpenClaw skills directory is `~/.openclaw/skills`:

```bash
scp -r wenxuecity-news-rankings cici@192.168.1.169:~/.openclaw/skills/
ssh cici@192.168.1.169 'cd ~/.openclaw/skills/wenxuecity-news-rankings && python3 scripts/fetch_rankings.py --format md'
```

