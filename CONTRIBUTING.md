# Contributing

Thanks for considering contributing! Here's how to help.

## 🐛 Found a bug?

1. Check [existing issues](https://github.com/KIAN-IRANI/mhrv-setup-full-tunell/issues) first
2. If new, [open an issue](https://github.com/KIAN-IRANI/mhrv-setup-full-tunell/issues/new) with:
   - What you expected vs what happened
   - Steps to reproduce
   - Your OS, VPS provider, app version
   - Relevant logs (sanitize secrets!)

## 💡 Have an idea?

[Open a discussion](https://github.com/KIAN-IRANI/mhrv-setup-full-tunell/discussions) or contact [@Kian_irani_t](https://t.me/Kian_irani_t) on Telegram.

## 🔧 Want to contribute code?

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/amazing-thing`)
3. Test your changes locally
4. Commit with clear message
5. Push and open a Pull Request

### What we accept

- 🐛 Bug fixes (always welcome)
- 📖 Documentation improvements (especially translations to other languages)
- ✨ New features that help end users
- 🌍 Translations of the interactive guide

### What we don't accept

- ❌ Major architecture changes without prior discussion
- ❌ Features that only work for specific VPS providers
- ❌ Dependencies that aren't strictly necessary
- ❌ Code that breaks Persian text rendering or RTL layout

## 🌍 Translating

The interactive page is **bilingual** (English + Persian). To add another language:

1. Copy `index.html` to `index.<lang>.html`
2. Translate user-facing text (keep CSS/JS unchanged)
3. Add a language switcher in the header
4. PR with screenshot

## 📜 Code style

- **Bash scripts:** POSIX-compatible when possible, `set -e` always
- **HTML/CSS:** No build step — pure HTML/CSS/JS, no React/Vue
- **Comments:** English in code; user-facing text bilingual where appropriate

## 🤝 Code of Conduct

Be kind. Don't be a jerk. Help people learn. That's it.

---

By contributing, you agree your contributions will be licensed under the [MIT License](LICENSE).
