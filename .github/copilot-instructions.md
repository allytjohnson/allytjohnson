# Repo conventions

Follow [operating principles](../docs/operating-principles.md) first. Shared skills (humanizer, grilling, caveman) live in the Role-Ops repo under `.github/skills/`; don't add copies here.

## Walking deck (`docs/walking-deck.md`)

- Marp slide deck. After any edit, rebuild the HTML:
  `npx @marp-team/marp-cli@latest docs/walking-deck.md -o docs/walking-deck.html --html`
- Style reference: `local-reference/slide-deck-sample-1.JPG` through `-7.JPG` (gitignored,
  local-only) show the approved gradient angle, typography, and bullet/list formatting the
  deck is modeled on. If they're missing, ask the user for fresh copies rather than guessing.
- Shared visual: a 135deg gradient (`linear-gradient(135deg, #006fdb 0%, #4862d4 25%, #8c52cc 50%, #c877ad 75%, #ffafa0 100%)`)
  is used on both the deck's bookend slides and the GitHub Page header. Keep them in sync.

## GitHub Page (`docs/index.html`)

- Structure/spacing/breakpoints are vendored from `pages-themes/cayman`
  (`_layouts/default.html`, `_sass/jekyll-theme-cayman.scss`, `_sass/variables.scss`), but the
  color palette is Fluent (Segoe UI font stack, accent blue `#0078d4` light / `#2899f5` dark),
  not Cayman's default green/blue.
- Theming: CSS custom properties (`--page`, `--ink`, `--muted`, `--line`, `--accent`,
  `--accent-soft`, `--focus`) with `:root[data-theme="dark"]` overrides, `localStorage('portfolio-theme')`
  for a persisted manual override, and a `prefers-color-scheme` media query listener for the
  system default when no override is set.

## Content sourcing

- Do not store resume or LinkedIn content in this repo — it goes stale quickly. If deck or
  README copy needs updating from either source, ask the user to paste or attach a current
  copy instead of relying on any cached file.

## Validation habit

- After editing `docs/walking-deck.md`, `docs/index.html`, or `README.md`, run `get_errors` on
  the changed file(s) and `git diff --check` to catch whitespace issues before considering the
  edit done.
