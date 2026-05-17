# marhs.me — Fix & Improvement Tasks

## Critical (site is broken for normal visitors)

- [x] **Fix TLS certificate.** Apex A records were pointing at the deprecated `192.30.252.x` block; updated to the current GitHub Pages apex IPs (`185.199.108–111.153`) plus AAAA records. DNS check passed and Let's Encrypt issued the cert; Enforce HTTPS is on.
- [x] **Fix mixed content.** Removed the entire GA block (both the `http://` external script and the inline UA snippet), which also cleared the dead-analytics task.

## Code hygiene

- [x] **Remove dead analytics.** Dropped along with the mixed-content fix above.
- [ ] **Fix the "sotfware" typo** → "software engineer".
- [ ] **Fix domain drift.** The HTML still references `marhs.de`:
  - The `<!-- saved from url=(0016)http://marhs.de/ -->` comment (artifact of a browser "Save As").
  - The GA `create` call uses `'marhs.de'` as the tracker domain.
  - Decide whether `marhs.de` should redirect to `marhs.me` (or vice versa) and make one canonical.
- [ ] **Close the unclosed `<p>`** at the end of the bio paragraph.
- [ ] **Clean up the `./files/` asset layout.** The directory structure looks like a Chrome "Save Page As" dump (`./files/style.css`, `./files/js.js`, `./files/css`). Rename to something intentional like `assets/` and drop anything unused.
- [ ] **Audit `./files/js.js`** — confirm it's actually doing something. If not, delete it.

## Content / design improvements

- [ ] **Rewrite the bio.** Replace the buzzword list ("data science, data engineering, machine learning, and artificial intelligence") with one concrete sentence about what you actually build or are working on right now. Memorable beats comprehensive on a landing page.
- [ ] **Add a favicon.** None is set currently.
- [ ] **Add basic SEO meta tags:** `<meta name="description">`, Open Graph (`og:title`, `og:description`, `og:image`), and Twitter card tags — so links shared in chat/social render with a preview.
- [ ] **Set `lang` on `<html>`** (e.g. `<html lang="en">`) for accessibility and SEO.
- [ ] **Verify the CV link still works.** It points to `github.com/marhs/marhs.github.io/raw/master/files/cv.pdf` — check the file exists and is current.
- [ ] **Add `rel="noopener"` (and consider `rel="me"`)** on external profile links.
- [ ] **Consider dropping analytics altogether.** For a one-page personal site, it's rarely worth the privacy cost or the cookie-banner overhead.

## Nice-to-haves

- [ ] Add a short "what I'm doing now" line or link to a `/now` page.
- [ ] Link to a blog, recent talk, or pinned project so the page has a "next click."
- [ ] Check mobile rendering — confirm `bg_photo` and `card` layout don't break on narrow viewports.
- [ ] Run the page through Lighthouse and fix any easy accessibility/perf wins.
