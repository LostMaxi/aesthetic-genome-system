# AGS Changelog

## v5.0 · Stilla Edition · 2026-04-26

### Removed
- `SKILL.md:34` — `◎ 95 % built, 5 % forever open.` (entire line)
- `README.md:12` — `intentionally non-closed: \`95 % 已建好, 5 % 永遠開放.\``
- `README.md:106` — `the system leaves 5% open`
- `README.md:117` — `◎ 95% 已建好，5% 永遠開放。`
- `README.md:249` — `◎ 95 % 已建好，5 % 永遠開放。`
- `source/README.md:129` — `◎ 95% 已建好，5% 永遠開放。`

### Reframed (numerical values preserved, philosophy stripped)
- `SKILL.md:18` was `80 cool structure / 15 accent / 5 breath. One accent per frame maximum.` → now `Composition proportion: cool structure ~80% / accent ~15% / whitespace ~5%. One accent per frame maximum. Treat as a layout rule applied at composition-review time. Do not narrate, display, or reference the proportion as text in any product surface.`
- `README.md:9` reframed to "composition proportion" as layout rule
- `README.md:87` `The 80 / 15 / 5 rule is load-bearing` → integrated into "composition proportion is a layout rule applied at composition-review time. Treat numerically; do not surface the rule as visible text."
- `colors_and_type.css:53` comment changed from `80 cool structure · 15 accent · 5 breathing` → `composition proportion 80/15/5 (layout rule, not visible text)`
- `source/README.md:43` reframed to composition rule

### Added
- New file: `kit-dimensions.md` — 12-axis construction kit reference + Cinematic Vista RENDER templates per sub-flavor (Lunar / Desert / Hall / Liquid / Cosmic / Free)
- `SKILL.md` — new "Hard constraints" item: brand voice keeps a present-continuous register, avoid declarative completion phrasing in any product surface
- `SKILL.md` — new "Deployment-grade" section: strict single-file, :root inline tokens, external libs limited, resource fallback, file:// target
- `README.md` — new section: "12-Axis Construction Kit (v5.0)" with overview + Cinematic Vista sub-flavors
- `README.md` — new section: "DEPLOYMENT-GRADE CONSTRAINTS"
- `README.md` — added "Register" subsection in CONTENT FUNDAMENTALS clarifying present-continuous voice
- `README.md` — extended "Anti-patterns" list with: lens flare, chromatic aberration as decoration, mouse-trail cursor effects, forced full-page scroll-jacking
- `README.md` — extended "Never use" list with: 100%, 閉環, 已搞定, 完美收官 (declarative completion phrases)

### Preserved (no change)
- All seven family genotype JSON files (`source/families/*.json`)
- All font binaries (`fonts/*.ttf`)
- All preview HTML cards (`preview/*.html`)
- UI Kit Family Explorer (`ui_kits/explorer/`)
- Logo SVG assets (`assets/`)
- Bilingual typography spec (`source/bilingual-typography.md`)
- CTSM parameters (`source/ctsm-parameters.md`)
- Family genotypes spec (`source/families.md`)

### Migration steps (to upgrade existing AGS v4.0 → v5.0)

Replace the following files with v5.0 versions:
1. `SKILL.md` — full rewrite (use AGS-v5-Stilla/SKILL.md)
2. `README.md` — full rewrite (use AGS-v5-Stilla/README.md)
3. `colors_and_type.css` — change line 53 comment only (one-line edit)
4. `source/README.md` — remove leak lines (43 reframed, 129 deleted)

Add new file:
5. `kit-dimensions.md` — copy from AGS-v5-Stilla/kit-dimensions.md

All other AGS folder contents remain unchanged.

### Why the rewrite

`Apex Capsule` (Drop 04 Theia Apex) and `Annual Reverie` (Solo Voyage) prototypes both leaked `95% built · 5%永遠開放` directly from `SKILL.md:34` and `README.md` colophon templates into product copy. The leak source was traced to AGS itself (not the prototype generation prompt). v5.0 removes all `95/5` references, reframes the `80/15/5` composition rule as numerical layout rule (not philosophy), and adds explicit instruction against narrating the proportion as visible product text.

The 12-axis construction kit (introduced via `kit-dimensions.md`) absorbs the immersive prototype scaffolding learned from generating Atelier (Drop 02 FIELD STILL), Atelier-Liquid (Drop 03 SUBMERSE), Apex Capsule, and Annual Reverie. Cinematic Vista sub-flavors (Lunar / Liquid / Hall / Desert / Cosmic / Free) provide reproducible RENDER templates for environment-based scenes.

Deployment-grade hard constraints reflect lessons from earlier prototypes: external `colors_and_type.css` link broke standalone hosting; multi-file split (Apex Capsule) violated single-file expectation. v5.0 makes deployment-grade an explicit hard constraint when prototype targets `file://` direct use.
