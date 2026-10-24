# 成人百科 · 夜读入口：发布准备

静态站文件在 `public/`；发布目录的根文件必须是非空的 `public/index.html`。本站是三页原创成人话题与海报导览：**首页、主题海报、夜读指南**。首页标题为「成人百科入口｜成年人的夜间探索指南」，描述为「从亲密关系、成人话题与夜间灵感出发，浏览原创主题海报，点击前往成人百科 chengrenbaike.com 探索更多。本站为独立导览。」本目录的配置只作发布准备，正式发布须先完成本地桌面与手机预览并获得用户确认。四个平台的正式网址只有发布后才能登记到项目根目录的 `sites.csv`，不要预填。

站内页面与资源链接使用相对路径，并在正式网址核验多页导航、手机布局及指向 `https://chengrenbaike.com/` 的可见链接。新建项目或独立仓库时建议使用 `chengrenbaike-night-guide` 作为公开地址代号（以平台实际可用名称为准）；Cloudflare Workers 配置已采用该名称。GitHub 项目站可能位于 `/仓库名/` 子路径；GitLab Pages 也可能使用项目子路径或独立域名。

## Cloudflare Pages（Git 集成）

1. 在用户确认预览后，推送包含本站的仓库，再到 Cloudflare **Workers & Pages → Create application → Pages → Import an existing Git repository** 连接该仓库。
2. 生产分支选实际默认分支；**Root directory** 设为 `sites/duanju-guide`，**Build command** 留空，**Build output directory** 设为 `public`。若控制台要求非空构建命令，可填 `exit 0`。
3. 部署完成后从控制台读取实际 `pages.dev` 地址；检查首页、内页、手机尺寸和主站外链，再登记 `sites.csv`。Git 集成会在后续推送时触发新部署，连接后不要把未经确认的改动推到生产分支。

此仓库为多站结构；Cloudflare Pages 支持不同项目各设根目录，官方文档列出同一仓库最多 5 个 Pages 项目的限制。若选择 **Direct Upload** 创建项目，之后无法将该项目改为 Git 集成，需另建项目。

官方资料：[Pages 构建配置](https://developers.cloudflare.com/pages/configuration/build-configuration/)、[多站仓库](https://developers.cloudflare.com/pages/configuration/monorepos/)、[Direct Upload](https://developers.cloudflare.com/pages/get-started/direct-upload/)。

## Cloudflare Workers（静态资源）

1. 在用户确认预览后，确认 Cloudflare CLI 已授权，然后进入 `sites/duanju-guide/`。
2. 使用本目录的 `wrangler.jsonc`，运行 `npx wrangler deploy`。它将 `public/` 作为静态资源发布；纯静态站不需要 Worker 脚本或额外的资源绑定。配置里的 Worker 名称若在账号内已被占用，应先选定可用名称并更新配置。
3. 从命令输出或控制台取得实际 `workers.dev` 地址，核验后登记 `sites.csv`。

官方资料：[Workers 静态资源最佳实践](https://developers.cloudflare.com/workers/best-practices/workers-best-practices/)、[Wrangler 配置](https://developers.cloudflare.com/workers/wrangler/configuration/)。

## GitHub Pages

1. 在用户确认预览后，将此多站仓库推送至有权限的 GitHub 仓库。在仓库 **Settings → Pages → Build and deployment** 中将 **Source** 设为 **GitHub Actions**。
2. 在 **Actions** 中手动运行仓库根目录的 `.github/workflows/duanju-guide-pages.yml`。工作流只上传 `sites/duanju-guide/public/`，不用在仓库设置任何发布令牌。
3. 从 Pages 设置或工作流结果读取实际网址，核验后登记 `sites.csv`。

GitHub Pages 的分支发布源只允许仓库根目录或 `/docs`，不能直接选 `sites/duanju-guide/public/`；所以工作流必须放在仓库根目录的 `.github/workflows/`。一个 GitHub 仓库最多发布一个 Pages 项目站，此工作流将该仓库的 Pages 站用于「成人百科 · 夜读入口」；未来其他独立站需要其他仓库。当前工作流只有手动触发器，准备文件不会自动发布。若将本站复制为独立仓库，需把工作流里的 `sites/duanju-guide/public` 改为独立仓库中的实际目录。

官方资料：[选择发布源](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)、[每仓库站点数量](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages)、[GitHub Actions 发布示例](https://docs.github.com/en/get-started/start-your-journey/deploying-your-website-automatically)。

## GitLab Pages

1. 在用户确认预览后，将此仓库推送至启用了 CI/CD Runner 与 Pages 的 GitLab 项目。
2. 在默认分支的 **Build → Pipelines** 手动启动 `deploy_chengrenbaike_night_guide_pages` 作业。仓库根目录 `.gitlab-ci.yml` 以 `pages.publish` 指向 `sites/duanju-guide/public`，并检查 `index.html` 非空。
3. 作业与 Pages 部署完成后，在 **Deploy → Pages** 读取实际网址，核验后登记 `sites.csv`。

GitLab 的 CI 配置需要放在仓库根目录；`pages.publish` 可以指定默认 `public/` 之外的发布目录。此作业限定默认分支且设为手动。若将本站复制为独立仓库，需同步修改 `.gitlab-ci.yml` 内的发布目录路径。

官方资料：[Pages 的 CI 配置](https://docs.gitlab.com/ci/yaml/#pages)、[Pages 设置与发布目录](https://docs.gitlab.com/user/project/pages/introduction/)。

## Google Sites

Google Sites 使用自己的页面编辑器和发布流程，不能直接把本项目的 `public/` 当作 Sites 原生站点上传。可依据本站已确认的内容与视觉，在 Google Sites 中创建页面、导航和可见的 `https://chengrenbaike.com/` 外链；也可用 **Insert → Embed** 嵌入 HTML/CSS/JS 片段，或嵌入一个已发布的网站页面。部分外部网站会阻止嵌入，嵌入版也要单独检查手机布局和交互。

先用编辑器的 **Preview** 检查；得到用户确认后点击 **Publish**，选择站点网址和可见范围。发布后打开实际网址核验，再登记 `sites.csv`。Google Sites 的导航可用 **Pages → New link** 添加外部网址。

官方资料：[嵌入内容和代码](https://support.google.com/sites/answer/90569)、[页面和导航外链](https://support.google.com/sites/answer/98216)、[预览与发布](https://support.google.com/sites/answer/6372880)。
