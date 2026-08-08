# EvilNote

**Professional bulk email sender for Windows** — SMTP rotation, From spoofing, templates, leads, scheduled sends. HackerMode UI (black / white).

**100% free** to download and use. No subscription required for the desktop app.

---

## Download

Grab the latest Windows installer from **Releases** (or build it yourself — see below).

| | |
|---|---|
| **Contact** | [https://jinkusu.dev](https://jinkusu.dev) |
| **Telegram** | [https://t.me/JINKUSUDEVELOP](https://t.me/JINKUSUDEVELOP) |

After install, run **EvilNote** from the Start Menu or desktop shortcut. Everything runs **locally on your PC** — no VPS / hosting needed for the UI.

---

## How it works

1. Open EvilNote.
2. Click **Generate key for this PC** → you get a key like `EN-XXXX-XXXX-XXXX-XXXX`.
3. **Copy and save** the key (it is bound to this computer).
4. Click **Login with key**.
5. Add an SMTP profile → send single or bulk mail from the dashboard.

Your data (SQLite database, key material) stays under `%APPDATA%\EvilNote\`.

> The key is valid **only on the PC where it was generated**. On another machine, generate a new key.

---

## Features

### Send
- Single or **bulk** send
- **SMTP rotation** (multiple profiles, round-robin)
- **From spoof** — custom From address + display name
- **From rotation** — cycle From identities per message
- Reply-To, preheader, List-Unsubscribe URL
- Custom headers
- Send delay / speed presets
- Live **preview** with `{{email}}` / `{{name}}`
- **Schedule** sends for later (desktop runs a local cron every minute)
- View / cancel pending scheduled jobs
- Daily quota display

### SMTP
- Add / edit / delete profiles (host, port, TLS, user, password, default From)
- Connection **test** + test email

### Leads
- Paste emails or upload `.txt` / `.csv`
- Optional names for personalization
- Reusable lists

### Templates
- Save subject + HTML/text body
- Default From / name / Reply-To per template
- Variables: `{{email}}`, `{{name}}`

### Logs & Blacklist
- Send history with status / errors
- **Export CSV**
- Per-user blacklist (never send to these addresses)

### Charts
- Sends per day and success vs failure (when data exists)

### Security / UX
- PC-bound device key (no password / captcha on desktop login)
- Frameless HackerMode window (black & white)
- App + installer icon from project logo

---

## Screenshots / UI

Dark terminal-style dashboard: **Send · SMTP · Leads · Templates · Logs · Blacklist**.

---

## Build from source (Windows)

**Requirements:** Node.js 20+, Windows x64.

```bash
npm install
npm run desktop:build
```

Installer output:

```text
release/EvilNote-Setup-2.0.5.exe
```

### Dev mode

```bash
npm run desktop:dev
```

### Useful scripts

| Script | Description |
|--------|-------------|
| `npm run desktop:build` | Production NSIS installer |
| `npm run desktop:dev` | Electron + Next in development |
| `npm run icons` | Rebuild `icon.ico` / favicon from `public/logo.png` |
| `npm run db:push` | Sync Prisma schema (SQLite) |

---

## Tech stack

- **Next.js** (App Router) + React + TypeScript  
- **Prisma** + SQLite (`better-sqlite3`)  
- **Nodemailer** (SMTP pool, retries)  
- **Electron** + electron-builder (Windows NSIS)

---

## License / usage

Free to download and use for personal or commercial projects as provided by the author.

Questions or custom work:

- Website: [jinkusu.dev](https://jinkusu.dev)  
- Telegram: [@JINKUSUDEVELOP](https://t.me/JINKUSUDEVELOP)

---

<p align="center">
  <strong>EvilNote</strong> — bulk mail. spoof. done.<br/>
  Made by <a href="https://jinkusu.dev">JINKUSU</a>
</p>
