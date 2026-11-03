# Future Living Report 2026

Landing page for the third edition of the betterhomes Future Living Report — the annual
survey of Dubai residents (1,714 respondents, 63 nationalities, fieldwork 17 June – 19 July 2026).

## Files

- `future-living-report-2026.html` — the full page. Self-contained: inline CSS and JS,
  hero image embedded as a data URI, Fraunces + DM Sans from Google Fonts.

## How the page is ordered

The page is built to read as a product, not as an article:

1. **Hero** — edition mark, title, download and film CTAs, and a credentials rail
   (respondents, nationalities, fieldwork, location, read time).
2. **Opening** — series mark (No. 03), the lead, and the three key takeaways.
3. **2026 at a glance** — the six headline numbers with year-on-year deltas, on navy.
4. **Chapter nav** — sticky, with scroll spy.
5. **Four chapters** — confidence, putting down roots, global standing, policy.
   Each has a standfirst, a chart, a "what it means" note and a download CTA.
6. **More from the survey** — the eight supporting findings.
7. **The film** — click-to-load YouTube embed.
8. **The report** — cover, what's inside, and the lead form with an edition selector.
9. **FAQ**, then **methodology** (deliberately near the end, as credibility rather than preamble).
10. **Previous editions and market reports**, **articles from this report**, footer.

## Before going live

Replace these placeholders:

| Placeholder | Where |
| --- | --- |
| `[Author name]`, `[AUTHOR PAGE URL]` | byline and JSON-LD |
| `[DD Month YYYY]`, `[YYYY-MM-DD]` | published / updated dates and JSON-LD |
| `[X] min` | read time in the hero rail and film copy |
| `[YOUTUBE VIDEO ID]`, `[m:ss]`, `[PT#M#S]`, `[VIDEO TRANSCRIPT URL]`, `[VIDEO THUMBNAIL URL]` | film section and JSON-LD |
| `[2026 PDF URL]`, `[2025 PDF URL]`, `[2024 PDF URL]`, `[PDF URL]` | `PDFS` map in the script, and JSON-LD |
| `[LEAD ENDPOINT]` | the commented-out `fetch` in the form submit handler |
| `[HERO IMAGE URL]`, `[LOGO URL]` | Open Graph and JSON-LD |
| `[ARTICLE URL]`, `[Author]`, `[date]` | the six cards in "Articles from this report" |

The form currently validates, fires a `report_download` dataLayer event and shows the success
state. Wire the `fetch` to the CRM before launch.
