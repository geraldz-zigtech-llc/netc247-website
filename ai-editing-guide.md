# AI Editing Guide for the networks | etc website

Use this guide when you ask an AI assistant to edit the site. Paste it into a chat assistant (ChatGPT, Claude, and others) before your request, or let a file-access tool (Claude Code, Cursor, and others) read it directly.

## Ground rules for the assistant

1. Make the smallest change that does the job. Do not restyle or reorganize pages unless asked.
2. Never remove content as a side effect of an edit. If a block is being removed, say so.
3. Before any find and replace, list every match first. A fix meant for one element can hit others.
4. Do not use hyphens or em dashes as punctuation in new copy. Use commas, colons, or semicolons.
5. Keep all core content (services, phone, address, license) in the static HTML. Do not load it with JavaScript.

## Accessibility and SEO guardrails to preserve

- Every `<img>` has an `alt` attribute. Decorative images use `alt=""`.
- Headings stay in order: one H1 per page, then H2, then H3, with no skipped levels.
- Every form field keeps its `<label for="...">` matched to the field `id`.
- Never remove focus outlines. Menu buttons keep `aria-expanded` and `aria-label`.
- `<html lang="en">` stays on every page, and the skip link `<a class="skip-link" href="#main">` stays.
- Keep titles in the form `Page Name | networks | etc`, under 60 characters.
- Each page keeps its canonical tag, viewport tag, Open Graph tags, and Twitter tags.

## Facts that appear in more than one place

Search the whole repo for every format before changing any of these.

- Phone: `407-476-1310` (visible text), `tel:+14074761310` (links), `+1-407-476-1310` (JSON-LD `"telephone"`). Appears in the header, mobile menu, footer, body links, contact page, support page, thank-you page, and JSON-LD.
- Address: `540 North State Road 434, Unit 123` on `contact.html` and in JSON-LD `"streetAddress"`.
- License: `EC13016153` in the footer of every page.
- Domain: `https://netc247.com` in canonical tags, Open Graph tags, JSON-LD, `sitemap.xml`, `robots.txt`, `llms.txt`, and the form `_next` value.
- Services: listed on Home, Services, the footer links, JSON-LD `knowsAbout`, the services FAQ JSON-LD, and `llms.txt`.

## Common edit cookbook (exact anchors)

**Change the phone number.** Search `407-476-1310`, `tel:+14074761310`, and `+1-407-476-1310`. Replace all three formats everywhere.

**Change the address.** On `contact.html`, search `540 North State Road 434, Unit 123<br>`. Also update `"streetAddress": "540 North State Road 434, Unit 123",` in the JSON-LD on each page, and `llms.txt`.

**Set the form recipient.** In `contact.html`, search `https://formsubmit.co/REPLACE_WITH_CLIENT_EMAIL` and replace only the email part. Do not change other form fields.

**Set Google Analytics.** On all six pages, replace both `G-XXXXXXXXXX` values (in the `gtag/js?id=` script and in `gtag('config', ...)`), then delete the TODO comment.

**Edit the footer license line.** Search `Certified Electrical Contractor License # EC13016153` and edit that one span on every page.

**Add a service bullet on Home.** In `index.html`, add a new `<li>` next to `<li>Managed IT</li>` through `<li>Cyber security</li>`. Then update the Services page, JSON-LD, and `llms.txt` to match.

**Change the remote support link.** In `support.html`, search `href="https://join.zoho.com"`.

**Add an image.** Use `<img src="img/name.jpg" alt="Describe the image" style="width:100%; height:auto;">`. The existing example is `img/bulb.jpeg` on `about.html`.

**Add the social share image.** Add a 1200 by 630 file named `img/og-default.jpg`. Pages already point to `https://netc247.com/img/og-default.jpg`.

**Go live (ZigTech only).** Remove `<meta name="robots" content="noindex, nofollow">` from index, about, services, support, and contact. Keep `<meta name="robots" content="noindex">` on `thank-you.html`.

## Pre-handoff verification checklist

- [ ] Every page still loads and the menu opens and closes by keyboard.
- [ ] One H1 per page, and heading levels do not skip.
- [ ] Every image has an `alt` attribute.
- [ ] Phone, address, and license match everywhere (search all formats).
- [ ] No leftover `REPLACE_WITH_CLIENT_EMAIL` or `G-XXXXXXXXXX` after launch.
- [ ] `sitemap.xml` lists only real pages, with no `#anchor` links and no `thank-you.html`.
- [ ] JSON-LD blocks are still valid (paste a page URL into the Schema Markup Validator).
- [ ] The contact form submits and lands on `thank-you.html`.

## Stop and contact ZigTech

Stop and email geraldz@zigtech-llc.com before touching any of these:

- DNS records, the `CNAME` file, or GitHub Pages domain settings
- The contact form, FormSubmit settings, or the `thank-you.html` redirect
- JSON-LD schema blocks
- `robots.txt`, `sitemap.xml`, or `llms.txt` structure
- License, certification, or compliance wording
- Moving or renaming any page (this breaks links and search listings)
