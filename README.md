# wenxuecity-news-rankings（OpenClaw/Codex 技能 / Skill）

这个仓库包含一个技能，用于抓取并整理文学城新闻频道的 24 小时排行：

- https://www.wenxuecity.com/news/

This repo contains a skill that fetches and formats Wenxuecity News 24-hour rankings from:

- https://www.wenxuecity.com/news/

它会提取：

- `24小时热点排行` (24-hour hot ranking)
- `24小时讨论排行` (24-hour discussion ranking)

It extracts:

- `24小时热点排行` (24-hour hot ranking)
- `24小时讨论排行` (24-hour discussion ranking)

## Skill 位置 / Location

- Skill folder: `wenxuecity-news-rankings/`
- Entry script: `wenxuecity-news-rankings/scripts/fetch_rankings.py`

## 依赖 / Requirements

- Python 3.10+（仅标准库，无额外依赖 / standard library only）
- 可访问 `www.wenxuecity.com` 的网络

## 用法 / Usage

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

输出 JSON / Output JSON:

```bash
python3 scripts/fetch_rankings.py --format json --pretty --output rankings.json
```

## 参数 / Options

- `--top N`: keep only top N items (default: 15; use `--top 0` for all available)
- `--format md|json`: output format
- `--include-images`: include `image_url` in JSON and embed images in Markdown
- `--output FILE`: write output to a file

## 备注 / Notes

- 页面可能本身就少于你请求的条目数（例如“热点排行”有时只有 5 条）。脚本会输出“实际存在的”条目。
- The source page may expose fewer items than requested (e.g., hot ranking sometimes shows only 5 entries). The script outputs what is available.

## 部署到 OpenClaw（示例）/ Deploy to OpenClaw (example)

如果你的 OpenClaw skills 目录是 `~/.openclaw/skills`：

If your OpenClaw skills directory is `~/.openclaw/skills`:

```bash
scp -r wenxuecity-news-rankings cici@192.168.1.169:~/.openclaw/skills/
ssh cici@192.168.1.169 'cd ~/.openclaw/skills/wenxuecity-news-rankings && python3 scripts/fetch_rankings.py --format md'
```
