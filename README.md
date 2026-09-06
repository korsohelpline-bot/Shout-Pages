# Shout In & Out — website

Flat, static multi-page site. All 11 pages now share one navbar (`swio-navbar`)
with the correct "active" state per page, and every internal link between
pages has been fixed to point at real files.

## Pages

| File | Page |
|---|---|
| index.html | Home |
| about.html | About |
| service.html | Services (overview) |
| creative-content-production.html | Service → Creative & Content Production |
| digital-marketing-growth.html | Service → Digital Marketing & Growth |
| technology-automation.html | Service → Technology & Automation |
| performance-marketing.html | Service → Performance Marketing |
| our-work.html | Our Work |
| team.html | Team |
| blog.html | Blog |
| contact.html | Contact |

## Deploy via GitHub + Vercel

1. Create a new GitHub repo and push these files to the root of the repo
   (no subfolder — `index.html` must sit at the repo root):
   ```
   git init
   git add .
   git commit -m "Launch site"
   git branch -M main
   git remote add origin https://github.com/<you>/<repo>.git
   git push -u origin main
   ```
2. Go to vercel.com → **Add New Project** → import that GitHub repo.
3. Framework preset: choose **Other** (it's a static site, no build step needed).
   Leave the Build Command empty and set the Output Directory to `.` (root).
4. Deploy. Vercel will pick up `vercel.json` automatically, which enables
   clean URLs (`/about` instead of `/about.html`) — the links in the pages
   already use the `.html` filenames and will still resolve correctly either way.
5. Add your custom domain under Project → Settings → Domains whenever you're ready.

Every future push to `main` auto-redeploys.

## Note on the old template placeholder links

The leftover `/service-detail/...`, `/portfolio-detail/...`, `/service/<slug>`,
and `/work/...` / `/works` links (in about.html, our-work.html,
performance-marketing.html, and service.html) now all point to `contact.html`,
since none of them had a real destination page in this project.
