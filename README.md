# AGS — Aesthetic Genome Design System v5.0
## 美學基因組設計系統 · Stilla Edition

> **Stilla Edition** · 碇紫鳶尾主色 · 沉揚並存十字結構
> **AGS v5.0** · 12-Axis Construction Kit · Anti-Convergence Engine

A bilingual (繁中 / EN), principled design system built on three layers:

1. **Color & Spatial Constraint Layer** — Stilla-Iris `#8384BD` is the anchor. Composition proportion: cool structure ~80% / accent ~15% / whitespace ~5%. CTAs use purple background + dark ink, never white ink.
2. **Aesthetic Genome Architecture** — six-layer system yielding seven distinguishable *families* (α Restrained → η Anti-Algorithm), each a coordinate in a Σ / Λ / Φ / CTSM space. Two of six anti-convergence operators fire on every output so no two runs feel the same.
3. **12-Axis Construction Kit** *(v5.0 new)* — for single-page immersive prototypes. Combines DOM aesthetic / Canvas scene / Interaction intensity preset axes with atomic layout/typography axes, parallel sub-systems, toggle, and tonal accent count. See `kit-dimensions.md`.

---

## Sources

All original specification files preserved at `source/`:

- `source/README.md` · top-level overview
- `source/SKILL.md` · skill definition
- `source/families.md` · full genotypes for α–η
- `source/ctsm-parameters.md` · Four-Bases numeric ranges
- `source/bilingual-typography.md` · ZH/EN as topological element
- `source/families/*.json` · machine-readable genotype tokens
- `source/package.json` · brand manifest

---

## Architecture (top → bottom = why → how)

```
Σ  符號元結構 Semiotic Meta-Structure  ── Why design (6 civilisational archetypes)
Λ  感知利用  Perception Exploit         ── Which visual traits to exploit
Φ  拓撲原語  Topology Primitives        ── What shapes (0D point → 4D time)
CTSM 四鹼基 Four Bases                  ── What values (Chromatics / Typography / Spatiality / Motion)
七族系      Seven Families (α~η)        ── Which voice
Anti-Convergence Engine                 ── Perturbation — 2 of 6 operators per output
12-Axis Construction Kit (v5.0)         ── Immersive prototype scaffolding
```

### The seven families

| Code | Name | DNA one-liner | Brand reference |
|------|------|---------------|-----------------|
| α | 克制消隱 Restrained | 技術越好，存在感越低 | Apple · Braun · Muji |
| β | 感動工藝 Kando | 精密中的溫度 | Sony · Leica · B&O |
| γ | 有機運算 Organic | 數學生成的自然 | Stripe · Linear · Vercel |
| δ | 敘事奢華 Luxury | 慢即奢侈 | Hermès · Bottega Veneta |
| ε | 系統功能 System | 500 人的一致性 | IBM Carbon · Porsche DS |
| ζ | 動態表現 Dynamic | 能量的視覺化 | Nike · Spotify · Discord |
| η | 抗演算法 Anti-Algo | 對光滑的叛逆 | A24 · Brutalist Web |

Each family ships as a JSON genotype at `source/families/{family}.json` with its own Σ / Λ / Φ / CTSM coordinates and font assignment.

---

## 12-Axis Construction Kit (v5.0)

For immersive single-page prototypes, the kit provides 12 configurable dimensions in 5 layers:

```
[L1 Preset · 3 axes]
1. Primary Style (DOM aesthetic)        — α / β / γ / δ / ε / ζ / η
2. Scene Mode (Canvas)                  — Particle Forest / Floating Geometry / Path Flythrough / Wave Field / Cinematic Vista / Off
3. Immersion Depth (Interaction)        — Light / Medium / Deep / Cinematic

[L2 Atomic · 3 axes]
4. Layout                               — Vertical Scroll / Single Page / Multi-Anchor / Split / Stage
5. Bilingual Mode                       — A Hierarchy / B Juxtapose / C Fusion
6. Camera Motion                        — Linear Flythrough / Orbit / Hover / Dynamic

[L3 Parallel Sub-systems · 4 axes]
7. zh Font                              — Noto Sans TC / 蘋方 / 思源宋體 / 獅尾 Thin / Maia
8. zh Weight                            — slider 300-700
9. en Font                              — Inter / LINER / Migra / IBM Plex Sans
10. en Weight                           — slider 300-700

[L4 Toggle · 1 axis]
11. Quiet Section                       — visible / hidden

[L5 Tonal Accents · 1 axis]
12. count                               — 0-3
```

### Cinematic Vista sub-flavors

When Scene Mode = Cinematic Vista, choose a sub-flavor:

