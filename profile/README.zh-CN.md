<p align="center">
  <img src="https://raw.githubusercontent.com/webmonitor/.github/main/image/logo.png" width="88" height="88" alt="WebMonitor" />
</p>

<h1 align="center">WebMonitor</h1>

<p align="center">
  监控网页变化，通过邮件接收提醒。<br />
  自行部署 · Docker 镜像 · 中英文界面
</p>

<p align="center">
  <a href="https://webmonitor.github.io/">官网</a> ·
  <a href="https://webmonitor.github.io/docs/">使用文档</a> ·
  <a href="https://webmonitor.qfpqhyl.top/">在线体验</a> ·
  <a href="https://github.com/webmonitor/.github/blob/main/profile/README.md">English</a>
</p>

## 选择项目

| 项目 | 创建监控 | 部署方式 | 许可证 |
| --- | --- | --- | --- |
| [WebMonitor-Agent](https://github.com/webmonitor/WebMonitor-Agent) | 用对话描述网页与通知条件，核对真实采集预览后确认 | API/后台与前端两个服务共用一个应用镜像，另有配套服务 | MIT |
| [WebMonitor](https://github.com/webmonitor/WebMonitor) | 填写网址、XPath 与检查间隔，可在实例内分享任务与订阅 | 一个容器同时提供界面与 API | CC BY-NC 4.0 |

WebMonitor-Agent 是当前持续开发的产品，支持 HTTP 与浏览器采集、文本与数值规则、列表变化、页面证据与邮件投递记录。WebMonitor 是原版可视化工作台，以维护和问题修复为主，不需要模型服务。

## 公开 Docker 镜像

两个应用镜像均已在 GitHub Container Registry 公开。任何人都可直接拉取，无需 GitHub 账户，也无需 `docker login`。Docker 会自动选择适合本机的 `linux/amd64` 或 `linux/arm64` 镜像。

```sh
docker pull ghcr.io/webmonitor/webmonitor-agent:1.0.0
docker pull ghcr.io/webmonitor/webmonitor:1.0.0
```

拉取只负责下载应用。部署无需克隆仓库：创建空目录，下载指南列出的部署文件，再按文档中的模板自行创建 `.env`。

- [Agent：安装、配置与启动](https://github.com/webmonitor/WebMonitor-Agent/blob/main/README.zh-CN.md) —— 配置模型服务、管理员、PostgreSQL、S3 兼容存储；邮件提醒另需 SMTP。
- [WebMonitor：安装、配置与启动](https://github.com/webmonitor/WebMonitor/blob/main/README.zh-CN.md) —— 配置管理员与签名密钥，邮件账户在应用内设置。

下载所需文件、填写自己的 `.env` 后，两个项目都在各自部署目录执行同一条启动命令：

```sh
docker compose up -d --wait
```

`compose.yaml` 默认拉取 `latest`。在 `.env` 中设置 `WEBMONITOR_IMAGE` 可固定到 `1.0.0` 等版本。`latest` 跟随稳定发布，`main` 在可用时代表开发分支构建。两个项目分别维护 [Agent 发布记录](https://github.com/webmonitor/WebMonitor-Agent/releases)与 [WebMonitor 发布记录](https://github.com/webmonitor/WebMonitor/releases)。Agent 的 S3 与出口代理辅助镜像仍用下载的部署文件在本地构建。开发者从源码构建时额外加载 `compose.build.yaml`。

长期使用前需配置持久存储与备份：Agent 随附数据服务使用临时存储，WebMonitor 默认把 SQLite 放在容器内，未挂载数据卷。重启数据服务或替换容器前，先阅读对应项目的数据保留说明。在线演示是单独运行的 WebMonitor 实例，可能暂时不可用。

## 开发与反馈

[官网仓库](https://github.com/webmonitor/webmonitor.github.io)维护中英文首页和使用文档。[mocksite](https://github.com/webmonitor/mocksite)提供可控的通知详情页，用于采集器开发；它从源码构建，页面端口与管理端口分离。

请向对应项目提交问题，附上复现步骤与脱敏后的页面示例。不要提交 API 密钥、SMTP 密码、会话 Cookie 或真实 `.env` 文件。

[Agent 问题反馈](https://github.com/webmonitor/WebMonitor-Agent/issues) · [WebMonitor 问题反馈](https://github.com/webmonitor/WebMonitor/issues)
