# CLAUDE.md

## What this is

A personal profile page (vanilla HTML/CSS/JS, no build step, no dependencies) that doubles as a
lab for learning web fundamentals, CI/CD, and AI collaboration tooling. See `README.md` for the
concept map. The infrastructure is deliberate, not accidental — do not propose removing it as
over-engineering.

## Running it

```sh
python3 -m http.server 8000
```

No install, no build, no test runner yet.

## Deploy

GitHub Pages, deployed by `.github/workflows/deploy.yml` on every push to `master`.
Live at https://sheng.phd. The custom domain is set in the repo's Pages settings, not a `CNAME`
file (Actions deploys ignore it). shenganigan.com forwards here from GoDaddy. Why: the home repo's
`docs/adr/0001-site-domains.md`.

## Conventions

- Four-space indent for HTML/CSS/JS, two for JSON/YAML (`.editorconfig` is authoritative).
- Behaviour goes in `script.js` via `addEventListener` — no inline `onclick` attributes.
- Colours belong in CSS custom properties, not literals scattered through rules.
- Content that repeats (projects, experience) belongs in `data/*.json`, not hardcoded markup.

## Git

- Work on a branch; never commit directly to `master`.
- One logical change per commit, with a message that says why, not what.
- Changes reach `master` through a pull request. `.github/pull_request_template.md`
  lists the checks; run them locally before opening it rather than letting CI find out.
- Before trusting a new CI gate, watch it fail on purpose. An untested gate is not a gate.

## The wiki

`raw/` holds immutable source material and `wiki/` holds compiled, cited articles — a knowledge
base of *external* reading, not documentation of this codebase. Never edit anything under
`raw/`. Both directories are excluded from the published site.

## Known unfinished work

The bio in `index.html` is empty, and the `<h1>` says "Sheng" while the `<title>` says
"Sheng-Ping Liang". Both are on the plan; leave them unless the task is to fix them.
