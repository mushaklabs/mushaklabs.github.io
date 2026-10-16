# mushaklabs.com — company website

Static one-page site for Mushak Labs LLC. Zero external requests (system fonts,
local assets only) — no CDNs, no trackers.

## Publish it (GitHub Pages + custom domain)

### 1. Push to the repo
The site lives in the **`mushaklabs.github.io`** repo under the `mushaklabs`
organization (public — GitHub Pages on the free plan requires a public repo).
Push every file in this folder to the repo's `main` branch, keeping the same
structure (`index.html` and `CNAME` at the root).

### 2. Turn on Pages
1. Repo → **Settings → Pages**.
2. Source: **Deploy from a branch** → branch `main`, folder `/ (root)` → Save.
3. Under **Custom domain**, enter `mushaklabs.com` → Save.
4. Wait for DNS (step 3), then tick **Enforce HTTPS**.

### 3. Point the domain at GitHub (Porkbun)
In Porkbun → Domain Management → mushaklabs.com → DNS, **add** (do not delete
the existing iCloud mail TXT / MX / CNAME records):

| Type  | Host | Value |
|-------|------|-------|
| A     | @    | 185.199.108.153 |
| A     | @    | 185.199.109.153 |
| A     | @    | 185.199.110.153 |
| A     | @    | 185.199.111.153 |
| CNAME | www  | mushaklabs.github.io |

DNS can take minutes to a few hours. Once GitHub detects the domain, HTTPS is
issued automatically — then tick **Enforce HTTPS** in the Pages settings.

### 4. Later additions
- App Store links: each app card in `index.html` has a `TODO` comment marking
  where to paste the real App Store URL.
- To add a page (e.g. `/privacy`), just add `privacy/index.html`.
