<p align="center">
  <a href="https://github.com/ogmabox/ogma">
    <img width="1916" height="821" alt="Ogma banner" src="https://github.com/user-attachments/assets/f7f6def5-3b4b-4bc7-8c67-5b7eca09cdf4" />
  </a>
</p>

<div align="center">

# Ogma

### A lightweight local proxy for web security testing.

<br/>

[![License: Proprietary](https://img.shields.io/badge/License-Proprietary-e8a44a?style=for-the-badge)](LICENSE)
[![GitHub Releases](https://img.shields.io/github/v/release/ogmabox/ogma?style=for-the-badge&color=e8a44a)](https://github.com/ogmabox/ogma/releases/latest)
[![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Windows%20%7C%20Linux-555555?style=for-the-badge)]()

<br/>

<a href="https://discord.gg/QNSadmjh6y"><img src="https://img.shields.io/badge/Discord-Join%20Community-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Discord"></a>
<a href="https://x.com/kaijinlab"><img src="https://img.shields.io/badge/Follow-%40kaijinlab-000000?style=for-the-badge&logo=x&logoColor=white" alt="X / Twitter"></a>

</div>

---

Intercept, replay, scan, automate, and extend HTTP workflows from one lightweight desktop app.

No account. No subscription. No cloud. Everything runs on your machine and your traffic stays there too.

<br/>

<div align="center">
  <a href="https://github.com/ogmabox/ogma/releases/latest">
    <img width="1920" height="1017" alt="Ogma HTTP History" src="https://github.com/user-attachments/assets/5522a915-64a8-4958-a7cb-dce2bc113dbd" style="border-radius: 12px;" />
  </a>
</div>

<br/>

## Download

**[Get the latest release](https://github.com/ogmabox/ogma/releases/latest)**

Source and CI builds live in the private `ogmabox/ogma-app` repository. Public
downloads, issues, and desktop update checks use `ogmabox/ogma`.

For a manual release, download every platform's assets from the private draft
release into one directory named `release-assets`, then run
`node scripts/prepare-updater-metadata.cjs release-assets` and
`node scripts/verify-updater-metadata.cjs release-assets`.
Upload all files in that directory to the same version tag in `ogmabox/ogma`,
including the generated `latest*.yml` files, ZIPs, installers, and blockmaps.
Publish only after all platforms are present. The public repository must be public
for users to download releases and check for updates without GitHub credentials.

| Platform | Package |
|----------|---------|
| macOS (Apple Silicon + Intel) | `.dmg` |
| Linux x64 / ARM64 | `.AppImage` or `.deb` |
| Windows x64 / ARM64 | `.exe` installer |

No setup required beyond installing the app. Start the proxy, import the CA certificate for HTTPS, and you are capturing traffic.

---

## What Ogma does

**Capture and inspect**
Every HTTP, HTTPS, WebSocket, and HTTP/2 request flows through Ogma's proxy. Filter, search, and tag traffic with HTTPQL - a purpose-built query language for HTTP history.

**Intercept and modify**
Pause any request before it leaves, edit it, then forward or drop it. Build Match & Replace rules to automatically rewrite headers, bodies, or paths in transit.

**Replay and fuzz**
Open any request in Replay and modify it freely. Scale up with Automate - Sniper, Pitchfork, and Cluster Bomb attack modes with payload extractors, matchers, and stop conditions. No rate limiting.

**Scan for vulnerabilities**
The passive scanner analyzes captured traffic continuously. The active scanner sends targeted payloads and only creates findings when the response contains evidence - SQL injection, XSS, SSRF, command injection, SSTI, path traversal, and open redirect.

**Discover attack surface**
Content discovery probes a target with a built-in 9,300-path wordlist, technology presets for WordPress, PHP, Java, .NET, and Node.js, and a live results table. Every discovered path feeds directly into HTTP History and Sitemap.

**Track and report**
The Findings panel links vulnerability evidence directly to the HTTP entries that prove it. Export reports as Markdown, JSON, or CSV. Import project archives to resume a session on any machine.

**Extend and automate**
Write plugins in JavaScript. Connect any AI assistant through the MCP server - 125+ tools covering history, findings, replay, workflows, and browser automation. Run headless pentests from the CLI: `ogma pentest <url>`.

---

## Use cases

- **Manual penetration testing** - intercept, analyze, and attack web applications with full control over every request
- **Bug bounty** - triage targets fast with HTTPQL filters, scope presets, and AI-assisted analysis
- **Security code review** - proxy your own app during development to catch issues before they ship
- **CTF challenges** - decode, replay, fuzz, and automate without switching between a dozen tools

---

## Quick start

1. [Download](https://github.com/ogmabox/ogma/releases/latest) the installer for your platform
2. Open Ogma and start the local instance
3. Configure your browser proxy to `127.0.0.1:8080` - or use the built-in browser
4. For HTTPS: import the Ogma CA certificate from **Settings > TLS**
5. Browse your target - traffic appears in **HTTP History**

### Headless mode

```bash
# Run an automated pentest and get a Markdown report
ogma pentest https://target.example.com

# Specify minimum severity and output file
ogma pentest https://target.example.com --min-severity high --output report.md
```

---

## Built with

Rust backend - Vue frontend - Electron desktop - SQLite storage

No performance compromise: the backend is a compiled Rust binary. The frontend is a pre-built static bundle. Startup is under 200ms.

---

## Contributing

Ogma is currently in **public beta**. We are not accepting code contributions yet - the architecture and internal APIs are still being finalized.

**What we accept right now:**

- [Bug reports](https://github.com/ogmabox/ogma/issues/new?template=bug_report.md)
- [Feature requests](https://github.com/ogmabox/ogma/issues/new?template=feature_request.md)
- Feedback and discussion in [Discord](https://discord.gg/QNSadmjh6y)

Code contributions will open with the v1.0 release.

---

## Community

**[Discord](https://discord.gg/QNSadmjh6y)** - bug reports, feedback, and general discussion

**[X / Twitter](https://x.com/kaijinlab)** - releases and updates

---

## License

Ogma is licensed under the [GNU Affero General Public License v3.0](LICENSE).
