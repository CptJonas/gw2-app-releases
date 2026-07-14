# GW2 App

A free Windows companion app for **Guild Wars 2**. It pulls your account data straight from the official Guild Wars 2 API and puts your dailies, wallet, Wizard's Vault progress, trading post prices, and crafting profits in one place — so you don't have to have five browser tabs open every time you log in.

Made by **CptJonas** (in-game: `CptJonas.9012`).

> **Unofficial fan project.** GW2 App is not made, endorsed, or supported by ArenaNet. It only *reads* your account data through the official public API — it can't log in as you, trade, or change anything on your account.

---

## Contents

- [What it does](#what-it-does)
- [Requirements](#requirements)
- [Installing](#installing)
- [Connecting your API key](#connecting-your-api-key)
- [Updating](#updating)
- [Troubleshooting](#troubleshooting)
- [Feedback & bug reports](#feedback--bug-reports)

---

## What it does

- **Home** — a dashboard: your daily reset countdown, gold/karma/Astral Acclaim/spirit shards at a glance, today's Wizard's Vault objectives (daily *and* weekly), daily fractal rotation with instabilities, raid rotations, and live world events.
- **Wizard's Vault** — full daily/weekly/special objective tracker, plus the rewards shop sorted by value per Astral Acclaim so you know what's actually worth buying.
- **Trading Post** — search item prices, and set **price alerts** that pop up a Windows notification when an item crosses your target price, even while GW2 App sits minimized in the background.
- **Crafting calculator** — profit/loss for craftable items, including the full ingredient tree.
- **Builds** — keep your own build templates (chat codes) in one list, and jump straight to build resources like Snow Crows, Hardstuck, MetaBattle, and gw2skills.net without leaving the app.
- **Characters, Bank, Material Storage, Wallet, Account info** — read-only views of your account, including things the in-game UI doesn't show together (e.g. mastery points and playtime side by side).
- **Session tracker** — see what you gained (gold, loot, karma, …) since you last hit "start session".
- **Search** — find an item across your bank, materials, and inventory at once.
- **Community & LFG** *(optional)* — a separate, opt-in sign-up for finding groups and posting your build for raids/strikes/fractals. Not required for anything else in the app.

GW2 App keeps running quietly in the **system tray** after you close the window, so Trading Post alerts keep working in the background. It supports dark and light themes, and the game-content language (item and currency names) can be switched independently of your account's actual language.

---

## Requirements

- Windows 10 or 11 (64-bit)
- A Guild Wars 2 account
- An internet connection — GW2 App talks to the official `api.guildwars2.com`

No Python, no .NET runtime to install separately — the installer bundles everything it needs.

---

## Installing

1. Open the [**Releases**](../../releases) page and, under **Assets** on the latest release, download **`Gw2App-win-Setup.exe`**.
2. Double-click it to run.
3. Windows will very likely show a blue **"Windows protected your PC"** screen. This isn't a virus warning — it just means the app isn't (yet) signed with a paid code-signing certificate, which is common for small/free apps. Click **More info**, then **Run anyway**.
4. Click through the short installer. No settings to configure.
5. Launch **GW2 App** from the Start Menu.

---

## Connecting your API key

GW2 App doesn't use a username/password — it uses a personal **API key**, a long code you generate yourself on Guild Wars 2's official website. It's free, takes about a minute, and you can revoke it at any time without affecting your game account.

### Step 1 — Create a key on the official GW2 site

1. Go to **https://account.arena.net/applications** and log in with your Guild Wars 2 account.
2. Click **New Key**.
3. Give it a name you'll recognize later — e.g. `GW2 App`.
4. Tick **all** the permission checkboxes (`account`, `builds`, `characters`, `inventories`, `progression`, `pvp`, `tradingpost`, `unlocks`, `wallet`) so every page in the app has what it needs. None of these permissions let anything *change* your account — the Guild Wars 2 API is read-only for third-party apps like this one, no matter which boxes are checked.
5. Click **Create API Key**.
6. Copy the long string that appears (it looks like `1058D340-...-1058D340...`).

### Step 2 — Add it to GW2 App

1. Open GW2 App.
2. Click the **gear icon (⚙)** in the top-right corner to open **Settings**.
3. Paste the key into the **API key** field.
4. Click **Save**.

Head back to **Home** — your gold, wallet, and today's Wizard's Vault progress should show up within a few seconds. If nothing appears, see [Troubleshooting](#troubleshooting) below.

### Is my key safe?

- It's stored only on your PC, encrypted with Windows' own per-account encryption (DPAPI) — nobody else who uses the same computer can read it, even if they can see your files.
- It's sent only to the official `api.guildwars2.com` — GW2 App has no server of its own that the key ever passes through.
- The optional Community & LFG sign-up shares only your **account name** (to verify it's really you) once you choose to verify it there — never the key itself.
- You can revoke a key any time from **account.arena.net/applications** without touching your game account, and create a new one for GW2 App whenever you like.

---

## Updating

GW2 App checks for updates automatically each time it starts. You can also trigger a check manually: **Settings → Check for updates**. When an update is found, it downloads and applies itself, then restarts the app. You can also read what changed in each version any time from **Settings → Changelog**, without leaving the app.

---

## Troubleshooting

**"Cannot reach the local backend" / data won't load**
GW2 App runs a small local helper process on your own PC (never over the network — it only talks to `127.0.0.1`) to talk to the Guild Wars 2 API. If your antivirus quarantined it or blocked it from starting, allow `Gw2App.Wpf.exe` (and the `backend` folder next to it) through your antivirus/firewall and restart the app.

**"API Error: 401" or nothing loads on Home/Account/Bank**
Your API key is missing, mistyped, or was revoked. Go to **Settings**, re-paste your key from **account.arena.net/applications**, and save again.

**The Wizard's Vault / dailies say the Guild Wars 2 API is unavailable**
That's ArenaNet's servers, not GW2 App — the official API occasionally has brief outages. The app automatically retries every couple of minutes.

**Where is my data stored?**
Your API key and settings live in `%LocalAppData%\Gw2App` and `%LocalAppData%\Gw2App.Wpf`, tied to your Windows user account. There's currently no cloud backup — if you reinstall Windows or move to a new PC, you'll need to paste your API key in again (your build list and preferences won't carry over automatically yet).

---

## Feedback & bug reports

Found a bug, or something confusing? Please open an issue on this repo's [**Issues**](../../issues) page — screenshots and the Guild Wars 2 game mode you were in (e.g. "WvW", "fractals") help a lot.

---

Made with ❤️ by **CptJonas** (`CptJonas.9012`).
