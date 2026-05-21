<div align="center">

# 🛡️ mhrv-rs Setup Guide

### Interactive setup guide for Full Tunnel anti-censorship VPN on Android

**🇮🇷 [راهنمای فارسی پایین‌تر صفحه](#راهنمای-فارسی)** — Persian guide below

[![Interactive Page](https://img.shields.io/badge/Live%20Site-Open%20in%20Browser-3fb950?style=for-the-badge&logo=github)](https://kian-irani.github.io/mhrv-setup-full-tunell/)
[![Visual Guide](https://img.shields.io/badge/Visual%20Guide-8%20Steps-58a6ff?style=for-the-badge&logo=gitbook)](https://kian-irani.github.io/mhrv-setup-full-tunell/guide.html)
[![PC/iPhone](https://img.shields.io/badge/PC%20%26%20iPhone-Guide-8957e5?style=for-the-badge&logo=apple)](https://kian-irani.github.io/mhrv-setup-full-tunell/pc-ios.html)
[![Telegram Channel](https://img.shields.io/badge/Telegram-Channel-26A5E4?style=for-the-badge&logo=telegram)](https://t.me/kian_irani_cdn_f)
[![Bot](https://img.shields.io/badge/Script%20Bot-Free-3fb950?style=for-the-badge&logo=telegram)](https://t.me/Mhrv_script_bot)
[![Debug Bot](https://img.shields.io/badge/AI%20Debug%20Bot-Free-e3b341?style=for-the-badge&logo=telegram)](https://t.me/Vpscript_bot)

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Stars](https://img.shields.io/github/stars/KIAN-IRANI/mhrv-setup-full-tunell?style=social)](https://github.com/KIAN-IRANI/mhrv-setup-full-tunell/stargazers)
[![Forks](https://img.shields.io/github/forks/KIAN-IRANI/mhrv-setup-full-tunell?style=social)](https://github.com/KIAN-IRANI/mhrv-setup-full-tunell/network/members)

---

**Free, root-less, undetectable VPN routed through Google's edge servers.**

</div>

---

## ⚡ What is this?

A complete setup toolkit for **[mhrv-rs](https://github.com/therealaleph/MasterHttpRelayVPN-RUST)** — an anti-censorship VPN that tunnels your Android traffic through **Google Apps Script** to a tunnel node on your VPS.

**Your ISP only sees a TLS connection to `www.google.com`** — no DPI fingerprint, no protocol detection, no easy way to filter.

### How it works

```
📱 Your phone
    ↓  TLS — SNI: www.google.com  ← ISP only sees this
☁️  Google Edge  (cannot be filtered)
    ↓
📝 Apps Script  (your Gmail — free)
    ↓
🖥️  Tunnel Node  (your VPS)
    ↓
🌍 Free internet
```

---

## ✨ Features

- 🆓 **100% free** — uses your own Google account quota (20k requests/day)
- 🔓 **No root needed** — works on any Android 7+
- 🛡️ **True Full Tunnel** — no MITM certificates needed (since v1.9.28)
- ⚡ **Self-hosted** — your data only goes through Google → your VPS → internet
- 🔄 **Auto-updates** — pinned versions with auto-rollback on failure
- 🌐 **Cross-platform** — Android, Windows, macOS, Linux supported

---

## 🚀 Quick Start

### 1. Get a script (free, ~30 seconds)

Choose one of two methods:

**Easiest:** Use the [Telegram bot](https://t.me/Mhrv_script_bot) → click "Get Script" → done.

**Or:** Use this [interactive page](https://kian-irani.github.io/mhrv-setup-full-tunell/) → enter your VPS info → copy generated script.

### 2. Deploy on Google Apps Script

1. Open [script.google.com](https://script.google.com), create new project
2. Paste the script you got in step 1
3. **Deploy** → New deployment → Web app → Execute as: **Me**, Access: **Anyone**
4. Copy the **Deployment ID** (starts with `AKfycb...`)

### 3. Install tunnel node on your VPS

One command — auto installs Docker, configures firewall, runs container:

```bash
PORT="8080" AUTH="$(openssl rand -hex 16)" SSH_PORT="22" \
  bash <(curl -fsSL https://raw.githubusercontent.com/KIAN-IRANI/mhrv-setup-full-tunell/main/install.sh)
```

> ⚠️ **Don't use your name as AUTH!** It must be a random secret (≥16 chars). The interactive page has a 🎲 button to generate one.

### 4. Configure the Android app

Download the [mhrv-rs APK](https://github.com/therealaleph/MasterHttpRelayVPN-RUST/releases/latest) → install → enter:

- **Deployment ID** (from step 2)
- **AUTH key** (from step 3)
- Set Mode to **Full Tunnel (no cert)**

Done. Enjoy free internet.

---

## 📦 What's in this repo

| File | Purpose |
|------|---------|
| [`index.html`](index.html) | Interactive setup wizard (live at [the GitHub Pages site](https://kian-irani.github.io/mhrv-setup-full-tunell/)) |
| [`guide.html`](guide.html) | 8-step visual deployment guide |
| [`pc-ios.html`](pc-ios.html) | PC (Windows/macOS/Linux) & iPhone setup guide |
| [`install.sh`](install.sh) | One-shot VPS installer (Docker + firewall + tunnel-node) |
| [`update.sh`](update.sh) | Smart updater with auto-rollback on failure |
| [`check.sh`](check.sh) | Health check & diagnostics |
| [`VERSION`](VERSION) | Pinned tunnel-node version (currently `1.9.33`) |
| [`CodeFull.gs.template`](CodeFull.gs.template) | Apps Script template with `%%AUTH_KEY%%` / `%%TUNNEL_URL%%` placeholders |

---

## 🖥️ System requirements

### Android
- Android 7+ (lower may work, not tested)
- ~50 MB free storage

### VPS (for Full Tunnel)
- 1 vCPU
- 1 GB RAM (2 GB recommended)
- 10 GB disk
- Ubuntu 20.04+ or Debian 11+
- Any provider — but Iran ISPs throttle some IPs (OVH, Hetzner France).
  **Recommended:** Netlen, Contabo, Hostinger, or anywhere outside throttled ranges.

### Windows/macOS/Linux client
- mhrv-rs Windows app (SOCKS5 on `127.0.0.1:1081`)
- For system-wide tunneling: pair with [NekoBox](https://github.com/MatsuriDayo/nekoray/releases) (GUI) or [sing-box](https://github.com/SagerNet/sing-box/releases) (CLI)

---

## 🆘 Support & Community

| Resource | Link |
|----------|------|
| 📢 Channel (Persian) | [@kian_irani_cdn_f](https://t.me/kian_irani_cdn_f) |
| 💬 Discussion group | [@kiancdn_group](https://t.me/kiancdn_group) |
| 🤖 Free script bot | [@Mhrv_script_bot](https://t.me/Mhrv_script_bot) |
| 🩺 **AI debug bot** | [@Vpscript_bot](https://t.me/Vpscript_bot) — paste your log, get instant analysis |
| 🆘 Direct support | [@Kian_irani_t](https://t.me/Kian_irani_t) |
| 🖥 Dedicated VPS setup | [@Kian_irani_vps](https://t.me/Kian_irani_vps) |

---

## 🤝 Contributing

Contributions welcome! Please open an issue first for major changes. See [CONTRIBUTING.md](CONTRIBUTING.md).

For security issues, see [SECURITY.md](SECURITY.md).

---

## 🙏 Credits

This is a **community helper / setup wrapper** for the upstream project:

- **[@therealaleph](https://github.com/therealaleph)** — Rust port + active maintainer of [mhrv-rs](https://github.com/therealaleph/MasterHttpRelayVPN-RUST)
- **[@masterking32](https://github.com/masterking32)** — original idea

All credit for the actual VPN goes to them. This repo only provides **easier onboarding** for Persian-speaking users.

---

## 📄 License

MIT — see [LICENSE](LICENSE)

---

<div align="center">

## راهنمای فارسی

</div>

### 🛡️ mhrv-rs — رد فیلتر اختصاصی برای اندروید

ابزار راه‌اندازی برای **[mhrv-rs](https://github.com/therealaleph/MasterHttpRelayVPN-RUST)** — یه VPN ضد سانسور که ترافیک گوشی اندرویدت رو از طریق **Google Apps Script** به یه tunnel-node روی VPS خودت رد می‌کنه.

**ISP فقط یه اتصال TLS به `www.google.com` می‌بینه** — هیچ پترن قابل تشخیصی نیست.

### ⚡ ویژگی‌ها

- 🆓 **کاملاً رایگان** — از سهمیه روزانه گوگل خودت استفاده می‌کنه (۲۰هزار درخواست/روز)
- 🔓 **بدون نیاز به Root**
- 🛡️ **Full Tunnel واقعی** — بدون نیاز به نصب گواهی
- ⚡ **خودمیزبان** — داده فقط از گوگل → VPS تو → اینترنت رد می‌شه
- 🔄 **آپدیت خودکار** — با rollback خودکار اگه fail بشه

### 🚀 شروع سریع

**۱.** اسکریپت رو از [ربات تلگرام](https://t.me/Mhrv_script_bot) بگیر (رایگان)

**۲.** در [script.google.com](https://script.google.com) deploy کن، Deployment ID رو کپی کن

**۳.** روی VPS:
```bash
PORT="8080" AUTH="$(openssl rand -hex 16)" SSH_PORT="22" \
  bash <(curl -fsSL https://raw.githubusercontent.com/KIAN-IRANI/mhrv-setup-full-tunell/main/install.sh)
```

**۴.** در اپ اندروید [mhrv-rs](https://github.com/therealaleph/MasterHttpRelayVPN-RUST/releases/latest)، Deployment ID و AUTH رو وارد کن.

### 📖 راهنمای کامل تصویری

به **[صفحه تعاملی](https://kian-irani.github.io/mhrv-setup-full-tunell/)** برو — همه چیز با مراحل تصویری.

### 🩺 مشکل داری؟

ربات اشکال‌زدای ما با هوش مصنوعی لاگ رو تحلیل می‌کنه و راه‌حل می‌ده — **رایگان**:
**[@Vpscript_bot](https://t.me/Vpscript_bot)**

### 💬 ارتباط با ما

- 📢 کانال: [@kian_irani_cdn_f](https://t.me/kian_irani_cdn_f)
- 💬 گروه گفتگو: [@kiancdn_group](https://t.me/kiancdn_group)
- 🆘 پشتیبانی: [@Kian_irani_t](https://t.me/Kian_irani_t)
- 🖥 سرور اختصاصی: [@Kian_irani_vps](https://t.me/Kian_irani_vps)

---

<div align="center">

**Made with ❤️ for a free internet**

[Star this repo ⭐](https://github.com/KIAN-IRANI/mhrv-setup-full-tunell) if it helped you

</div>
