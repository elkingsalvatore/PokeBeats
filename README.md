# 🎵⚡ PokéBeats

> **Descubrí qué Pokémon representa tu música de este mes.**  
> Connect your Spotify and let your listening habits build your perfect Pokémon team.

![PokéBeats](https://img.shields.io/badge/PokéBeats-v3.0-1DB954?style=for-the-badge&logo=spotify&logoColor=white)
![HTML](https://img.shields.io/badge/HTML-Single%20File-orange?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

---

## ✨ Features

- 🎵 Analyzes your **Spotify top artists & tracks** from the past month
- ⚡ Builds a **team of 6 Pokémon** based on your musical genres
- 🏅 Awards you a **unique medal** based on your music vibe
- 📅 **Team history** — compare teams month to month
- ⚔️ **Battle mode** — fight your current team vs a past one
- 🖼️ **Share as image** — download your team or top songs as a 9:16 card
- ☀️🌙 **Dark / Light mode** toggle
- 🌐 **Spanish / English** support
- 📱 Fully mobile-responsive

---

## 🚀 How to use (for everyone — no server needed)

PokéBeats is a **single HTML file** that runs entirely in the browser.  
Each user connects with their **own free Spotify Developer app** — no shared API keys, no restrictions.

### Step 1 — Get your free Spotify Client ID

1. Go to [developer.spotify.com/dashboard](https://developer.spotify.com/dashboard) and log in with your Spotify account
2. Click **"Create app"**
3. Fill in:
   - **App name:** PokéBeats (or anything you want)
   - **App description:** Personal music team generator
   - **Redirect URI:** The URL where you'll open the file (see below)
   - **APIs used:** Web API
4. Click **Save**, then copy your **Client ID** from the app settings

### Step 2 — Set your Redirect URI

The Redirect URI must match **exactly** where you open the app:

| How you open it | Redirect URI to use |
|---|---|
| GitHub Pages | `https://YOUR-USERNAME.github.io/pokebeats/` |
| Local file | `http://localhost:PORT` (use a local server, see below) |
| Custom domain | `https://your-domain.com/` |

> ⚠️ `file://` URLs don't work with OAuth — you need to serve it via HTTP.

### Step 3 — Open PokéBeats and paste your Client ID

When you open PokéBeats for the first time, it will ask for your Client ID.  
Paste it in → it's saved locally in your browser. You only do this **once per device**.

---

## 🌐 Deploy on GitHub Pages (free hosting, 2 minutes)

1. Fork or upload this repo to your GitHub account
2. Go to **Settings → Pages**
3. Set source: **Deploy from branch `main`**, folder `/ (root)`
4. Your app will be live at `https://YOUR-USERNAME.github.io/pokebeats/`
5. Use that URL as your Redirect URI in the Spotify Dashboard

---

## 💻 Run locally

```bash
# Python (easiest)
python3 -m http.server 8080

# Node.js
npx serve .

# Then open: http://localhost:8080
# Use http://localhost:8080 as your Redirect URI in Spotify
```

---

## 🛠️ Tech stack

| Layer | Tech |
|---|---|
| Frontend | Vanilla HTML + CSS + JS (single file, no framework) |
| Auth | Spotify OAuth 2.0 with PKCE (no backend needed) |
| Music data | [Spotify Web API](https://developer.spotify.com/documentation/web-api) |
| Pokémon data | [PokéAPI](https://pokeapi.co) |
| Image export | [html2canvas](https://html2canvas.hertzen.com) |
| Fonts | Google Fonts — Nunito |

---

## 🎮 How team generation works

1. Fetches your **top 50 artists** from the last month
2. Analyzes their genres and maps them to **Pokémon types** (e.g. Hip-Hop → Fighting, Electronic → Electric, Reggaetón → Fire)
3. Selects **6 unique type slots** based on your genre frequency
4. Randomly picks a Pokémon from each type pool (Pokémon #1–900)
5. Awards a **medal** based on your dominant type

### Genre → Type mapping

| Genre | Pokémon Type |
|---|---|
| Hip-Hop / Rap | ⚔️ Fighting |
| Electronic / EDM | ⚡ Electric |
| Reggaetón / Latin | 🔥 Fire |
| Metal | 🔩 Steel |
| Indie / Alternative | ☠️ Poison |
| Jazz / Blues | 💧 Water |
| K-Pop / J-Pop | 🌸 Fairy |
| Classical / Orchestra | 🐉 Dragon |
| Rock | 🪨 Rock |
| Folk / Country | 🌍 Ground |
| R&B / Soul / Neo Soul | 🔮 Psychic |
| Dark / Ghost vibes | 👻 Ghost / Dark |
| Pop | ⭐ Normal |
| Ambient / Lo-fi | 🌬️ Flying |

---

## ☕ Support

If you enjoy PokéBeats, you can support its development:

[![Ko-fi](https://img.shields.io/badge/Ko--fi-Support-ff5f5b?style=for-the-badge&logo=ko-fi&logoColor=white)](https://ko-fi.com/elkingsalvatore)

---

## 📄 License

MIT — free to use, fork, modify and share.  
Built with ❤️ by [@elkingsalvatore](https://ko-fi.com/elkingsalvatore)

---

## 🙏 Credits

- [Spotify Web API](https://developer.spotify.com) — music data
- [PokéAPI](https://pokeapi.co) — Pokémon data  
- [html2canvas](https://html2canvas.hertzen.com) — image export
- Pokémon © Nintendo / Game Freak (this is a fan project, not affiliated)
