# 平台接入状态

记录日期：2026-10-24。接入状态可能改变，每次发布前应重新核验。

| 平台 | 当前已核实的状态 | 发布前待办 |
| --- | --- | --- |
| GitHub | `lumingyu286-ux/chengrenbaike-night-guide` 已公开，GitHub Pages 已发布并核验。 | 后续内容更新须重新运行 Pages 工作流。 |
| Cloudflare Pages / Workers | Cloudflare Pages 项目 `chengrenbaike-night-guide` 已发布并核验；本站为纯静态内容。 | 后续更新按项目的部署方式重新发布。 |
| GitLab Pages | `lumingyu286/chengrenbaike-night-guide` 已从公开 GitHub 仓库导入，项目公开；GitLab 要求先完成账号身份验证，尚无法运行 CI 流水线。 | 账号持有人完成 GitLab 验证后，在 `main` 上启动流水线与手动作业，再核验 Pages 地址。 |
| Google Sites | `chengrenbaike-night-guide` 已使用原生页面编辑器发布并核验，含首页、主题海报、夜读指南与可见主站外链。 | 内容修改后在编辑器中重新发布。 |

已发布的网址见 [`sites.csv`](sites.csv)。不要把浏览器登录误认为 CLI 已授权。
