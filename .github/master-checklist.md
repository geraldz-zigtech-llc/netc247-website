# Master Checklist: networks | etc (netc247.com)

Source of truth for the build and handoff. SOW ZT-SOW-2026-06 Rev. 1 (signed by Brian Velez 10/13/2026). Update in place; mark each item DONE with the final content used.

Status as of 10/16/2026: site is LIVE at https://netc247.com with HTTPS enforced.

## Build

- [x] DONE: Demo approved by Brian Velez (Oct 6, 2026)
- [x] DONE: Site moved to standalone repo; repo now owned by GitHub user `netc247` (netc247/netc247-website, public)
- [x] DONE: Hero alignment and headline line breaks applied on Home, About, Services, Support, Contact
- [x] DONE: `thank-you.html` built from site template, noindex, excluded from sitemap, Disallowed in robots.txt (separate from FormSubmit activation)
- [x] DONE: `robots.txt` (AI crawler groups, thank-you Disallow, Sitemap line); AI crawler choice A (allow all) confirmed by Brian 10/16/2026
- [x] DONE: `sitemap.xml` (5 pages, no anchors, no thank-you)
- [x] DONE: `llms.txt`
- [x] DONE: `README.md`
- [x] DONE: `ai-editing-guide.md`
- [x] DONE: `.github/master-checklist.md` (this file)
- [x] DONE: `img/og-default.jpg` (1200 by 630, dark background, red accent, logo, tagline, domain and phone)

## Approvals and paperwork

- [x] DONE: SOW ZT-SOW-2026-06 Rev. 1 signed by Brian Velez 10/13/2026 ($500 total: core build $300, handoff package included, Analytics setup $100, DNS changes $100)
- [x] DONE: Launch Approval signed 10/15/2026 (content final, license number EC13016153 confirmed, AI crawler option A, FormSubmit handling, GitHub ownership steps)
- [x] DONE: DNS Change Approval signed 10/15/2026; www target `netc247.github.io` confirmed by Brian in writing 10/15/2026
- [x] DONE: dashboard and dashboard2 CNAME deletion approved by Brian on the 10/16/2026 call; written confirmation sent in the recap email 10/16/2026
- [x] DONE: Invoice ZT-SOW-2026-06 for $500.00 sent via QuickBooks 10/16/2026, Net 15, due 10/31/2026
- [ ] Invoice paid (confirm online payment works on the QuickBooks account; add billing address for Network ETC if wanted)

## Cutover (completed 10/16/2026)

- [x] DONE: Brian granted GoDaddy delegate access (10/9/2026)
- [x] DONE: `CNAME` file added at repo root containing `netc247.com` (commit 0225422)
- [x] DONE: DNS at GoDaddy: A records for `@` set to 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153 (the .109.153 record has a 600 second TTL, others 1 Hour); CNAME `www` set to `netc247.github.io.`; old A 199.34.228.65 removed. Rollback values: A @ 199.34.228.65, CNAME www netc247.com. AAAA records were not added (optional).
- [x] DONE: dashboard and dashboard2 CNAME records deleted (rollback values: dashboard.systemmonitor.us. and dashboard2systemmonitor.us.)
- [x] DONE: GitHub Pages custom domain reads exactly `netc247.com`; DNS check successful; Enforce HTTPS checked
- [x] DONE: Verified live: https://netc247.com returns 200, http redirects 301 to https, www redirects 301 to apex; title is "networks | etc | Orlando Managed IT, Security & Infrastructure"; no noindex on content pages
- [x] DONE: Removed `<meta name="robots" content="noindex, nofollow">` from the 5 content pages (kept noindex on thank-you)

## Forms and Analytics

- [x] DONE: Client email for FormSubmit set to contactform@netc247.com
- [x] DONE: FormSubmit activation (separate from the redirect): live form submitted, "Activate your form" link clicked by Brian 10/16/2026, test message delivered
- [x] DONE: Form redirect verified end to end: submit goes to https://netc247.com/thank-you.html
- [x] DONE: GA4 Measurement ID `G-6P4TZNJFPE` installed on all 6 pages; Realtime confirmed 10/16/2026

## Search and discoverability

- [x] DONE: Google Search Console Domain property for netc247.com already verified (via existing Google verification CNAME; no TXT record was needed)
- [x] DONE: `https://netc247.com/sitemap.xml` submitted in Search Console; status Success, 5 pages discovered
- [ ] Request Indexing on key pages (home, about, services, support, contact) via URL Inspection
- [ ] Bing Webmaster Tools: import from Search Console; enable IndexNow or submit sitemap
- [ ] Old sitemap `http://www.netc247.com/sitemap.xml` (31 pages) in Search Console: Brian must remove it from his account (submitted from another account)
- [ ] Gather where else the business appears online (Google Business Profile, directories, chamber, reviews, social); run NAP check against: networks | etc, 540 North State Road 434, Unit 123, Altamonte Springs, FL 32714, 407-476-1310
- [ ] Add `sameAs` links to JSON-LD once third-party profiles are known

## Open items

- [ ] ZigTech GoDaddy delegate access still active; Brian to remove it when ready (Account Settings, Delegate Access)
- [ ] Repo "About" description still reads "Preview build, netc247.com refresh (not production)"; Brian or collaborator with access to update
- [ ] `thank-you.html` heading uses an em dash; replace with a comma or colon in a follow up commit
- [ ] Remove `netc247-preview/` from geraldz-zigtech-llc/website
- [ ] Optional for Brian: add SPF, DKIM and DMARC records (none exist); GoDaddy ownership protection is off on three of his domains
- [ ] Post launch changes are $50 each, requested by email and confirmed before work, per the SOW
