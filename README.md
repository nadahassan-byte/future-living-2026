# Future Living Report 2026

Landing page for the third edition of the betterhomes Future Living Report — the annual
survey of Dubai residents (1,714 respondents, 63 nationalities, fieldwork 17 June – 19 July 2026).

## Files

- `future-living-report-2026.html` — the full page. Self-contained: inline CSS and JS,
  hero image embedded as a data URI, Cormorant Garamond + Jost from Google Fonts.

## Components

The page is built only from components already in the betterhomes page kit, plus the three
signed-off blocks. Nothing else is invented.

Existing components reused as-is:

| Component | Class | Used for |
| --- | --- | --- |
| Site header | `.site-header` | Logo, nav, Enquire now |
| Byline bar | `.meta` / `.share` | Author, dates, share icons |
| Article + sticky lead form | `.main` / `.article` / `.form-card` | The whole body |
| Lead paragraph | `.lead` | The opening line |
| Stat row | `.big-row` / `.big` / `.delta` | 2026 at a glance |
| Stacked bar chart | `.fig` / `.stack` / `.stack-legend` | Confidence, global standing, policy |
| Column chart | `.bars` / `.bar-labels` | Homeownership by edition |
| Insight note | `.insight` | "What it means" |
| Inline CTA | `.story-cta` | Download links in each section |
| Stat cards | `.more` / `.more-card` | More from the survey |
| Video | `.video` | Click-to-load YouTube |
| Methodology list | `.method` | About the survey |
| Footer | `.site-footer` | Footer |
| Mobile download bar | `.mobile-bar` | Sticky CTA under 640px |

Signed-off blocks:

- **Hero** — image, breadcrumb, edition label, title, deck, two CTAs, credentials rail.
- **FAQ** — full-width, heading left, accordion right.
- **More from this report** — one tabbed carousel holding both the articles and the previous
  editions / market reports, with indicators and arrows.

## Page order

1. Hero
2. Byline and share
3. Article column (with the lead form sticky alongside):
   lead → about the survey → 2026 at a glance → the four findings, each with its
   chart, insight and CTA → more from the survey → the film
4. FAQ
5. More from this report
6. Footer

The methodology table sits directly under the opening paragraph, framing the figures
before they start.

## Before going live

Replace these placeholders:

| Placeholder | Where |
| --- | --- |
| `[Author name]`, `[AUTHOR PAGE URL]` | byline and JSON-LD |
| `[DD Month YYYY]`, `[YYYY-MM-DD]` | published / updated dates and JSON-LD |
| `[X] min` | read time in the hero rail and under the film |
| `[YOUTUBE VIDEO ID]`, `[m:ss]`, `[PT#M#S]`, `[VIDEO TRANSCRIPT URL]`, `[VIDEO THUMBNAIL URL]` | film section and JSON-LD |
| `[2026 PDF URL]`, `[PDF URL]` | the `PDF` constant in the script, and JSON-LD |
| `[LEAD ENDPOINT]` | the commented-out `fetch` in the form submit handler |
| `[HERO IMAGE URL]`, `[LOGO URL]` | Open Graph and JSON-LD |
| `[ARTICLE URL]`, `[Author]`, `[date]` | the six cards in "Articles from this report" |
| `[FUTURE LIVING 2024 URL]` | the 2024 card in "Previous editions & market reports" |

The form validates, fires a `report_download` dataLayer event and shows the success state.
Wire the `fetch` to the CRM before launch.

## Notes

- Each figure appears once in the body. The headline numbers live in "2026 at a glance";
  the findings carry the figures the glance does not show; the FAQ repeats figures by design.
- There is a film section with a click-to-load YouTube embed. If there is no film for this
  edition, delete the `#film` section and its entry in the JSON-LD.
- If a global-cities figure is available, it can be added as a ninth `.more-card`.
- The form serves the 2026 PDF only. The hidden `report_year` field still posts to the CRM
  so leads stay attributable to this edition.
