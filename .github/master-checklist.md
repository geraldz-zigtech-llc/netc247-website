# Master Checklist: networks | etc (netc247.com)

Source of truth for the build and handoff. SOW ZT-SOW-2026-06. Update in place; mark each item DONE with the final content used.

## Build

- [x] DONE: Demo approved by Brian Velez (Oct 6, 2026)
- [x] DONE: Site moved to standalone repo geraldz-zigtech-llc/netc247-website
- [x] DONE: Hero alignment and headline line breaks applied on Home, About, Services, Support, Contact
- [x] DONE: `thank-you.html` built from site template, noindex, excluded from sitemap, Disallowed in robots.txt (separate from FormSubmit activation)
- [x] DONE: `robots.txt` (AI crawler groups, thank-you Disallow, Sitemap line)
- [x] DONE: `sitemap.xml` (5 pages, no anchors, no thank-you)
- [x] DONE: `llms.txt`
- [x] DONE: `README.md`
- [x] DONE: `ai-editing-guide.md`
- [x] DONE: `.github/master-checklist.md` (this file)

## Open items before cutover

- [ ] Client email for FormSubmit: replace `REPLACE_WITH_CLIENT_EMAIL` in `contact.html` form action
- [ ] FormSubmit activation (separate from the redirect):
  1. Submit the live form once with any test name and message.
  2. Check the recipient inbox and spam or junk for "Activate your form" from FormSubmit.
  3. Click the confirmation link.
  4. Confirm later submissions are delivered normally.
- [ ] GA4 Measurement ID: replace both `G-XXXXXXXXXX` on all 6 pages, remove TODO comment
- [x] DONE: `img/og-default.jpg` (1200 by 630, dark background, red accent, logo, tagline, domain and phone) added
- [ ] Gather where else the business appears online (Google Business Profile, directories, chamber, reviews, social); run NAP check against: networks | etc, 540 North State Road 434, Unit 123, Altamonte Springs, FL 32714, 407-476-1310
- [ ] Add `sameAs` links to JSON-LD once third-party profiles are known

## Cutover

- [ ] Brian provides DNS access at his current host
- [ ] Add `CNAME` file at repo root containing `netc247.com`
- [ ] DNS: A records for `@` to 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153 (optional AAAA 2606:50c0:8000::153 through 2606:50c0:8003::153); CNAME `www` to the GitHub Pages host
- [ ] GitHub Pages custom domain reads exactly `netc247.com`; Enforce HTTPS checked after DNS check passes
- [ ] Verify live site by title and heading, not just that DNS resolves
- [ ] Remove `<meta name="robots" content="noindex, nofollow">` from the 5 content pages (keep noindex on thank-you)
- [ ] Re-test form end to end on the live domain

## After launch

- [ ] Google Search Console Domain property; submit `sitemap.xml`; Request Indexing on key pages
- [ ] Bing Webmaster Tools: import from Search Console; enable IndexNow or submit sitemap
- [ ] Transfer repo ownership to GitHub user `netc247`
- [ ] Remove `netc247-preview/` from geraldz-zigtech-llc/website
