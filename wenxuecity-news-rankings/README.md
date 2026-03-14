# 文学城新闻 24 小时排行技能 / Wenxuecity News Rankings Skill

抓取并整理文学城新闻频道 https://www.wenxuecity.com/news/ 的两个 24 小时榜单：

- `24小时热点排行`
- `24小时讨论排行`

Fetch and format Wenxuecity News 24-hour rankings from https://www.wenxuecity.com/news/:

- `24小时热点排行`
- `24小时讨论排行`

## 运行 / Run

Windows (PowerShell):

```powershell
py scripts\fetch_rankings.py --format md
```

Linux/macOS:

```bash
python3 scripts/fetch_rankings.py --format md
```

## 常用参数 / Common flags

- `--top N` (default: 15; use `--top 0` for all)
- `--format md|json`
- `--pretty` (JSON)
- `--output FILE`
