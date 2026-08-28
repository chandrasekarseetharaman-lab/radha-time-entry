# Punch — a plain-text time log

A single-page time-tracking app: log check-in/check-out sessions per day (multiple per day supported), and see your hours totalled by week and by month against your agreed standard hours, with overtime/undertime called out.

No build step, no backend — it's one HTML file that stores your data in the browser (`localStorage`). That makes it free and simple to host on GitHub Pages.

## Features

- Multiple check-in/check-out sessions per day (e.g. morning + afternoon shifts)
- Automatic daily, weekly (Mon–Sun) and monthly totals
- Set your standard hours/day and standard work days — the app computes your weekly and monthly agreed-hours target from that
- Overtime / on-target / under-target stamps on every week and month
- Edit or delete any logged day
- Export your data as a JSON backup file, and import it back in (useful before clearing browser data, or to move to another device/browser)

## Run it locally

Just open `index.html` in a browser — no install needed.

## Host it on GitHub Pages

1. Create a new GitHub repository (public, so Pages can serve it on the free tier), e.g. `time-log`.
2. Add `index.html` (and this `README.md`) to the repo — either via the GitHub web UI ("Add file → Upload files") or:
   ```bash
   git init
   git add index.html README.md
   git commit -m "Initial commit: Punch time log"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to "Deploy from a branch", branch `main`, folder `/ (root)`. Save.
5. GitHub will publish it at `https://<your-username>.github.io/<your-repo>/` within a minute or two.

## A note on your data

Your entries live only in the browser you use it in (`localStorage`), tied to that specific URL. That means:
- Clearing your browser's site data for that page will erase your log — use **Export backup** periodically.
- The same log won't automatically appear on a different browser or device — use **Export** on one and **Import** on the other to move it over.

If you'd rather have your data sync across devices automatically, that would need a small backend or a service like Firebase — happy to help wire that up if you want to take it further.
