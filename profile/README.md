<p align="center">
  <img src="https://raw.githubusercontent.com/webmonitor/.github/main/image/logo.png" width="88" height="88" alt="WebMonitor" />
</p>

<h1 align="center">WebMonitor</h1>

<p align="center">
  Watch page changes and receive email alerts.<br />
  Self-hosted · Docker images · English and Chinese
</p>

<p align="center">
  <a href="https://webmonitor.github.io/en/">Website</a> ·
  <a href="https://webmonitor.github.io/en/docs/">Documentation</a> ·
  <a href="https://webmonitor.qfpqhyl.top/">Live demo</a> ·
  <a href="https://github.com/webmonitor/.github/blob/main/profile/README.zh-CN.md">简体中文</a>
</p>

## Choose a project

| Project | Monitoring setup | Deployment | License |
| --- | --- | --- | --- |
| [WebMonitor-Agent](https://github.com/webmonitor/WebMonitor-Agent) | Describe a page and notification conditions; review a real collection preview before confirming | One application image shared by API/worker and frontend services, plus supporting services | MIT |
| [WebMonitor](https://github.com/webmonitor/WebMonitor) | Enter a URL, XPath and check interval; share tasks and subscribe within your instance | One container serves the UI and API | CC BY-NC 4.0 |

WebMonitor-Agent is the actively developed product. It supports HTTP and browser collection, text and numeric rules, list changes, page evidence and email delivery records. WebMonitor is the original dashboard, maintained for fixes, and requires no model service.

## Public Docker images

Both images are public on GitHub Container Registry. Anyone can pull them without a GitHub account or `docker login`. Docker selects `linux/amd64` or `linux/arm64` for your machine.

```sh
docker pull ghcr.io/webmonitor/webmonitor-agent:1.0.0
docker pull ghcr.io/webmonitor/webmonitor:1.0.0
```

Pulling only downloads the application. Deployment requires no repository clone: create an empty directory, download the deployment files listed in the project guide, and create your own `.env` from its inline template.

- [Agent: install, configure and run](https://github.com/webmonitor/WebMonitor-Agent#readme) — model credentials, administrator credentials, PostgreSQL, S3-compatible storage and optional SMTP.
- [WebMonitor: install, configure and run](https://github.com/webmonitor/WebMonitor#readme) — administrator credentials and signing key; configure email in the app.

After downloading the required files and filling in your `.env`, both projects start with the same command from their own deployment directory:

```sh
docker compose up -d --wait
```

`compose.yaml` pulls `latest` by default. Set `WEBMONITOR_IMAGE` in `.env` to a version such as `1.0.0` for repeatable deployments. `latest` follows stable releases; `main` is a development build when available. See [Agent releases](https://github.com/webmonitor/WebMonitor-Agent/releases) and [WebMonitor releases](https://github.com/webmonitor/WebMonitor/releases) separately. Agent’s S3 and egress helper images still build locally from the downloaded deployment files. Developers use `compose.build.yaml` for source builds.

The supplied deployments need storage changes and backups for long-term use: Agent data services use temporary storage, and WebMonitor stores SQLite inside its container without a data volume. Read the project’s retention notes before restarting data services or replacing containers. The live demo is a separate WebMonitor instance and may be unavailable.

## Development and feedback

[Website source](https://github.com/webmonitor/webmonitor.github.io) contains the bilingual homepage and documentation. [mocksite](https://github.com/webmonitor/mocksite) provides a controllable notice page for collector development; it builds from source and has separate site and administration ports.

Report issues in the relevant project with reproduction steps and a page example with sensitive data removed. Never include API keys, SMTP passwords, session cookies or real `.env` files.

[Agent issues](https://github.com/webmonitor/WebMonitor-Agent/issues) · [WebMonitor issues](https://github.com/webmonitor/WebMonitor/issues)
