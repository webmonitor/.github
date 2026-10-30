<p align="center">
  <img src="https://raw.githubusercontent.com/webmonitor/.github/main/image/logo.png" width="88" height="88" alt="WebMonitor" />
</p>

<h1 align="center">WebMonitor</h1>

<p align="center">关注网页变化，让更新送到邮箱。</p>

<p align="center">
  <a href="https://webmonitor.github.io/">官网</a> ·
  <a href="https://webmonitor.github.io/docs/">使用指南</a> ·
  <a href="https://webmonitor.qfpqhyl.top/">在线体验</a> ·
  <a href="https://github.com/webmonitor/.github/blob/main/profile/README.md">English</a>
</p>

商品有没有降价？学校有没有发新公告？报名日期有没有调整？把需要反复查看的页面交给 WebMonitor，按你设置的频率检查，有符合条件的变化时通过邮件提醒。

## 选一种适合你的方式

| 你的需求 | 推荐产品 | 如何开始 |
| --- | --- | --- |
| 想用一句话说明需求，例如“每十分钟看一次，价格低于 200 元时通知我” | [WebMonitor-Agent](https://github.com/webmonitor/WebMonitor-Agent) | 粘贴网址，描述条件，核对采集预览后确认创建；需要模型服务 |
| 已经知道要看页面的哪块内容，只要文字变了就通知 | [WebMonitor](https://github.com/webmonitor/WebMonitor) | 填写网址、XPath 和检查间隔；不需要模型服务 |

Agent 支持价格阈值、关键词和列表新增等通知条件，还能查看变化前后的内容与页面存档。WebMonitor 支持把任务分享给同一实例的其他用户，让他们用自己的邮箱订阅更新。

## 开始使用

**管理员已经提供了访问地址？** 直接在浏览器打开并登录。Agent 的新成员需要管理员发放邀请链接，无需在自己电脑上安装。

**想自己部署？** 准备好 Docker，选择下面的安装指南。无需克隆仓库，也无需登录镜像仓库：下载所需文件，按模板创建自己的 `.env`，填好配置后启动。

- [安装 Agent](https://github.com/webmonitor/WebMonitor-Agent/blob/main/README.zh-CN.md)：准备模型服务的地址、密钥和模型名称；需要邮件时再填写邮箱服务配置。
- [安装 WebMonitor](https://github.com/webmonitor/WebMonitor/blob/main/README.zh-CN.md)：设置管理员账户和密钥，启动后在界面里添加邮件账户。

两个产品在各自安装目录中使用同一条启动命令：

```sh
docker compose up -d --wait
```

安装后，Agent 打开 `http://localhost:8080`，WebMonitor 打开 `http://localhost:8000`。第一次使用时，先预览提取内容，确认抓到的是你要关注的部分，再启用监控。

**准备长期使用？** 先阅读安装指南里的数据保留说明。Agent 默认临时数据会在数据服务停止或重启后清空；WebMonitor 默认数据会在替换应用容器后丢失。请先安排持久存储与备份，再保存重要任务。

也可以先访问 [WebMonitor 在线演示](https://webmonitor.qfpqhyl.top/)，了解任务、邮件配置与日志页面；演示可能暂时不可用。

## 获取帮助

[阅读完整使用指南](https://webmonitor.github.io/docs/) · [反馈 Agent 问题](https://github.com/webmonitor/WebMonitor-Agent/issues) · [反馈 WebMonitor 问题](https://github.com/webmonitor/WebMonitor/issues)

反馈时请说明想监控什么、在哪一步遇到问题，以及界面中的提示。网页示例与截图请先脱敏，不要附带密码、API 密钥或真实 `.env` 文件。

[WebMonitor-Agent](https://github.com/webmonitor/WebMonitor-Agent/blob/main/LICENSE) 与 [WebMonitor](https://github.com/webmonitor/WebMonitor/blob/main/LICENSE) 均采用 **CC BY-NC 4.0**：署名、附上许可链接并注明修改后，可分享与修改，仅限非商业用途。
