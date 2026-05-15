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

### v1.0.0-beta.5.0 (2026-05-15)

## New Features

- Add email management UI: recovery and login email cards now display in the Security tab with setup and removal flows
- Add EmailSetupDialog for the first step of email configuration, featuring a picker to reuse addresses from other accounts or enter new ones, plus optional 2FA password gating for recovery email
- Add EmailCodeDialog for the second step of email confirmation, supporting code entry and resend
- Add LoginEmailCard to manage login email without 2FA dependency (removal intentionally not exposed)
- Add RecoveryEmailCard to manage recovery email with password-gated removal and status display
- Register email management backend commands and expose frontend wrappers for recovery and login email flows
- Add recovery email set/confirm/resend/remove console commands with SRP-based password verification
- Add login email set/verify/resend console commands; removal intentionally not exposed per design
- Add email module to read and display email status, including masking for security
- Add email status types and extend Account model to track recovery and login email addresses
- Extend database with recovery_email and login_email columns and list_used_emails query to prevent duplicate assignments across accounts

## Improvements

- Update email verification to use the correct EmailVerifyPurpose for each flow: LoginChange for managing login email in authenticated sessions, LoginSetup only for initial phone-login setup

## Bug Fixes

- Fix database field order in TestDb to ensure SQLite connection closes before temp directory removal (Windows compatibility)
- Remove unused parameter from LoginEmailCard callback to resolve linting warnings

**Full Changelog**: v1.0.0-beta.4.4...v1.0.0-beta.5.0

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-beta.4.4 (2026-05-05)

## Bug Fixes

- Fix encrypted descriptor size calculation to include the 4-byte prefix itself, resolving compatibility issues with TDesktop's TData format

**Full Changelog**: v1.0.0-beta.4.3...v1.0.0-beta.4.4

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-beta.4.3 (2026-05-05)

## Bug Fixes

- Fix tdata export to write directly into the chosen output directory instead of nesting files in an extra `tdata/` subfolder, resolving import failures when uploading to other tools

## Internal

- Revert app URLs back to GitHub while maintaining Codeberg bridge script for users on v1.0.0-beta.4.2

**Full Changelog**: v1.0.0-beta.4.2...v1.0.0-beta.4.3

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-beta.4.2 (2026-05-05)

## Bug Fixes

- Fix tdata export to allow saving to user-created paths (previously failed when exporting to a new directory)
- Update repository links to Codeberg

**Full Changelog**: v1.0.0-beta.4.1...v1.0.0-beta.4.2

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-beta.4.1 (2026-05-05)

## New Features

- Add tdata generation from session when no import blob exists, preserving byte-exact round-trips for previously imported accounts
- Add TdataWriter to generate full Telegram Desktop tdata directory trees, including key_datas, per-account mtp files, maps, and configs from session data
- Add EncryptedDescriptor primitive for encrypting/decrypting tdata files using AES-IGE with SHA1-derived per-blob keys
- Add TDF file framing with MD5 trailer support
- Add Qt QDataStream writer for big-endian numerics and length-prefixed byte arrays
- Add PBKDF2-HMAC-SHA512 local-key derivation
- Add AES-IGE-256 encryption (verified against opentele test vectors)

## Internal

- Refactor tdata module into a directory structure with separate reader and writer components
- Document tdata format constants and file layouts with binary test fixtures for deterministic verification

**Full Changelog**: v1.0.0-beta.4.0...v1.0.0-beta.4.1

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-beta.4.0 (2026-05-01)

## New Features

- Add "Delete on Telegram" button with confirmation dialog to account panel; relabel local delete to "Delete Account (local only)" for clarity
- Add support for deleting accounts directly on Telegram via MTProto (2FA-protected)
- Add SRP-6a authentication helper for 2FA-gated RPC calls
- Add `PasswordRequired` error variant to signal when 2FA password is needed
- Add DELETED account status throughout the UI (status badge, edit dialog, accounts page filter)
- Add DELETED account status to the database schema with validation
- Split session string export into Telethon and Pyrogram formats
- Implement real Telethon and Pyrogram session string generation (replacing stub)
- Add session export module with helpers to extract connection details (datacenter, IP, port, auth key) from stored session bytes
- Add encoders to serialize session parts into Telethon StringSession and Pyrogram v3 string formats

## Improvements

- Broaden connection retry logic to handle all transient errors (not just proxy-auth failures); add exponential backoff (2s, 4s) and retry on timeouts for both `TelegramManager::connect` and raw client connections

## Bug Fixes

- Fix session string export to decode stored session bytes and extract real connection parameters instead of returning stubs
- Remove dead DELETED case in UI stat counter

**Full Changelog**: v1.0.0-beta.3.1...v1.0.0-beta.4.0

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-beta.3.1 (2026-03-28)

# Changelog

## Bug Fixes

- Fix media URL test file by removing unused imports

**Full Changelog**: v1.0.0-beta.3.0...v1.0.0-beta.3.1

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-beta.2.5 (2026-03-28)

## New Features

- Add new SQL commands for managing proxies in the database

## Improvements

- Enhance database schema to support improved data organization and management

**Full Changelog**: v1.0.0-beta.2.4...v1.0.0-beta.2.5

---

### Install

Download the file for your platform from the assets below.

**macOS:** After installing, you may see *"TeleVault is damaged and can't be opened."* This is because the app is not signed with an Apple Developer certificate. To fix it, run:

```bash
xattr -cr /Applications/TeleVault.app
```

Then open the app normally.


---

### v1.0.0-beta.2.4 (2026-03-28)

## Bug Fixes

- Fix unused imports in DeveloperTab component

**Full Changelog**: v1.0.0-beta.2.3...v1.0.0-beta.2.4

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
