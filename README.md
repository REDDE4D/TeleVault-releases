# TeleVault

**Secure Telegram Account Manager** — A cross-platform desktop app for managing multiple Telegram accounts with military-grade encryption.

[![Latest Release](https://img.shields.io/github/v/release/REDDE4D/TeleVault-releases?style=flat-square)](https://github.com/REDDE4D/TeleVault-releases/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/REDDE4D/TeleVault-releases/total?style=flat-square)](https://github.com/REDDE4D/TeleVault-releases/releases)

## Features

- **Multi-Account Management** — Add, organize, and monitor multiple Telegram accounts
- **AES-256-GCM Encryption** — Sessions and sensitive data encrypted at rest
- **Health Checking** — Verify account status and connectivity
- **Code Extraction** — Extract login codes from Telegram service messages
- **Spam Status Check** — Check if accounts are restricted via @SpamBot
- **Groups & Tags** — Organize accounts with custom groups
- **Proxy Support** — SOCKS5/HTTP proxy per account
- **Import/Export** — CSV, database, and encrypted backup support
- **Cross-Platform** — Windows, macOS (Intel & Apple Silicon), Linux
- **Auto-Updates** — Built-in update checker

## Download

Download the latest version for your platform from the [Releases page](https://github.com/REDDE4D/TeleVault-releases/releases/latest).

| Platform | File |
|----------|------|
| Windows | `.msi` or `.exe` |
| macOS (Apple Silicon) | `.dmg` (aarch64) |
| macOS (Intel) | `.dmg` (x86_64) |
| Linux | `.deb` or `.AppImage` |

### macOS — "app is damaged" warning

Since the app is not signed with an Apple Developer certificate, macOS will block it. After installing, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.

## Changelog

### v1.0.0-alpha.3 (2026-03-12)

## What's Changed

- Update release notes and improve deployment script; change latest.json URL to raw GitHub content

**Full Changelog**: v1.0.0-alpha.2...v1.0.0-alpha.3

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-alpha.2 (2026-03-12)

## What's Changed

- Update ci,tooling

**Full Changelog**: v1.0.0-alpha.1...v1.0.0-alpha.2


---

### v1.0.0-alpha.1 (2026-03-12)

## What's Changed

- Update ci
- Update release.yml
- Update release.yml
- Add changelog UI, backend and release automation
- Enable vendored OpenSSL for Telegram deps
- Enable rustls, update deps & build workflow
- Update release workflow and Tauri build commands
- Set projectPath and fix Tauri frontend paths
- Update release.yml

**Full Changelog**: v1.0.0...v1.0.0-alpha.1



---

Built with [Tauri v2](https://v2.tauri.app) + React + Rust
