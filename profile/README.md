# CrydenSync 🔐

<div align="center">

**Open-source, embeddable authentication infrastructure for modern developers**

[![GitHub Org](https://img.shields.io/badge/GitHub-CrydenSync-6366f1?style=flat-square&logo=github)](https://github.com/crydensync)
[![Go Reference](https://img.shields.io/badge/Go-Reference-00ADD8?style=flat-square&logo=go)](https://pkg.go.dev/github.com/crydensync/cryden/v2)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)
[![Twitter Follow](https://img.shields.io/twitter/follow/crydensync?style=social)](https://x.com/CrydenSync)

</div>

---

## 🎯 What is CrydenSync?

CrydenSync is an **embeddable authentication engine** that gives developers a standard, reusable auth system they control.

**Think of it as:**
`import "github.com/crydensync/cryden/v2"` → production-ready auth in minutes.

**No vendor lock-in. No cloud dependency. Your users belong to YOU.**

---

## 🌍 Built for Africa, Ready for the World

```
🇳🇬 🇰🇪 🇿🇦 🇬🇭 🇪🇬 🇹🇿 🇺🇬 🇸🇳 🇷🇼 🇳🇦 🇿🇲 🇨🇲 🇪🇹 🇲🇦 🇩🇿

African developers are our priority.
Offline-first storage is on the roadmap — see below.
Affordable to run, self-hosted, no forced cloud dependency.
Your data, your rules, your continent.
```

---

## 🚀 Our Projects

| Project | Description | Status |
|---|---|---|
| **cryden** | Core auth engine | ✅ v2.0.0 — full rewrite, tested, Postgres-backed |
| **typebook** | Reference app (notes, full auth flow) | ✅ Built |
| **api** | Self-hosted HTTP wrapper | ✅ Built, tested end-to-end |
| **csax** | Admin CLI | ✅ Built — users, sessions, audit, stats, migrations |
| **sdk-js** | JavaScript/TypeScript SDK | ✅ Built, tested — not yet published to npm |
| **sdk-py** | Python SDK | 📅 Planned |
| **docs** | Documentation site | 🚧 In progress |

*Why v2, not v1? The original v1 had real, since-fixed security issues (predictable session IDs, a hardcoded default JWT secret, broken rate limiting). v2 is a ground-up rewrite that fixes these at the architecture level — see the [design decisions doc](https://github.com/crydensync/cryden/blob/main/docs/design-decisions.md) for the full story.*

---

## ✨ What Makes CrydenSync Different?

**👑 Own Your Users**
Your users belong to you, not us. User data stays in your own Postgres database, self-hosted, from the first line of code.

**🔌 Framework Agnostic**
No HTTP, no cookies, no headers baked in. Pure logic you can wrap with a CLI, an HTTP API, or embed directly in your Go app.

**🕵️ Zero Telemetry**
The engine never phones home. Logs, audit events, and email delivery all go wherever *you* configure — nothing leaves your infrastructure by default.

**🌍 African-First, Global-Ready**
Built with real-world constraints in mind (unstable connectivity, affordable infrastructure) — self-hosting anywhere, including on modest hardware, is a first-class use case, not an afterthought. True offline-first local storage (e.g. SQLite) is a real, planned roadmap item, not shipped yet.

---

## 📦 Quick Start

```go
import (
	"context"

	"github.com/crydensync/cryden/v2"
	"github.com/crydensync/cryden/v2/store/postgres"
)

func main() {
	db, _ := sql.Open("postgres", os.Getenv("DATABASE_URL"))

	engine, _ := cryden.New(cryden.Config{
		JWTSecret: os.Getenv("JWT_SECRET"),
		Users:     postgres.NewUserStore(db),
		Sessions:  postgres.NewSessionStore(db),
		Audit:     postgres.NewAuditStore(db),
	})
	ctx := context.Background()

	// Sign up
	user, _ := cryden.SignUp(ctx, engine, "devray@example.com", "Pass@2026", callerIP)

	// Login
	tokens, _ := cryden.Login(ctx, engine, "devray@example.com", "Pass@2026", callerIP, userAgent)

	// Protect routes
	userID, _ := cryden.VerifyToken(engine, tokens.AccessToken)
}
```

No database yet? Swap in `store/memory` for a zero-setup version to try it out.

📚 [Get Started →](https://github.com/crydensync/cryden#readme)

---

## 🗺️ Roadmap

| Focus | Status |
|---|---|
| Core engine — auth, sessions, token rotation with reuse detection, account lockout, email verification | ✅ Shipped (v2.0.0) |
| Admin CLI, self-hosted HTTP API, JS SDK | ✅ Built |
| Documentation site | 🚧 In progress |
| OAuth (Google, GitHub), Python SDK, React SDK layer | 📅 Next |
| AI-assisted admin tooling (natural-language queries, audit review — human-confirmed actions only, never automatic) | 📅 Planned |
| A second storage backend (e.g. SQLite, for true offline-first use) | 📅 Deliberately deferred, not yet scoped |

*A hosted, multi-tenant CrydenSync Cloud is explicitly not on the current roadmap — every deployment is self-hosted, by design.*

---

## 🤝 We Need You!

### Current Open Roles

| Role | Need |
|---|---|
| **Go Developer** | Core engine, CLI, API |
| **Security Reviewer** | The engine has extensive automated tests but no external security audit yet — this is genuinely needed |
| **Frontend/SDK Developer** | JS SDK polish, Python SDK, React hooks layer |
| **Documentation Writer** | Guides, examples, real-world tutorials |
| **Test Engineer** | More integration coverage, especially around edge cases |
| **Junior Dev** | Good-first-issues, learn by contributing to a real project |

<!-- TODO: link each row to a real, curated GitHub issue or label filter once issues exist -->

### How to Join

1. Read [CONTRIBUTING.md](https://github.com/crydensync/cryden/blob/main/CONTRIBUTING.md)
2. Check [open issues](https://github.com/crydensync/cryden/issues)
3. Join the [WhatsApp group](#-community) or [Discord](#-community)
4. Introduce yourself

### First-Time Contributors Welcome

Look for issues labeled `good-first-issue`, `help-wanted`, or `documentation`. We'll help you land your first PR.

---

## 💬 Community

**African developers: WhatsApp is our primary home.**

| Type | Link | Purpose |
|---|---|---|
| **WhatsApp Channel** | [Join](https://chat.whatsapp.com/IkPWOYlnr4DI6zTzEC0g8m) | 📢 Announcements only (1-way) |
| **WhatsApp Group** | <!-- TODO: this currently points to the same link as the Channel above — add the real group invite --> | 💬 Discussions, help, contributions (2-way) |
| **Discord** | [Join](https://discord.gg/xUCYcDBAWx) | 🎙️ Voice calls, technical deep dives |
| **GitHub** | [Discussions](https://github.com/crydensync/cryden/discussions) | 📝 Long-form technical discussions |
| **X / Twitter** | [@CrydenSync](https://x.com/CrydenSync) | Updates |

- Just want updates? → Join the Channel
- Want to ask questions? → Join the Group
- Want voice calls? → Discord
- Want to contribute code? → GitHub Discussions

Direct: [Ask on WhatsApp](https://wa.me/+2347075937777?text=I%20need%20help%20with%20CrydenSync)

> Built in Nigeria. For African developers. Welcoming the world.

---

## 📄 License

All CrydenSync projects are open source under the MIT License.

Free forever. Open always. Own your users.

<div align="center">

Built with ❤️ in Nigeria, for developers everywhere.

**Own your users, not vendor lock-in.**

</div>
