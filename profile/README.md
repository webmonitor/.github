<p align="center">
  <img src="https://raw.githubusercontent.com/webmonitor/.github/main/image/logo.png" width="88" height="88" alt="WebMonitor" />
</p>

<h1 align="center">WebMonitor</h1>

<p align="center">Watch the pages you care about. Receive updates by email.</p>

<p align="center">
  <a href="https://webmonitor.github.io/en/">Website</a> ·
  <a href="https://webmonitor.github.io/en/docs/">User guide</a> ·
  <a href="https://webmonitor.qfpqhyl.top/">Live demo</a> ·
  <a href="https://github.com/webmonitor/.github/blob/main/profile/README.zh-CN.md">简体中文</a>
</p>

Has a price dropped? Is there a new announcement? Has a deadline moved? Give WebMonitor the pages you keep checking, choose how often to check, and receive an email when a change meets your conditions.

## Choose how to monitor

| What you need | Recommended product | How to begin |
| --- | --- | --- |
| Describe a request such as “check every ten minutes and email me when the price falls below 200” | [WebMonitor-Agent](https://github.com/webmonitor/WebMonitor-Agent) | Paste a URL, describe your conditions, review the collected preview and confirm creation; requires a model service |
| Watch text changes in a page region you already know | [WebMonitor](https://github.com/webmonitor/WebMonitor) | Enter a URL, XPath and check interval; no model service needed |

Agent supports price thresholds, keywords and new list entries, with before/after content and saved pages to help you review changes. WebMonitor lets you share tasks with other users of your instance, who can subscribe using their own email settings.

## Start using WebMonitor

**Already have an address from your administrator?** Open it in your browser and sign in. New Agent members register using an invitation link from the administrator.

**Want your own instance?** Prepare Docker and follow the installation guide below: download the listed files, create `.env` from the template, fill in your settings and start.

- [Install Agent](https://github.com/webmonitor/WebMonitor-Agent#readme): prepare your model service URL, key and model name. Add mail service settings if you want email alerts.
- [Install WebMonitor](https://github.com/webmonitor/WebMonitor#readme): choose administrator credentials and a signing key, then add an email account in the app after starting.

Both products use the same command from their own installation directory:

```sh
docker compose up -d --wait
```

Open `http://localhost:8080` for Agent or `http://localhost:8000` for WebMonitor. Before enabling your first monitor, preview the extracted content and make sure it matches the part you want to follow.

**Planning long-term use?** Read the installation guide’s data-retention instructions first. Agent’s default temporary data is cleared when its data services stop or restart; WebMonitor’s default data is lost when its application container is replaced. Arrange persistent storage and backups before saving important tasks.

You can also explore the [WebMonitor live demo](https://webmonitor.qfpqhyl.top/) to see tasks, email settings and logs. The demo may be unavailable at times.

## Get help

[Read the complete user guide](https://webmonitor.github.io/en/docs/) · [Report an Agent issue](https://github.com/webmonitor/WebMonitor-Agent/issues) · [Report a WebMonitor issue](https://github.com/webmonitor/WebMonitor/issues)

Include what you wanted to monitor, the step that failed and the message shown in the app. Share example pages and screenshots with credentials and personal information removed.

Both [WebMonitor-Agent](https://github.com/webmonitor/WebMonitor-Agent/blob/main/LICENSE) and [WebMonitor](https://github.com/webmonitor/WebMonitor/blob/main/LICENSE) use **CC BY-NC 4.0**: share and adapt for non-commercial use with attribution, a license link and an indication of changes.
