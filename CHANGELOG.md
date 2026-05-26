# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html) for installer/script versions.

The `TUNNEL_VERSION` pin in [`VERSION`](VERSION) tracks the [upstream mhrv-rs releases](https://github.com/therealaleph/MasterHttpRelayVPN-RUST/releases).

---

## [Unreleased]

### Planned
- Multi-region tunnel orchestrator UI
- Auto-update notification via Telegram bot
- Health monitoring dashboard

### Added (2026-05-21)
- **🤖 Auto-sync workflow** (`.github/workflows/sync-upstream.yml`):
  - Runs every 2 days at 18:00 UTC (21:30 Tehran time)
  - Schedule: `0 18 2,4,6,8,10,12,14,16,18,20,22,24,26,28,30 * *`
  - First run: May 22, 2026 18:00 UTC
  - Checks upstream `therealaleph/MasterHttpRelayVPN-RUST` for new releases
  - Auto-updates: CodeFull.gs.template, VERSION, HTML download links,
    README badges, CHANGELOG (this file)
  - Commits + pushes only if upstream changed
  - Manual trigger available via Actions → workflow_dispatch

---## [1.9.35] — 2026-05-26 (auto-synced from upstream)

### Changed
- **Synced to mhrv-rs v1.9.35** (was v1.9.34)
- CodeFull.gs.template updated to match upstream
- All download links in `index.html` / `pc-ios.html` / README updated
- VERSION file pin updated to 1.9.35

### Upstream notes
> ℹ️ CodeFull.gs بدون تغییر نسبت به نسخه قبل — تغییرات این release فقط در اپ Rust (نه Apps Script).

Auto-synced by `.github/workflows/sync-upstream.yml`

---

## [1.9.34] — 2026-05-22 (auto-synced from upstream)

### Changed
- **Synced to mhrv-rs v1.9.34** (was v1.9.33)
- CodeFull.gs.template updated to match upstream
- All download links in `index.html` / `pc-ios.html` / README updated
- VERSION file pin updated to 1.9.34

### Upstream notes
> <div dir="rtl">

Auto-synced by `.github/workflows/sync-upstream.yml`

---

## [2.0.0] — 2026-05-21

### Added
- **VERSION pinning system** — tunnel-node version is now pinned via [`VERSION`](VERSION) file (no more `:latest` surprises)
- **Auto-rollback in update.sh** — if update fails, automatically reverts to previous container image
- **AUTH validation** in `install.sh`:
  - Minimum 16 characters
  - Rejects common weak patterns (names, "password", "admin", etc.)
  - Rejects shell-dangerous characters
- **Smart pre-flight checks** in `install.sh`:
  - Detects port already bound by other service (nginx, apache, etc.) before install
  - Shows which PID holds the port and how to free it
  - Detects "wrong service" responses (HTML/Forbidden) instead of tunnel-node
- **IP detection with 4-source fallback** — ipify, icanhazip, ipinfo, ifconfig.me, then hostname -I
- **Memory limit** for tunnel-node container — `--memory=512m --memory-swap=1g` (helps on 1GB VPS)
- **Bilingual README** (English + Persian) for international visibility
- **`LICENSE`** file (MIT)
- **`CONTRIBUTING.md`** with code style guide
- **`SECURITY.md`** with private vulnerability reporting
- **GitHub issue templates** (bug report, feature request)
- **PR template** with testing checklist
- **`DONATE.md`** with TRC20 Tron address + transparency cost breakdown
- **`FUNDING.yml`** — adds 💟 Sponsor button to repo

### Changed
- `update.sh` — completely rewritten:
  - Reads pinned version from `VERSION` file (not `:latest`)
  - Records current image for rollback before update
  - Conditional warning for v1.9.32+ updates (zstd compatibility)
  - Removed misleading "no redeploy needed" message
- `install.sh` — version updated to v2.0:
  - Memory limits applied to container
  - All `:latest` references replaced with pinned version
- `CodeFull.gs.template` — updated to v1.9.33 (773 lines)
- Repository description, topics (20 tags), homepage all properly set

### Fixed
- **403 Forbidden after install** — caused by other service holding port 8080 (now detected pre-install)
- **"Cannot view IP" error** — fixed with multi-source IP detection
- **Wrong AUTH (user's name)** — fixed with validation + 🎲 button on interactive page

---

## [1.9.33] — 2026-05-20 (synced with upstream)

Upstream mhrv-rs released v1.9.31, v1.9.32, v1.9.33 in rapid succession. We tested and synced:

### Added
- Support for **zstd compression** (v1.9.32) — 30% download bandwidth savings
- Updated AI debug bot knowledge base with v1.9.31/32/33 patterns

### Fixed (upstream)
- **Quota burn fix** (v1.9.31) — idle Full-mode sessions no longer generate excessive empty polls
- **WebRTC voice calls** (v1.9.31) — `block_stun` default changed from true → false
- **Mixed-fleet keepalive** (v1.9.33) — better round-robin for deployment fleets with both old and new versions

---

## [1.9.30] — 2026-05-18

### Changed
- `CodeFull.gs.template` updated to v1.9.30 (745 lines, was 753)
- AI debug bot knowledge base now includes 14 official troubleshooting patterns from upstream `docs/android.fa.md`

---

## [1.9.29] — 2026-05-17

### Added
- AI debug bot launched (@Vpscript_bot) — free log analysis via Groq AI
- Pinned to GitHub for transparency

---

## [1.9.28] — 2026-05-16

### Added
- First version using `CodeFull.gs` (753 lines)
- Block STUN/TURN UDP support added to client config

---

## Earlier versions

For changelog of versions before this format was adopted, see [GitHub releases](https://github.com/KIAN-IRANI/mhrv-setup-full-tunell/releases) or commit history.
