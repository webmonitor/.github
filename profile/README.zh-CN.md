<p align="center">
  <img src="https://raw.githubusercontent.com/webmonitor/.github/main/image/logo.png" width="88" height="88" alt="WebMonitor" />
</p>

<h1 align="center">WebMonitor</h1>

<p align="center">
  <strong>关注变化，不必反复刷新。</strong><br />
  网页内容监控 · 邮件通知 · 自托管
</p>

<p align="center">
  <a href="https://webmonitor.qfpqhyl.top/">在线体验</a> ·
  <a href="https://github.com/webmonitor/WebMonitor/blob/main/README.zh-CN.md">中文文档</a> ·
  <a href="https://github.com/webmonitor/.github/blob/main/profile/README.md">English</a>
</p>

---

公告更新、商品调价、页面内容变动——把你关心的网页交给 WebMonitor，在检测到变化时收到邮件提醒。

## 选择你的监控方式

### [WebMonitor](https://github.com/webmonitor/WebMonitor)

**通过可视化面板，管理日常监控。**

用 XPath 指定要关注的页面区域，定时检查内容变化。支持邮件通知、公开任务与用户订阅，提供任务和日志管理、中英文界面及 Docker 部署。

[部署与使用 →](https://github.com/webmonitor/WebMonitor/blob/main/README.zh-CN.md)

### [WebMonitor-Agent](https://github.com/webmonitor/WebMonitor-Agent)

**用对话描述需求，确认后开始监控。**

从真实页面分析到配置草稿、内容提取与邮件预览，逐步确认监控内容。支持静态页面与浏览器渲染页面，保留变化事件、运行记录和采集证据。API/后台进程与前端打包在同一个镜像里。

[了解 Agent →](https://github.com/webmonitor/WebMonitor-Agent#readme)

> Agent 当前面向本地开发与验证；部署方式与数据保留限制请先阅读项目说明。

## 运行 WebMonitor

两个项目在每次发布时都会把多架构镜像（`linux/amd64` 与 `linux/arm64`）推送到 GitHub Container Registry。克隆仓库取得 Compose 文件与配置，再让 Compose 使用发布镜像：

```sh
# WebMonitor-Agent —— 一个镜像，两个服务（api + web）
echo "WEBMONITOR_IMAGE=ghcr.io/webmonitor/webmonitor-agent:0.1.0" >> .env
docker compose -f compose.yaml -f compose.ghcr.yaml up -d --wait
```

```sh
# WebMonitor
echo "WEBMONITOR_IMAGE=ghcr.io/webmonitor/webmonitor:1.0.0" >> .env
docker compose -f docker-compose.yml -f docker-compose.ghcr.yml up -d --wait
```

版本号换成[最新发布](https://github.com/webmonitor/WebMonitor-Agent/releases)。匿名拉取要求包已设为公开，否则先执行 `docker login ghcr.io`。直接 `docker compose up` 仍从源码构建。

## 一起完善 WebMonitor

欢迎分享监控场景、反馈问题，或通过 Pull Request 改进代码与文档。提交问题时，请附上复现步骤与脱敏后的页面示例。

[反馈 WebMonitor 问题](https://github.com/webmonitor/WebMonitor/issues) · [反馈 Agent 问题](https://github.com/webmonitor/WebMonitor-Agent/issues)
