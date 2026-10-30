<p align="center">
  <img src="https://raw.githubusercontent.com/webmonitor/.github/main/image/logo.png" width="88" height="88" alt="WebMonitor" />
</p>

<h1 align="center">WebMonitor</h1>

<p align="center">
  <strong>Follow changes. Skip the refresh.</strong><br />
  Web content monitoring · Email alerts · Self-hosted
</p>

<p align="center">
  <a href="https://webmonitor.qfpqhyl.top/">Live demo</a> ·
  <a href="https://github.com/webmonitor/WebMonitor#readme">Documentation</a> ·
  <a href="https://github.com/webmonitor/.github/blob/main/profile/README.zh-CN.md">简体中文</a>
</p>

---

Announcements, price changes, and page updates—let WebMonitor watch the pages you care about and notify you by email when it detects a change.

## Choose how you monitor

### [WebMonitor](https://github.com/webmonitor/WebMonitor)

**Manage everyday monitoring from a visual dashboard.**

Target a specific page region with XPath and check it on a schedule. Includes email alerts, public tasks and subscriptions, task and log management, a bilingual interface, and Docker deployment.

[Deployment and usage →](https://github.com/webmonitor/WebMonitor#readme)

### [WebMonitor-Agent](https://github.com/webmonitor/WebMonitor-Agent)

**Describe what matters. Preview it. Confirm and monitor.**

Create monitors through conversation, from real page analysis to configuration drafts, content extraction, and email previews. Supports static and browser-rendered pages, with change events, run history, and collected evidence. Ships as a single image for both the API/worker and the frontend.

[Explore the Agent →](https://github.com/webmonitor/WebMonitor-Agent#readme)

> The Agent currently targets local development and evaluation. Read its project documentation for deployment requirements and data retention limitations.

## Run it

Both projects publish multi-architecture images (`linux/amd64` and `linux/arm64`) to GitHub Container Registry on every release. Clone the repository for its Compose file and configuration, then point Compose at the released image:

```sh
# WebMonitor-Agent — one image, two services (api + web)
echo "WEBMONITOR_IMAGE=ghcr.io/webmonitor/webmonitor-agent:1.0.0" >> .env
docker compose -f compose.yaml -f compose.ghcr.yaml up -d --wait
```

```sh
# WebMonitor
echo "WEBMONITOR_IMAGE=ghcr.io/webmonitor/webmonitor:1.0.0" >> .env
docker compose -f docker-compose.yml -f docker-compose.ghcr.yml up -d --wait
```

Replace the version with the [latest release](https://github.com/webmonitor/WebMonitor-Agent/releases). Pulling anonymously requires the package to be public; otherwise `docker login ghcr.io` first. Plain `docker compose up` still builds from source.

## Build with us

Share a monitoring use case, report an issue, or contribute code and documentation through a pull request. For bug reports, include reproduction steps and a page example with sensitive information removed.

[WebMonitor issues](https://github.com/webmonitor/WebMonitor/issues) · [Agent issues](https://github.com/webmonitor/WebMonitor-Agent/issues)
