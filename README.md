# ml4spatialbio 2026 workshop website

Static site (plain HTML/CSS, no build step) for the NeurIPS 2026 workshop
"Machine Learning for Spatially Resolved High-dimensional Biology".

## Files

- `index.html` — home page (overview, dates, speakers, schedule, organizers, venue)
- `cfp.html` — call for papers (topics, submission format, dates, OpenReview link placeholder)
- `style.css` — shared styling
- `.nojekyll` — tells GitHub Pages to skip the Jekyll build step (not needed for plain HTML)

## Publish it on GitHub Pages

1. Create a new **public** repository on GitHub, e.g. `ml4spatialbio2026` (Settings you already chose: personal account, no build tooling).
2. From this folder, initialize and push:

   ```bash
   git init
   git add .
   git commit -m "Initial workshop website"
   git branch -M main
   git remote add origin https://github.com/bbboylux/ml4spatialbio2026.git
   git push -u origin main
   ```

3. On GitHub: repo **Settings → Pages** → under "Build and deployment", set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`. Save.
4. Your site will be live within a minute or two at:

   `https://bbboylux.github.io/ml4spatialbio2026/`

## Updating content later

- **OpenReview submission link**: once your venue is live, edit the `href="#"` on the "OpenReview submission link" button in `cfp.html` to the real URL.
- **Program Committee**: currently says "to be announced" on purpose (the real list wasn't finalized when this was built — see the accepted proposal for the preliminary/prospective names). Replace the placeholder note in both `index.html` and `cfp.html` with a `.grid.cols-2` of `.card` blocks (copy the pattern used for Organizers) once the PC is confirmed.
- **Workshop date/room**: replace the `<span class="badge tbd">Date TBD</span>` badges once NeurIPS assigns your slot.
- **Speaker photos**: add an `images/` folder and `<img>` tags inside each speaker `.card` if you want photos.
- Every push to `main` updates the live site automatically — no rebuild needed.

## Local preview

Just open `index.html` in a browser, or run a tiny local server from this folder:

```bash
python -m http.server 8000
```

then visit `http://localhost:8000`.
