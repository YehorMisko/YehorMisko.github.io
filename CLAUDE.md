# Portfolio site

Yehor Misko's portfolio, served by GitHub Pages at https://yehormisko.github.io.
Static HTML, CSS and vanilla JS. No build step, no framework, no dependencies.
Editing a file and pushing is the whole deploy process.

## Layout

- `index.html` gallery and about
- `pages/` deep dives: `horizon-details`, `slick9-details`, `kcd-converter-details`,
  `tools-details`
- `translations.js` every string for all three languages
- `style.css`, `assets/`, `resume.pdf`

## Translations

The site is English, Czech and Ukrainian. Text lives in `translations.js` under
`en` / `cs` / `uk`, keyed by the `data-i18n` attribute on each element. Adding copy
means adding the element with a `data-i18n` key and adding that key to all three
language blocks, or it silently falls back to whatever is hardcoded in the HTML.

`preferredLang()` in `translations.js` reads `?lang=` from the URL, so
`https://yehormisko.github.io/?lang=cs` opens the site in Czech. It accepts `cs` or
`cz`, and `uk` or `ua`, then falls back to the visitor's stored choice, then English.
Call sites are guarded with `typeof preferredLang === 'function'` so a stale cached
`translations.js` degrades instead of breaking the switcher.

## Rules

- **Never use em or en dashes (— –) in any copy for this site or for Yehor.** Use
  colons, commas, periods, parentheses. Hyphens are fine in ranges.
- **Never commit, push, or create branches without asking first, and agree the commit
  message before committing. Never add yourself as author or co-author, and never add
  AI-generated trailers.**
- **Never guess an engine version.** Slick 9 is UE4, Project Horizon is UE5. If a
  project isn't listed here, ask rather than infer.
- Project Horizon is built on the Survival Game Kit framework and commercial
  marketplace plugins. The site is careful to describe Yehor's integration, netcode
  and content work rather than claiming authorship of those frameworks. Keep that
  distinction in any copy you write.
- The site's tone is evidence first and honest about limits, including where AI
  assistance was used. Don't add marketing language.

## Wider context

Background, current work, and outreach lives in the private `work-ops` repo, which
has its own `CLAUDE.md`. Nothing personal belongs in this repo, it's public.