- **Lunar** — moon surface / volcanic rock / mineral terrain. Warm dust fog, directional drift particles, bright HDRI, bloom 0.85.
- **Desert** — Tarkovsky Stalker / Dune. Wind-blown sand, low warm sun, dust particles.
- **Hall** — abandoned interior / industrial / monumental architecture. Spotlights, hard shadows, contained acoustics.
- **Liquid** — underwater / aqueous void. Cool teal fog, caustic shaders, Brownian buoyant particles, bloom 0.4 (restrained).
- **Cosmic** — deep space / planetary orbit. No fog, starfield 8000-15000, planet/moon backdrop, no god-rays, bloom 1.2.
- **Free** — agent decides based on context.

See `kit-dimensions.md` for full RENDER ARCHITECTURE template per sub-flavor.

---

## Index

| File | Purpose |
|---|---|
| `README.md` | this file |
| `SKILL.md` | Claude-skill entry point — cross-compatible with Agent Skills |
| `kit-dimensions.md` | 12-axis construction kit + Cinematic Vista RENDER templates |
| `colors_and_type.css` | design tokens + semantic type styles |
| `fonts/README.md` | font substitution notes |
| `source/` | original specification documents |
| `preview/` | Design-System-tab preview cards |
| `ui_kits/explorer/` | UI kit: AGS Family Explorer |
| `assets/` | logo mark, wordmark, grid pattern |
| `fonts/` | five brand instruments installed locally |

---

## Core colors (authoritative)

| Priority | Name | Token | Hex (digital) | Hex (print) |
|---|---|---|---|---|
| 1 | **Stilla-Iris 碇紫鳶尾** | `--stilla-iris` | `#8384BD` | `#7D7EB2` |
| 2 | Yellow 115 | `--yellow-115` | `#FDDA25` | `#FFDE2C` |
| 3 | Green 389 | `--green-389` | `#D0DF00` | `#D2DF00` |
| 4 | Green 390 | `--green-390` | `#B5BD00` | — |

Structural neutrals: `--black-6 #101820`, `--cool-gray-10 #63666A`, `--cool-gray-1 #D9D9D6`, `--paper #F6F6F4`, `--white #FFFFFF`.

The composition proportion (cool ~80% / accent ~15% / whitespace ~5%) is a layout rule applied at composition-review time. Treat numerically; do not surface the rule as visible text in product copy or colophon.

---

## CONTENT FUNDAMENTALS

**Voice.** Bilingual 繁中 / EN, frequently in the same breath. Copy reads as if written by a practitioner, not a marketer — specific, slightly cold, unafraid of technical vocabulary. Trusts the reader to look things up.

**Tone.**
- **Declarative, not persuasive.** "less is more" — not "we believe". No "join the journey" softeners.
- **Proverbial.** Compressed, almost-aphoristic sentences. One line should carry a complete thought.
- **Technical ornament.** Greek letters (Σ Λ Φ α β γ δ ε ζ η), coordinate-style notation (`temp 0.45, sat 0.12`), and Φ-topology references are part of the voice.
- **Japanese loanwords** (感動 Kando, 侘寂 Wabi-sabi, 氣韻 Qi-yun, 初心 Shoshin) where load-bearing.

**Register.** Brand voice keeps a present-continuous register. Avoid declarative completion phrasing in product copy, colophon, footer, edition stamps, status messages, marketing surfaces. Prefer "in motion" / "continues" / "ongoing" verbs over "complete" / "finished" / "shipped" / "100%".

**Casing.**
- Titles: ZH title + EN subtitle in uppercase with `letter-spacing: 0.12em` — "美學基因組系統 / AESTHETIC GENOME SYSTEM"
- Body: sentence case; no title-case paragraphs
- Code/coordinate labels: `monospace`, lower-case, underscore (`font-en-engineering`, `anti_convergence`)

**Pronouns.** Spec docs avoid `we` / `you` almost entirely — they read as observations of a system. User-facing product copy can soften to second-person for instruction; first-person plural is rare.

**Emoji.** ❌ None. Not in spec, not in product, not in headings. Unicode-math glyphs (Σ Λ Φ ◎ △ □ ·) are the only allowed soft graphical marks — they function as iconography here.

**Bilingual patterns** (see `bilingual-typography.md` for CSS):
- **Mode A · Primary-Secondary 主從** — ZH large, EN smaller/uppercase below. Formal. *Used in α β δ ε.*
- **Mode B · Juxtapose 並置** — ZH left, EN right, same size, creating dialogue. Design-forward. *Used in γ ζ.*
- **Mode C · Fusion 融合** — mixed inline, Maia highlights the accent. Experimental. *Used in η.*

**Concrete voice examples:**

