🎹 Piano Words: Cyber Arcade Ultimate

A retro pixel-art speed-typing game. Words fall down four "piano" lanes like tiles — type each word exactly before it hits the bottom. Clear 15 words to finish a level, then face faster tiles and longer words in a new colour-themed world.

Everything lives in a single HTML file: no build step, no dependencies, no server.

✨ Features
Piano-tile gameplay – 4 lanes, falling word tiles, instant destroy on exact match
Live match highlighting – matched letters turn green as you type
Combo system – each consecutive word raises your multiplier (10 × combo points)
Progressive difficulty – faster tiles and harder word banks each level
5 dynamic worlds – background and lane glow colour change every level (cyan → pink → green → gold → purple, then repeats)
Interactive 8-bit tutorial – a pixel-art robot instructor and a bouncing pointer guide you through your first word
Accounts – register / login with a username and password (stored locally)
Missions (Tasks) – earn 💎 gems for destroying tiles and reaching levels
Cyber Shop – spend gems on avatar skins (🥷 👾 🧙♂️ 🤖)
Profile & stats – best level, high score, total words cleared
Retro effects – pixel particle explosions, floating score text, screen shake, optional CRT scanlines
Synthesized 8-bit sound – all sound effects generated with the Web Audio API (no audio files)
Pause / Help / Exit controls during play
Mobile friendly – responsive layout with a viewport-fit=cover meta tag
🚀 Getting Started
Save the game as index.html.
Open it in any modern browser (Chrome, Edge, Firefox, Safari).
Register a username and password, then press 🚀 START MISSION.

The "Press Start 2P" pixel font loads from Google Fonts. Without an internet connection the game falls back to a system monospace font.

To host it online, drop the file on any static host (GitHub Pages, Netlify, Vercel, etc.).

🎮 How to Play
Look at the falling tiles.
Type the exact word into the input box at the bottom (case-insensitive). Tiles clear automatically when the word matches — no Enter needed.
If several tiles share the same word, the lowest one is destroyed first.
Destroy 15 tiles to clear the level.
If any tile touches the bottom, it's GAME OVER.
Difficulty by level
Level	Word bank	Examples
1	3-letter tech words	bit, ram, cpu
2	4-letter words	code, data, ping
3–4	6-letter words	matrix, kernel, socket
5+	Long words	firewall, algorithm, cybersecurity

Tile fall speed increases every level, and spawn intervals shrink from level 3 onward.

📜 Missions & Shop
Mission	Reward
Destroy 15 tiles	20 💎
Destroy 40 tiles	50 💎
Destroy 100 tiles	100 💎
Reach Level 2	40 💎
Reach Level 4	80 💎

New accounts start with 10 💎.

Skin	Price
Ninja 🥷	30 💎
Alien 👾	50 💎
Wizard 🧙♂️	80 💎
Mecha Unit 🤖	200 💎
🗂️ Project Structure
index.html   # HTML + CSS + JavaScript, all in one file
README.md

Inside index.html:

Section	Purpose
CSS :root variables	Colour theme, fonts, per-world lane glow
draw8BitCharacter()	Draws the robot instructor on canvas
Audio engine	playSfx() – square/triangle/sawtooth oscillator effects
WORD_BANKS, TASKS, SHOP_ITEMS	Easy-to-edit game data
Local store	loadStore() / saveStore() using localStorage
Particle system	Canvas pixel explosions and floating text
Gameplay engine	startMission, spawnTile, gameLoop, destroyTile
Tutorial	startFCTutorialMode, spawnTutorialTile
🛠️ Customisation
Add words: edit the arrays in WORD_BANKS.
Change tiles per level: replace the 15 in destroyTile and the HUD text.
Tune speed: adjust baseSpeed in spawnTile and spawnInterval in startMission.
New missions / skins: add entries to TASKS or SHOP_ITEMS.
New world colours: add a .world-N CSS class and update the modulo in updateWorldTheme.
⚠️ Known Limitations
Data is local only. Accounts, scores and gems are saved in the browser's localStorage, so they don't sync between devices and clear if site data is wiped.
Passwords are stored in plain text in localStorage. Don't reuse a real password; this is a demo-grade login, not real security.
Combo never resets on a missed word (only when a new mission starts).
"Words" on the Game Over screen shows the count for the current level, not the whole run.
Some sandboxed environments (e.g. embedded previews) block localStorage, in which case progress won't persist.
💡 Ideas for the Future
Combo reset on wrong input
Online leaderboard
Background music
Hashed passwords / real backend auth
More word categories and difficulty modes
📄 License

Add your preferred license here (e.g. MIT).
