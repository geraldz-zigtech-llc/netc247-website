# networks | etc website (netc247.com)

Static website for networks | etc, built and handed off by ZigTech LLC (SOW ZT-SOW-2026-06). Contact: geraldz@zigtech-llc.com

## Quick facts

- Business: networks | etc, 540 North State Road 434, Unit 123, Altamonte Springs, FL 32714
- Phone: 407-476-1310
- Canonical domain: https://netc247.com (no www)
- Hosting: GitHub Pages, deployed from the `main` branch, root folder
- Build step: none. Plain HTML, CSS, and JavaScript.
- Contact form: FormSubmit.co

## File structure

```
index.html            Home
about.html            About Us
services.html         Services
support.html          Support
contact.html          Contact (FormSubmit form)
thank-you.html        Form confirmation page (noindex, not in sitemap)
css/main.css          All site styles
js/main.js            Mobile menu and small behaviors
img/                  Images and favicon
robots.txt            Crawler rules
sitemap.xml           Pages for search engines
llms.txt              Plain summary for AI tools
ai-editing-guide.md   Guide for editing this site with an AI assistant
.github/master-checklist.md   Launch and handoff checklist
```

## How deployment works

Every push to `main` publishes automatically through GitHub Pages. Allow 1 to 2 minutes for the build, and up to 10 minutes for the CDN cache to refresh.

## Simple manual edits

1. Open the file in GitHub (pencil icon) or a text editor.
2. Change the text between the tags. Do not remove tags or attributes.
3. Commit to `main`, wait for the build, and reload the page.

If a fact such as the phone number appears in several places, change every place. See `ai-editing-guide.md` for the list.

## Do not touch without ZigTech

- DNS records and the `CNAME` file
- FormSubmit settings (the `action`, `_next`, `_autoresponse`, and `_honey` fields in `contact.html`)
- Structure of `robots.txt`, `sitemap.xml`, and `llms.txt`
- JSON-LD schema blocks (`<script type="application/ld+json">`)
- License, certification, or compliance wording

## Launch status

See `.github/master-checklist.md` for the current state. Until cutover, every content page carries `noindex, nofollow` on purpose, so the site stays out of search results while it is being reviewed.
