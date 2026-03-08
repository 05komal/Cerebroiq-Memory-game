# CerebroIQ — Word & Memory Challenge Suite

> A browser-based game suite featuring a word guessing game and a flash memory challenge, built with pure HTML, CSS, and JavaScript. No frameworks. No installs. Just open and play.

---

## Live Demo

>[https://cerebroiq-memory-game.vercel.app/]

---

## Preview

| Login | Hub | WordQuest | MNEMO |
|-------|-----|-----------|-------|
| Sign in / Register | Pick your game | Guess the word | Flash memory |

---

## Games

### WordQuest
A word guessing game with **200 words** across **10 categories**.

- Guess the hidden word using a hint
- **5 attempts** before the answer is automatically revealed
- Use **Reveal Letter**, **Word Length**, or **Skip** as power-ups
- On-screen keyboard + floating category-themed particles
- **10 points** per correct answer
- Categories: Geography, History, Science, Music, Sports, Tech, Nature, Games, General, All

### MNEMO
A flash memory game that tests how well you can recall sequences.

- A sequence of items flashes on screen for a few seconds
- It disappears — type it back from memory in the correct order
- **On-screen symbol keyboard** for easy input in Symbols & Chaos modes
- **10 points** for perfect recall, **5 points** for partial
- 5 modes: Digits, Letters, Symbols, Words, Chaos
- 4 difficulties: Easy (4 items / 5s) → Expert (10 items / 2.5s)
- 3 lives before game over

---

## Features

- 🔐 **Login / Register system** — per-user scores saved in `localStorage`
- 🛡️ **Auth-gated pages** — hub and games redirect to login if not signed in
- 📊 **Live score tracking** — score, streak, accuracy, and best scores per category
- 🌊 **Category-themed floating particles** — leaves for Geography, notes for Music, bugs for Nature, etc.
- 🎨 **10 dynamic themes** — each category has its own color palette and background
- 📱 **Responsive design** — works on desktop and mobile
- ⚡ **No dependencies** — pure HTML/CSS/JS, no npm, no build step

---

## File Structure

```
cerebroiq/
├── login.html           ← Start here — Sign in / Register
├── index.html           ← Game hub
├── lexon-complete.html  ← WordQuest word guessing game
├── mnemo-memory.html    ← MNEMO flash memory game
└── README.md
```

---

## Running Locally

### Option 1 — VS Code Live Server (Recommended)
1. Install the **Live Server** extension in VS Code
2. Right-click `login.html` → **Open with Live Server**
3. Browser opens automatically at `http://127.0.0.1:5500/login.html`

### Option 2 — Python
```bash
python -m http.server 8080
```
Then open: [http://localhost:8080/login.html](http://localhost:8080/login.html)

### Option 3 — Direct open
Double-click `login.html` in File Explorer *(most features work)*

> ⚠️ Always open `login.html` first — other pages are auth-gated and will redirect if you open them directly without logging in.

---

## Deployment

### Vercel (Recommended)
1. Push this repo to GitHub
2. Go to [vercel.com](https://vercel.com) → **Add New Project**
3. Import your GitHub repo
4. Leave all settings default → click **Deploy**
5. Live in ~30 seconds 

### GitHub Pages
1. Go to your repo → **Settings** → **Pages**
2. Branch: `main` → Folder: `/root` → **Save**
3. Live at: `https://YOUR_USERNAME.github.io/cerebroiq/login.html`

---

## Tech Stack

| Technology | Usage |
|-----------|-------|
| HTML5 | Structure & game screens |
| CSS3 | Themes, animations, floating particles |
| Vanilla JavaScript | Game logic, auth, localStorage |
| Google Fonts | Orbitron, Space Mono, JetBrains Mono |
| Web Audio API | (Previously used for music — removed) |
| localStorage | User accounts & scores |
| sessionStorage | Login session per tab |

---

## How Auth Works

- Passwords are **hashed** before storing (simple hash function)
- Sessions use `sessionStorage` — each browser tab manages its own session
- All data stays **100% local** in the browser — nothing is sent to any server
- Closing the browser clears the session (you'll need to log in again)

---

## Scoring

| Game | Correct | Partial | Miss |
|------|---------|---------|------|
| WordQuest | +10 pts | — | 0 pts |
| MNEMO | +10 pts | +5 pts | 0 pts |

- Scores are saved **per user** and **per category**
- Best score and best streak are tracked across all sessions

---

## Future Improvements

- [ ] Leaderboard between users
- [ ] Sound effects and animations on correct answers
- [ ] Timer mode for WordQuest
- [ ] More word categories (Movies, Science Fiction, Food)
- [ ] Dark/Light theme toggle
- [ ] Mobile touch gestures for MNEMO

---

## Author

Built as a personal project — feel free to fork, modify, and deploy your own version!

---

## License

This project is open source and available under the [Apache License 2.0](LICENSE).

```
Copyright 2024 CerebroIQ

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
