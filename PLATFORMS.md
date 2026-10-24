# 平台接入状态

记录日期：2026-10-24。接入状态可能改变，每次发布前应重新核验。

| 平台 | 当前已核实的状态 | 发布前待办 |
| --- | --- | --- |
| GitHub | 当前聊天可通过已连接的 GitHub 工具读取账号 `lumingyu286-ux`；核验时该账号尚无仓库。 | 为具体站点创建仓库并设置 GitHub Pages。 |
| Cloudflare Pages / Workers | 浏览器中已登录 Cloudflare；其 GitHub App 已安装且可访问该账号的全部仓库。上次查看时账号没有可导入的仓库。 | 新站确定后创建仓库，再连接 Pages Git 自动部署；或使用有权限的 Cloudflare 插件 / CLI。 |
| GitLab Pages | 尚未核实账号连接。 | 按需连接 GitLab，确认仓库与 Pages 流水线权限。 |
| Google Sites | 尚未核实账号连接。 | 按需确认 Google 账号与网站编辑 / 发布权限。 |

Cloudflare 本地 Wrangler 的设备授权曾被 Cloudflare 安全检查拦截；这不影响先用 Git 仓库接入 Pages 的方案。不要把浏览器登录误认为 CLI 已授权。