- `面說話，線閉嘴，點偶爾低語。` (α motto)
- `規則存在，是為了被看見地違反。` (η motto)
- `精密中的溫度 / precision + warmth` (β DNA)
- `當一件事物被做到極致，它就消失了。` (α principle)

**Never use:** "leverage", "unleash", "reimagine", "journey", "elevate", "seamless", "next-generation", "100%", "閉環", "已搞定", "完美收官". These are the tropes AGS is engineered against.

---

## VISUAL FOUNDATIONS

### Color vibe
- **Cool-dominant** across the board. Default temperature sits 0.30–0.50 on the CTSM scale. Even "warm" families (δ Luxury at 0.65) never approach beige maximalism.
- **Stilla-Iris is bivalent** — it can count as cool structure *or* as accent depending on context. Never both in the same composition.
- **Saturation is rationed.** Neutral grays fill the structural backbone; accent yellow/green is reserved for a single point of focus per screen.
- **Imagery** (when present) skews cool, matte, low-saturation. No warm Instagram grading, no orange-teal cinematography. Grain is welcome; HDR bloom is not.

### Type
See `colors_and_type.css`. Five instruments, not interchangeable — arranged on a density gradient from maximum restraint to maximum organic warmth:

```
獅尾 Thin   ──   Yu Gothic Light   ──   Noto Sans TC 400   ──   LINER   ──   Maia
極度克制          輕                    中性骨幹              工程均一     有機手寫
```

Bilingual rules: **ZH line-height 1.8, EN 1.4**, CJK/Latin interstice `0.25em`, EN at 85 % of ZH size in primary-secondary mode. All five canonical typefaces (獅尾 Thin, Yu Gothic Light, Noto Sans TC, LINER, Maia) are installed locally under `fonts/` — no CDN substitutes.

### Spacing
- **8 px grid is the default** (α β γ δ ε). Dynamic / anti-algorithmic families (ζ η) drop to a 4 px grid or abandon grid constraints (`grid_regularity = 0.10`).
- Layout density varies wildly by family: δ Luxury at 0.15 (expansive), ζ Dynamic at 0.70, ε System at 0.65.

### Borders
- **Hairline culture.** 1 px borders at `--hairline #D9D9D6` are the default divider.
- **Dark 1 px borders** (`--black-6`) signal form controls, boundaries of interactive surfaces in ε / ζ families.
- Borders are preferred over shadows for structural affordance in α β ε families.

### Radii
Family-tuned:
- α / δ / η — **0 px** sharp
- β — 2 px (a breath of softness)
- ε — 4 px (systematic)
- γ — 8 px (organic)
- ζ — 12 px (friendly-dynamic)
- Pills (`--r-pill`) are used only for tags, status chips, never for buttons.

### Shadows
Four shadow systems co-exist:

- **Atmospheric** (α β δ) — `--shadow-2 / -3`, subtle cool-gray rgba, mimics Mach-band perception. Used to hint at elevation without drama.
- **Structural** (γ ζ) — `--shadow-struct` with a cool Stilla-Iris cast; bolder geometry.
- **Tenebrism** (δ) — `--shadow-tenebrism`, deep single-source; reserved for editorial hero panels.
- **Indicative only** (ε) — `--shadow-1`, 1-pixel offset, purely to communicate clickability.
- **Absent** (η) — shadows are banned; depth comes from dimensional conflict.

### Backgrounds
- **`--paper #F6F6F4`** warm off-white is the default ground; pure white is reserved for lifted surfaces.
- **No gradients** by default. When a family does use gradient (γ Organic, ζ Dynamic), it is a *curve field* overlaid with transparency — never the lazy bluish-purple hero-section diagonal.
- **Imagery** is full-bleed only in δ (narrative luxury) and η (editorial/brutalist). Other families treat imagery as rectangular assets inside the grid.

### Blur & transparency
- **Liquid Glass** appears in α (`backdrop-filter: blur(24px) saturate(140%)`) for floating toolbars and sheets.
- Translucent plane overlays are central to γ (`rgba(131,132,189, 0.08)` washes).
- η forbids transparency — it is a smoothness tell.

### Animation
- **Speed scales by family.** α Restrained at 0.30 (300 ms), δ Luxury at 0.15 (1200 ms slow fades), ζ Dynamic at 0.85 (everything springs).
- **Easing library** (see CSS):
  - `--ease-standard` — default material-style
  - `--ease-kando` — β's signature `cubic-bezier(0.19, 1, 0.22, 1)`
  - `--ease-spring` — γ / ζ physics
  - `--ease-linear` — η (no softening)
- **No bouncing in δ.** Elasticity is 0.00; motion is irreversible.
- **Stagger** 0–200 ms for list reveals; default 60 ms.

