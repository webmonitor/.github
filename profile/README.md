<p align="center">
  <img src="https://raw.githubusercontent.com/webmonitor/.github/main/image/logo.png" width="96" height="96" alt="WebMonitor logo">
</p>

<h1 align="center">WebMonitor</h1>

<p align="center">
  <strong>Monitor the pages that matter. Get email alerts when content changes.</strong><br>
  Self-hosted web monitoring with scheduled checks and conversational setup.
</p>

<p align="center">
  <a href="https://webmonitor.github.io/en/">Website</a> ·
  <a href="https://webmonitor.github.io/en/docs/">Documentation</a> ·
  <a href="https://webmonitor.qfpqhyl.top/">Live demo</a> ·
  <a href="https://github.com/webmonitor/.github/blob/main/profile/README.zh-CN.md">简体中文</a>
</p>

WebMonitor helps you track prices, announcements, deadlines, and other web content without repeatedly checking pages yourself. Choose a conversational monitor for natural-language conditions, or a page-region monitor that needs no model service.

## Choose your monitor

| Product | Best for | How to begin | Requirements |
| --- | --- | --- | --- |
| [WebMonitor-Agent](https://github.com/webmonitor/WebMonitor-Agent) | Price thresholds, keywords, new list entries, and custom conditions | Paste a URL, describe what to watch and when to receive an alert, review the preview, then confirm | Model service; mail service for email alerts |
| [WebMonitor](https://github.com/webmonitor/WebMonitor) | Text changes in a page region you already know | Enter a URL, XPath, and check interval | No model service; email account configured in the app |

Agent saves pages and before/after content to help you review each change. WebMonitor lets you share tasks with other users of your instance, who can subscribe with their own email settings.

## Get started

**Using an existing instance?** Open the address provided by your administrator and sign in. New Agent members need an invitation link from the administrator.

**Self-hosting with Docker:**

1. Choose [Agent installation](https://github.com/webmonitor/WebMonitor-Agent#readme) or [WebMonitor installation](https://github.com/webmonitor/WebMonitor#readme), then follow the guide to download the deployment files and prepare `.env`.
2. Start the selected product from its installation directory:

   ```sh
   docker compose up -d --wait
   ```

3. Open [http://localhost:8080](http://localhost:8080) for Agent or [http://localhost:8000](http://localhost:8000) for WebMonitor.
4. Before enabling a monitor, preview the extracted content and confirm that it matches the page region you want to watch.

> **Data retention:** Agent’s default temporary data is cleared when its data services stop or restart. WebMonitor’s default data is lost when its application container is replaced. Follow the installation guide to configure persistent storage and backups before saving important tasks.

You can also explore the [live demo](https://webmonitor.qfpqhyl.top/) to see tasks, email settings, and logs. Demo availability may vary.

## Documentation and support

- [Read the complete user guide](https://webmonitor.github.io/en/docs/)
- [Report an Agent issue](https://github.com/webmonitor/WebMonitor-Agent/issues)
- [Report a WebMonitor issue](https://github.com/webmonitor/WebMonitor/issues)

When reporting a problem, include the page you wanted to monitor, the step that failed, and the message shown in the app. Example pages and screenshots are helpful; remove credentials and personal information first.

## License

Both [WebMonitor-Agent](https://github.com/webmonitor/WebMonitor-Agent/blob/main/LICENSE) and [WebMonitor](https://github.com/webmonitor/WebMonitor/blob/main/LICENSE) use **CC BY-NC 4.0**. You may share and adapt them for non-commercial use with attribution, a license link, and an indication of changes.
