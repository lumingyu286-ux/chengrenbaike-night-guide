# 平台接入状态

记录日期：2026-10-24。接入状态可能改变，每次发布前应重新核验。

| 平台 | 当前已核实的状态 | 后续操作 |
| --- | --- | --- |
| GitHub | `lumingyu286-ux/chengrenbaike-night-guide` 已公开，GitHub Pages 已发布并核验。 | 后续内容更新须重新运行 Pages 工作流。 |
| Cloudflare Pages / Workers | Cloudflare Pages 项目 `crbk` 已发布并核验，首选地址为 `https://crbk.pages.dev/`；原项目 `chengrenbaike-night-guide` 保留。本站为纯静态内容。 | 后续更新需向两个 Direct Upload 项目分别上传 `sites/duanju-guide/public/` 的最新文件。 |
| GitLab Pages | `lumingyu286/chengrenbaike-night-guide` 公开仓库已导入，网页源码已同步；用户决定暂时跳过 Pages 发布。GitLab 要求先完成账号身份验证，当前 CI 流水线无法运行。 | 仅在用户之后要求恢复发布时，再由账号持有人完成验证，并在 `main` 上运行 Pages 作业、核验正式地址。 |
| Google Sites | `chengrenbaike-night-guide` 已使用原生页面编辑器发布并核验，含首页、主题海报、夜读指南与可见主站外链。 | 内容修改后在编辑器中重新发布。 |

已发布的网址见 [`sites.csv`](sites.csv)。不要把浏览器登录误认为 CLI 已授权。
