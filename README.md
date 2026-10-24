# 生成网站上传

本项目用于制作不同主题、内容和版式的网站，并按需发布到 Cloudflare Pages / Workers、GitHub Pages、GitLab Pages 或 Google Sites。每个站独立保存源码、预览与发布记录。站点中需要在合适的内容位置链接到 [chengrenbaike.com](https://chengrenbaike.com/)；链接应清晰可见，并与页面内容相关。

## 工作顺序

1. 确定站点主题、目标读者、栏目、发布平台和站名；填写 [`SITE_BRIEF.md`](SITE_BRIEF.md)。
2. 用 `frontend-design` 等设计 skill 制作独立的视觉方案，确定字体、布局、配色和移动端交互，再完成源码。
3. 本地运行并检查桌面与手机尺寸、导航、内容、图片、可访问性和外链。
4. 把成品预览交给用户看；根据反馈修改，并在用户确认后上传发布。
5. 检查正式网址可以打开，登记平台、仓库、预览、正式网址和日期到 [`sites.csv`](sites.csv)。

首个站点已建立在 [`sites/duanju-guide/`](sites/duanju-guide/)：**成人百科 · 夜读入口**，三页原创成人话题与海报导览，包含首页、主题海报和夜读指南。页面用亲密关系、边界与自我探索的主题灵感引导成年访客访问 [chengrenbaike.com](https://chengrenbaike.com/)；海报不代表目标站的具体内容。Cloudflare Pages、GitHub Pages、Google Sites 已发布；GitLab 公开仓库已导入，Pages 流水线仍需账号身份验证。实际网址与状态记录在 [`sites.csv`](sites.csv)，更新流程见 [`PUBLISH.md`](sites/duanju-guide/PUBLISH.md)。

## 在 Codex 中使用

本目录已初始化为本地 Git 仓库。若要让它出现在 Codex 侧边栏的“项目”中，请在 Codex 的 Projects 视图中新建**本地项目**，并把本目录添加为主文件夹。之后可把当前聊天移入该项目；新聊天会自动读取本目录的 `AGENTS.md`。参见 [OpenAI Docs：Projects and chats](https://learn.chatgpt.com/docs/projects)。

## 目录

- `sites/<站点代号>/`：每个网站单独存放源码、资源和说明。
- [`sites.csv`](sites.csv)：站点状态与正式网址登记表。
- [`SITE_BRIEF.md`](SITE_BRIEF.md)：新站需求模板。
- [`PLATFORMS.md`](PLATFORMS.md)：账号与发布渠道当前状态。
- [`AGENTS.md`](AGENTS.md)：后续在此目录工作的执行规范。

## 参考站

这些链接只用于了解站型，不复刻其内容和视觉：

- [jiaose.pages.dev](https://jiaose.pages.dev/)：分类网址导航。
- [huangguotv.pages.dev](https://huangguotv.pages.dev/)：多页面内容站。
- [91crdh.carrd.co](https://91crdh.carrd.co/)：单页链接聚合。

可按需求选择导航站、专题内容站、工具站、问答站等形式。每个站应有真实的独立内容和用途，避免换皮重复。
