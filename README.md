<div align="center">

# 🎮 CS2 Console Commands Cheat Sheet

One-click copy · 11 categories · Bilingual (EN / 中文) · Zero-dependency single file

**English** · [简体中文](README.zh-CN.md)

</div>

A pure static **Counter-Strike 2 console command cheat sheet**. 100 frequently used commands organised into 11 categories — click to copy, paste into the in-game console, done. The whole project is a single `index.html`: no framework, no build step, no external dependencies.

## ✨ Features

- 📋 **One-click copy** — every command has a copy button with visual feedback
- 🗂 **11 categories** — from practice/cheats and knife models to the pet chicken
- 🔗 **SteamID → `connect`** — paste any text containing `[A:1:xxxx:xxxxx](xxxxxxxxxx)` (e.g. `status` output) and get a ready-to-use `connect` command
- 🌐 **Bilingual UI** — switch between 中文 / EN in the top-right corner; defaults to your browser language and remembers your choice
- 🎨 **Neumorphic UI** — Gemini-style light neumorphism, particle background and liquid-crystal pill buttons
- 📱 **Responsive** — works on desktop and mobile
- 🧩 **Zero dependencies** — plain HTML / CSS / JavaScript in one file

## 🗂 Categories

| Category | Count | What's inside |
| --- | :---: | --- |
| ⚡ Common | 7 | `status`, `bot_kick`, `mp_restartgame`, `sv_cheats`, `clear`, silencer mode |
| Practice & cheats | 8 | God mode, noclip, infinite ammo, grenade trajectory, bullet impacts |
| Knife models | 20 | Switch between knife skins |
| Map switching | 20 | Quick load of practice / competitive maps |
| Bot management | 8 | Add, kick, difficulty, freeze bots |
| Match control | 13 | Restart, freeze time, round length, overtime, friendly fire, C4 timer, respawn |
| Economy & items | 7 | Buy time, buy anywhere, money limit, drop settings |
| Server & connection | 2 | `status` for server / player info, `disconnect` to leave the server |
| Display & HUD | 2 | `cl_draw_only_deathnotices` — keep kill feed only, hide the rest of the HUD |
| Voice | 6 | All-talk, dead talk, voice toggles, mute enemy team |
| Other utilities | 3 | `kill`, `clear`, `kick` |
| Pet chicken | 4 | `cl_ent_scale` to resize the chicken |

> Commands change between game updates; a few may not work in every version or on every server.

## 🚀 Deploy to GitHub Pages

1. Create a new GitHub repository and upload `index.html` (plus `README.md` and `README.zh-CN.md` if you like) to the root
2. Open `Settings → Pages`
3. Set `Source` to `Deploy from a branch`, choose branch `main` and folder `/ (root)`, then save
4. Wait a minute, then visit `https://<your-username>.github.io/<repo-name>/`

**Local preview**: just double-click `index.html`, or run

```bash
python -m http.server 8080
# open http://localhost:8080
```

**Enable the in-game console**: `Settings → Game → Enable Developer Console → Yes`, then press `~` in game.

## 🌐 Language switching

| Method | Behaviour |
| --- | --- |
| URL parameter | `?lang=en` forces English, `?lang=zh` forces Chinese — handy for sharing with players of either language |
| Top-right buttons | Click 中文 / EN; the choice is stored in `localStorage` (key `cs2_lang`) |
| Default | Follows the browser language (`navigator.language`) |

## ➕ Add your own command

Append a `cmd-row` block inside the matching `<div class="tab-content" id="...">`:

```html
<div class="cmd-row">
    <div class="cmd-text-wrapper">
        <code class="cmd-code">sv_cheats 1</code>
        <span class="comment">// 开启作弊指令</span>
    </div>
    <button class="copy-btn" data-cmd="sv_cheats 1">复制</button>
</div>
```

- `data-cmd` is what actually gets copied — keep it identical to the text inside `<code>`
- To show an English comment in English mode, add the Chinese comment as a key in the page's `DICT` map, e.g. `"开启作弊指令": "Enable cheats"`
- A new category needs both a `tab-btn` and a matching `tab-content` block

## ⚠️ Notes

- Commands marked "local / bot match only" usually require `sv_cheats 1` and do nothing on official matchmaking servers
- Using cheat commands on official servers may result in a VAC ban — use your own judgement
- Commands were collected and tested against the current CS2 build and may break after updates
- This project is not affiliated with Valve or Counter-Strike in any way

## 📄 License

MIT — free to use, modify and redistribute.
