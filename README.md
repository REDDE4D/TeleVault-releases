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

### v1.0.0-beta.2.2 (2026-03-28)

## New Features

- Add frontend build process to release workflow

**Full Changelog**: v1.0.0-beta.2.1...v1.0.0-beta.2.2

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-beta.2.1 (2026-03-27)

## New Features

- Add bulk function execution for running operations across multiple selected accounts
- Add support for executing multiple NordVPN proxies at once with progress indication
- Add SOCKS5 proxy support, allowing accounts to connect through assigned proxies

## Improvements

- Enhance the provider proxy dialog to display progress when adding multiple proxies

**Full Changelog**: v1.0.0-beta.2.0...v1.0.0-beta.2.1

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-beta.2.0 (2026-03-27)

## New Features

- Add PIN unlock feature with enable, disable, and unlock commands
- Add session management commands to retrieve and terminate active sessions
- Improve proxy testing to support authentication

## Improvements

- Enhance app status to include PIN-related states
- Refactor Telegram operations for better session handling and reporting
- Integrate PIN functionality with existing biometric unlock logic

## Internal

- Implement PIN validation, hashing, and encryption using PBKDF2
- Update database models to store PIN configurations

**Full Changelog**: v1.0.0-beta.1.1...v1.0.0-beta.2.0

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-beta.1.1 (2026-03-18)

## New Features

- Add error sanitization to prevent sensitive information leakage in user-facing error messages
- Add brute force protection to unlock functionality with attempt limits and progressive delays

## Improvements

- Improve security by restricting Content Security Policy for script and object sources
- Improve biometric cache directory permissions for enhanced security
- Optimize database performance by implementing message caching limits
- Update dependencies for better compatibility and security

## Internal

- Remove TDLib integration and all related console commands
- Remove TDLib references from build configuration

**Full Changelog**: v1.0.0-beta.1...v1.0.0-beta.1.1

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-beta.1 (2026-03-18)

## New Features

- Add account export functionality in CSV and JSON formats, excluding sensitive information
- Enhance proxy management with update and test commands to modify settings and verify connectivity
- Add 2FA status check for Telegram accounts
- Introduce message caching in the database to store and retrieve messages with metadata

## Improvements

- Update security policies for media handling with enhanced Content Security Policy and asset protocol support

**Full Changelog**: v1.0.0-alpha.15.1...v1.0.0-beta.1

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-alpha.15.1 (2026-03-16)

## New Features

- Add tagging functionality for accounts with support for creation, updating, deletion, and filtering
- Add tag assignment in bulk action bar and account management interface

**Full Changelog**: v1.0.0-alpha.15...v1.0.0-alpha.15.1

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-alpha.15 (2026-03-16)

## New Features

- Add console commands and raw client connection for Telegram, enabling direct interaction with Telegram's console interface

## Improvements

- Enhance authentication tracking to record when two-factor authentication is required during login

**Full Changelog**: v1.0.0-alpha.14...v1.0.0-alpha.15

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-alpha.14 (2026-03-16)

## New Features

- Add Telegram group and bot creation features with dedicated dialogs for creating groups (with type and description options) and managing bot creation via BotFather

## Internal

- Enhance TelegramManager with methods for creating groups and channels, and resolving bot usernames
- Update database schema to include new fields for account management
- Integrate AI-generated release notes using Claude API in the release workflow

**Full Changelog**: v1.0.0-alpha.13.3...v1.0.0-alpha.14

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-alpha.13.3 (2026-03-13)

## What's Changed

- chore: bump version to 1.0.0-alpha.13.3
- feat: add react-markdown for rendering changelog notes

**Full Changelog**: v1.0.0-alpha.13.2...v1.0.0-alpha.13.3

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-alpha.13.2 (2026-03-13)

## What's Changed

- chore: bump version to 1.0.0-alpha.13.2
- feat: implement custom API credentials management and obfuscation

**Full Changelog**: v1.0.0-alpha.13.1...v1.0.0-alpha.13.2

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.



---

Built with [Tauri v2](https://v2.tauri.app) + React + Rust
