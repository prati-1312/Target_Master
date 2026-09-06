# Target Master — The Probability Challenge

Single-file HTML/CSS/JS binomial-distribution game (Group 4, Business Statistics project).

## What's actually in this repo
- `index.html` — the entire game (markup, styles, and script are all inline). No build step, no external JS libraries, no API calls. It only touches `localStorage` for the classroom leaderboard.
- `package.json` — added so Hostinger's Node.js panel can detect and run the project.
- `.gitignore` — keeps `node_modules` out of the repo.

## Deploying on Hostinger — pick ONE path

### Path A: Static hosting (recommended, simplest)
This game needs zero server logic, so this is the right choice:
1. In hPanel, go to **Websites → Manage → File Manager** (or use Git deploy) and point the site's document root at the folder containing `index.html`.
2. If you're using Hostinger's **Git** feature, just connect this repo — no build command needed, no output directory needed (or set output directory to `/` and leave build command blank).
3. Done — visiting the domain loads `index.html` directly.

### Path B: Node.js app hosting
Only needed if Hostinger's dashboard specifically requires a running Node process (some panels insist on this even for static content):
1. Run `npm install` to pull in `serve` (a tiny static file server).
2. Set the **Startup file** to `npm start` (or `node_modules/.bin/serve`), which runs:
   ```
   serve -s . -l $PORT
   ```
3. Hostinger will inject its own `PORT` env variable — the script already respects that.

You don't need both paths — Path A is simpler and is what this kind of single-file game is built for. Use Path B only if your Hostinger plan's Node.js setup insists on a start command before it will deploy.
