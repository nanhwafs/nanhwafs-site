# 旧站（SiteHub）→ 新站 URL 对照（2026-09-29）

旧站 sitemap 共 24 条，处理方式：

| 类别 | 条数 | 处理 |
|---|---|---|
| 同路径，新站自然接住（`/` `/history` `/about` `/organization` `/news`） | 5 | 无需规则；GitHub Pages 会自动把 `/about` 补成 `/about/` |
| 路径不同，需 301 | 17 | 见 `redirects.csv`（Cloudflare Bulk Redirects 可直接导入） |
| 新站尚无对应页（`/legal-notice` `/privacy`） | 2 | 待校方提供真实文本后建 `/legal-notice/` `/privacy/`；建好前不设规则 |

`redirects.csv` 每条目标文件与锚点已用脚本逐条核对存在（17/17）。

## 前提

- 域名 DNS 切到 GitHub Pages 之前，这份表不生效。
- GitHub Pages 本身做不了服务端 301。仓库里已为这 17 个旧路径各放一个跳转页（`<旧路径>/index.html`：meta refresh 0 秒＋canonical＋noindex），不依赖 Cloudflare 也能接住旧链接；搜索引擎把 0 秒 meta refresh 视同永久跳转。日后若 Cloudflare 记录开橙云，可再导入 `redirects.csv` 换成真 301。
- 旧站 8 个 `/events/*` 文章已全部在新站按年新闻馆里找到对应原文（同一 FB 源帖）。
