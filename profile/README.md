# CrydenSync 🔐

<div align="center">

**Open-source, embeddable authentication infrastructure for modern developers**

[![GitHub Org](https://img.shields.io/badge/GitHub-CrydenSync-6366f1?style=flat-square&logo=github)](https://github.com/crydensync)
[![Go Reference](https://img.shields.io/badge/Go-Reference-00ADD8?style=flat-square&logo=go)](https://pkg.go.dev/github.com/crydensync/cryden)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)
[![Twitter Follow](https://img.shields.io/twitter/follow/crydensync?style=social)](https://twitter.com/crydensync)

</div>

---

## 🎯 What is CrydenSync?

CrydenSync is an **embeddable authentication engine** that gives developers a standard, reusable auth system they control. 

**Think of it as:**  
`import "github.com/crydensync/cryden"` → production-ready auth in minutes.

**No vendor lock-in. No cloud dependency. Your users belong to YOU.**

---

## 🌍 Built for Africa, Ready for the World

```markdown
🇳🇬 🇰🇪 🇿🇦 🇬🇭 🇪🇬 🇹🇿 🇺🇬 🇸🇳 🇷🇼 🇳🇦 🇿🇲 🇨🇲 🇪🇹 🇲🇦 🇩🇿

**African developers are our priority.**
**Termux developers out first class citizens.**
**Offline-first. Low bandwidth. Affordable.**
**Your data, your rules, your continent.**
```

---

🚀 Our Projects

Project Description Status Go Doc
cryden Core auth engine ✅ v1.0.0 https://pkg.go.dev/badge/github.com/crydensync/cryden.svg
typebook Demo app with auth ✅ v1.0.0 -
docs Documentation website 🚧 Building -
csax CLI tool 📅 v1.1.0 -
sdk-js JavaScript SDK 📅 v1.2.0 -
sdk-py Python SDK 📅 v1.2.0 -

---

✨ What Makes CrydenSync Different?

🏝️ Offline-First

Auth works without internet during development. SQLite by default.

👑 Own Your Users

Your users belong to you, not us. User data stays in your database.

🔌 Framework Agnostic

No HTTP, no cookies, no headers. Pure logic you can wrap anywhere.

🌍 African-First, Global-Ready

Built for real-world constraints (unstable internet, affordable infra), works everywhere.

---

📦 Quick Start

```go
import "github.com/crydensync/cryden"

func main() {
    engine := cryden.New()
    ctx := context.Background()
    
    // Sign up
    user, _ := cryden.SignUp(ctx, engine, "alice@example.com", "SecurePass123")
    
    // Login
    tokens, _, _ := cryden.Login(ctx, engine, "alice@example.com", "SecurePass123")
    
    // Protect routes
    userID, _ := cryden.VerifyToken(engine, tokens.AccessToken)
}
```

📚 Get Started →

---

🗺️ Roadmap

Version Focus Status
v1.0.0 Core Auth ✅ Released (March 2026)
v1.1.0 Dev Experience 🚧 Coming June 2026
v1.2.0 API & SDKs 📅 Q3 2026
v1.3.0 Advanced Auth 📅 Q4 2026

v1.1.0 Features:

· 🔐 SHA-256 token hashing
· 🖥️ CLI tool (csax)
· 📱 Device tracking
· 📁 File audit logger
· 👤 User metadata
· 🐬 MySQL support

---
## 🤝 We Need You!

### Current Open Roles

| Role | Need | Apply |
|------|------|-------|
| **Go Developer** | Core auth implementation | [Issues](link) |
| **Security Engineer** | Security audit, cryptography | [Issues](link) |
| **Database Expert** | SQLite, PostgreSQL, MongoDB adapters | [Issues](link) |
| **Documentation Writer** | Guides, examples, API docs | [Issues](link) |
| **Test Engineer** | Unit, integration, security tests | [Issues](link) |
| **Junior Dev** | Good first issues, learn by doing | [Issues](link) |

### How to Join

1. Read the [CONTRIBUTING.md](CONTRIBUTING.md)
2. Check [open issues](https://github.com/crydensync/cryden/issues)
3. Join [Discord](https://discord.gg/crydensync)
4. Introduce yourself in #introductions

### What We Offer

- 📚 **Mentorship** - Learn from experienced developers
- 🏗️ **Real Project** - Build something people use
- 🌍 **Community** - Work with devs worldwide
- 📝 **Portfolio** - Open source contributions
- 🎯 **Impact** - Help developers own their users

### First Time Contributors Welcome!

Look for issues labeled:
- `good-first-issue`
- `help-wanted`
- `documentation`

**We'll help you make your first PR!**

## 💬 Community

**African developers: WhatsApp is our primary home.**

| Type | Link | Purpose |
|------|------|---------|
| **WhatsApp Channel** | [Join Channel](https://whatsapp.com/channel/your-channel-id) | 📢 Announcements only (1-way) |
| **WhatsApp Group** | [Join Group](https://chat.whatsapp.com/your-group-id) | 💬 Discussions, help, contributions (2-way) |
| **Discord** | [Join Discord](https://discord.gg/crydensync) | 🎙️ Voice calls, technical deep dives |
| **GitHub** | [Discussions](https://github.com/crydensync/cryden/discussions) | 📝 Long-form technical discussions |

### Which One to Join?

- **Just want updates?** → Join the Channel
- **Want to ask questions?** → Join the Group
- **Want voice calls?** → Join Discord
- **Want to contribute code?** → GitHub Discussions

### Direct WhatsApp Chat with Maintainers

Need help? Chat directly: [Ask on WhatsApp](https://wa.me/+2348028420932?text=I%20need%20help%20with%20CrydenSync)

> Built in Nigeria. For African developers. Welcoming the world.
---

📄 License

All CrydenSync projects are open source under the MIT License.

Free forever. Open always. Own your users.

---

<div align="center">

Built with ❤️ in Nigeria, for developers everywhere.

Own your users, not vendor lock-in.

---

🌍 WhatsApp Community • 🐦 Twitter • 💬 Discord • 📝 GitHub

</div>
