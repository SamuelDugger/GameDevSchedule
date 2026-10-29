# Game Dev Rotation

A single-page course schedule. Open it on any device and install it on your phone's home screen.

## Files

- `index.html`: the whole app (course data, scheduling logic, styles).
- `manifest.webmanifest`, `sw.js`, `*.png`: make it installable and usable offline.

## Put it online (pick one)

### GitHub Pages

Run these from this folder. Free GitHub Pages needs a public repo. The page only lists courses and your progress, which is stored in your browser and never uploaded.

```bash
git init -b main
git add .
git commit -m "Game dev rotation"
gh repo create game-dev-rotation --public --source=. --push
gh api -X POST "repos/{owner}/{repo}/pages" -f "source[branch]=main" -f "source[path]=/"
```

The site appears at `https://<your-username>.github.io/game-dev-rotation/` after a minute or two.

### Netlify or Cloudflare Pages

Drag this folder onto [Netlify Drop](https://app.netlify.com/drop), or use Cloudflare Pages Direct Upload. Both need a free account, and both can host from a private repo if you connect one.

## On your phone

Open the site URL, then:

- Android Chrome: menu, Install app.
- iPhone Safari: Share, Add to Home Screen.

It opens full screen and works offline after the first visit.

## Keeping progress in sync

Progress is saved on each device. Tap **Copy sync link** and open that link on your other device to carry your progress over. Do it again after you make more progress.

## Changing the plan

Edit the `COURSES` list near the top of the script in `index.html` to add, remove or reorder items. Each course has a track, an order within the track, hours, and optional prerequisites (`after`). Bump `CACHE` in `sw.js` if a phone keeps showing an old copy.
