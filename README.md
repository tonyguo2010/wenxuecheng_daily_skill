# Wenxuecity News Rankings Skill (OpenClaw/Codex)

[中文](#中文) | [English](#english)

---

## 中文

一个用于抓取并整理文学城新闻频道 24 小时排行的 OpenClaw/Codex 技能，数据来源：

- https://www.wenxuecity.com/news/

提取两块榜单：

- `24小时热点排行`
- `24小时讨论排行`

### 功能

- 抓取并输出两块 24 小时排行（Markdown / JSON）
- 默认 Top 15（如页面不足 15 条则输出实际条目）

### 文件位置

- Skill 目录：`wenxuecity-news-rankings/`
- 脚本入口：`wenxuecity-news-rankings/scripts/fetch_rankings.py`

### 前置准备

- Python 3.10+（仅标准库，无额外依赖）
- 可访问 `www.wenxuecity.com` 的网络

### 本地运行

```bash
cd wenxuecity-news-rankings
# Linux/macOS
python3 scripts/fetch_rankings.py --format md
```

Windows (PowerShell):

```powershell
cd wenxuecity-news-rankings
py scripts\fetch_rankings.py --format md
```

### 参数（常用）

- `--top N`：保留 Top N（默认 15；`--top 0` 输出页面实际全部）
- `--format md|json`：输出格式
- `--pretty`：JSON 美化输出
- `--output FILE`：写入文件
- `--include-images`：JSON 带 `image_url`，Markdown 嵌入图片

### OpenClaw 部署示例

（假设 OpenClaw skills 目录为 `~/.openclaw/skills`）

```bash
scp -r wenxuecity-news-rankings <user>@<host>:~/.openclaw/skills/
ssh <user>@<host> 'cd ~/.openclaw/skills/wenxuecity-news-rankings && python3 scripts/fetch_rankings.py --format md'
```

---

## English

An OpenClaw/Codex skill that fetches and formats Wenxuecity News 24-hour rankings from:

- https://www.wenxuecity.com/news/

It extracts:

- `24小时热点排行` (24-hour hot ranking)
- `24小时讨论排行` (24-hour discussion ranking)

### Features

- Fetch and output both 24-hour rankings (Markdown / JSON)
- Default Top 15 (if the page exposes fewer items, output what is available)

### Layout

- Skill folder: `wenxuecity-news-rankings/`
- Entry script: `wenxuecity-news-rankings/scripts/fetch_rankings.py`

### Prerequisites

- Python 3.10+ (standard library only; no extra dependencies)
- Network access to `www.wenxuecity.com`

### Local Run

```bash
cd wenxuecity-news-rankings
# Linux/macOS
python3 scripts/fetch_rankings.py --format md
```

Windows (PowerShell):

```powershell
cd wenxuecity-news-rankings
py scripts\fetch_rankings.py --format md
```

### Options (common)

- `--top N`: keep only Top N (default: 15; use `--top 0` for all available)
- `--format md|json`: output format
- `--pretty`: pretty-print JSON
- `--output FILE`: write output to a file
- `--include-images`: include `image_url` in JSON and embed images in Markdown

### OpenClaw deploy example

(Assuming your OpenClaw skills directory is `~/.openclaw/skills`)

```bash
scp -r wenxuecity-news-rankings <user>@<host>:~/.openclaw/skills/
ssh <user>@<host> 'cd ~/.openclaw/skills/wenxuecity-news-rankings && python3 scripts/fetch_rankings.py --format md'
```