### Hover / press states
- **Hover.** α β δ — 1 frame opacity shift (`0.85`) + underline-thickness 1 → 2. γ — color shift to `--stilla-iris`. ζ — transform `translateY(-2px)`. ε — subtle border darken. η — flicker / step change, no smooth transition.
- **Press (active).** Color darkens to `--stilla-iris-dim`; transforms to `scale(0.985)` in ζ, no transform elsewhere.
- **Focus.** 2 px outline in `--stilla-iris-bright`, offset `2px`. Always keyboard-visible.

### Cards
- Default card = `--bg-2` (paper-ink) on `--bg-1` ground, 1 px `--hairline` border, `--shadow-1`, `--r-2` radius (ε) or none (α δ). No drop-shadow + rounded + colored-accent-border combo (that's an AI-slop pattern AGS expressly rejects).
- Full-bleed cards (δ, η) drop borders and extend to viewport.

### Protection gradients
Avoided. If text must sit on imagery, prefer a **solid cool-gray overlay at 40–60 %** or letterbox bars, not a gradient fade.

### Anti-patterns (explicitly banned in AGS)
- Bluish-purple diagonal hero gradients
- Emoji-icon cards
- Rounded-corner cards with a colored left-border accent
- `Inter`, `Roboto`, generic geometric sans for ZH/EN displays
- HDR imagery, orange-teal cinema grade
- Trailing drop shadows on buttons
- Skeuomorphic "glass morphism" that is not actually Liquid Glass
- Lens flare, chromatic aberration as decoration
- Mouse-trail cursor effects
- Forced full-page scroll-jacking (section-level pinning is allowed)

---

## ICONOGRAPHY

The brand has **no icon font** and no conventional icon system. Glyphs are treated as typography, not illustration.

1. **Greek letters (Σ Λ Φ α β γ δ ε ζ η)** are first-class iconography. They name the system's architecture and appear wherever a "category marker" is needed. Set in the EN engineering face (`--font-en-engineering`), regular weight, usually displayed at 1.2× body size.
2. **Unicode geometric marks** — `◎ △ □ · ·· ◯ ✕ →` — used as structural markers (section breaks, bullet points, diagram nodes). Never emoji.
3. **Topology notation** — `Φ-0 Φ-1 Φ-2 Φ-3 Φ-4` — used to label dimensional budgets in component metadata.
4. **SVG micro-marks** may be drawn for UI affordances (chevron, close, check). Stroke 1.5 px, no fill, caps square — matching LINER's uniform-stroke philosophy. Store them in `assets/icons/` when added.

### Substitutions flagged to user
- The canonical iconography is extremely sparse; this system does **not** pull in Lucide / Heroicons by default. If a UI kit needs them, they are loaded from CDN and flagged in that kit's README as a substitution.

### Emoji
**Forbidden.** The only soft graphical marks allowed are Unicode geometric glyphs above.

---

## DEPLOYMENT-GRADE CONSTRAINTS

When generating single-file HTML prototypes for direct hosting / `file://` use:

- **Strict single-file.** CSS + JS inline. No external `.css` / `.js` references.
- **No design-system stylesheet dependency.** All `:root` CSS variables defined inline at top. Do not link to `colors_and_type.css` from external path — either inline its content, or duplicate the tokens you need.
- **External libs limited** to Three.js / Lenis / GSAP via CDN module (importmap). Other resources inline (SVG / canvas texture / base64).
- **Resource fallback.** HDRI / fonts / GLB / images on CDN must have try-catch with procedural / system-font fallback.
- **Target.** Open in `file://` directly, must still render core content (CDN module load tolerated; full HDRI / fonts may degrade gracefully).
- **Scale tolerance.** Up to ~2500 lines single-file. Beyond, prefer module split with clear bundling instruction.

---

## Quick start

```html
<style>
  /* Inline tokens — do not link external stylesheet for deployment-grade */
  :root {
    --stilla-iris: #8384BD;
    --black-6: #101820;
    --paper: #F6F6F4;
    --font-zh: 'Noto Sans TC', 'PingFang TC', sans-serif;
    --font-en: 'Inter', system-ui, sans-serif;
    --font-display: 'Maia', 'Cormorant Garamond', serif;
  }
</style>
<body>
  <h1 class="bilingual-primary-secondary">
    <span class="zh">美學基因組系統</span>
    <span class="en">Aesthetic Genome System</span>
  </h1>
  <p class="zh">物質本真，反對光滑。<span class="en">Material authenticity, against the smooth.</span></p>
</body>
```

Pick a family → load its JSON from `source/families/` → let it set your `--font-*`, `--r-*`, `--dur-*`, `--ease-*` variables for that composition.

For immersive prototypes, layer the 12-axis construction kit on top (see `kit-dimensions.md`).
