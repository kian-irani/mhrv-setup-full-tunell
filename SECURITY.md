# Security Policy

## 🔒 Reporting a vulnerability

If you find a security issue, **do not open a public issue**. Instead:

### Contact privately

- 📧 Email: `kian.irani.gh@gmail.com`
- 💬 Telegram: [@Kian_irani_t](https://t.me/Kian_irani_t)

We'll respond within 48 hours.

## 🛡️ Scope

### In scope (this repo)
- `install.sh` / `update.sh` / `check.sh` — shell injection, AUTH validation bypass
- `index.html` / `guide.html` / `pc-ios.html` — XSS, CSRF, leaked secrets
- `CodeFull.gs.template` — incorrect placeholder substitution that leaks user keys

### Out of scope (upstream)
- mhrv-rs app itself → report to [upstream](https://github.com/therealaleph/MasterHttpRelayVPN-RUST/security)
- tunnel-node Docker image → same upstream
- Google Apps Script platform → Google's security team

## 🔐 Best practices for users

If you're using this setup:

1. **Generate a strong AUTH key.** Use `openssl rand -hex 16` or the 🎲 button on the page. **Never use your name or simple words.**
2. **Don't share your script with others.** Each Apps Script deployment is tied to your Gmail quota. Sharing burns through it fast.
3. **Keep your VPS updated.** `apt update && apt upgrade -y` weekly.
4. **Use UFW or another firewall.** Our `install.sh` configures it, but check `ufw status` periodically.
5. **Use SSH keys, not passwords.** Disable password auth in `/etc/ssh/sshd_config`.
6. **Don't expose port 22.** Change SSH port or restrict by IP if possible.

## 📜 Disclosure timeline

After a report:

| Day | Action |
|-----|--------|
| 0 | Acknowledge receipt |
| 1-7 | Investigate, develop fix |
| 7-14 | Test fix, prepare release |
| 14+ | Release, publish CVE (if applicable), credit reporter |

We may extend timelines for complex issues, with regular updates to the reporter.

## 🏆 Hall of Fame

(Reporters of valid security issues will be credited here, with permission.)

---

Thank you for helping keep this project and its users safe.
