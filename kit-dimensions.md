# 12-Axis Construction Kit · v5.0
## AGS Stilla Edition · Immersive Prototype Reference

For single-page immersive prototypes, this kit defines 12 configurable dimensions in 5 layers. Combine with a chosen family (α-η) and the AGS color/type tokens.

---

## Overview

```
Intent (header · per-prototype):
  - Purpose       (e.g., Product Marketing / Capsule Reveal / Annual Reverie)
  - Subject       (e.g., Physical Object / Conceptual Piece / Singular Figure)

[L1 Preset · 3 axes]
  1. Primary Style      — DOM aesthetic family
  2. Scene Mode         — Canvas content type
  3. Immersion Depth    — Interaction intensity

[L2 Atomic · 3 axes]
  4. Layout             — page composition
  5. Bilingual Mode     — ZH/EN topology
  6. Camera Motion      — scroll-driven camera trajectory

[L3 Parallel Sub-systems · 4 axes]
  7. zh Font            8. zh Weight
  9. en Font           10. en Weight

[L4 Toggle · 1 axis]
 11. Quiet Section      — visible / hidden

[L5 Tonal Accents · 1 axis]
 12. count              — 0-3 small accent injections
```

---

## L1 Preset · DOM aesthetic (Primary Style)

Maps to seven families. Load `source/families/{family}.json` for full tokens.

| Code | Name | Brand reference | Use when |
|------|------|----------------|---------|
| α | Restrained | Apple · Braun · Muji | Quiet luxury, type-centric |
| β | Kando | Sony · Leica · B&O | Precision with warmth |
| γ | Organic | Stripe · Linear · Vercel | Mathematical naturalness |
| δ | Luxury | Hermès · Bottega Veneta | Slow narrative, full-bleed imagery |
| ε | System | IBM Carbon · Porsche DS | High-density operational UI |
| ζ | Dynamic | Nike · Spotify · Discord | Energy, motion, spring physics |
| η | Anti-Algorithm | A24 · Brutalist Web | Severity, exposed structure |

---

## L1 Preset · Canvas scene (Scene Mode)

| Mode | Geometry | Use when |
|------|----------|---------|
| Particle Forest | THREE.Points 3000-8000 + filament lines | Quiet object hero |
| Floating Geometry | InstancedMesh 200-500 | Abstract field |
| Path Flythrough | CatmullRomCurve3 + TubeGeometry | Linear narrative tunnel |
| Wave Field | PlaneGeometry + vertex displacement | Frequency/data hero |
| Cinematic Vista | Environment scene with subject (see sub-flavors below) | Lusion-tier sense of scale |
| Off | No canvas | Pure DOM page |

### Cinematic Vista sub-flavors

When Scene Mode = Cinematic Vista, USER PROMPT specifies one of:

#### Lunar
- Reference: Lusion-About astronaut scene, Apollo documentary
- toneMappingExposure: 1.05 (bright)
- Fog: warm dust `0x2a2218`, density 0.014
- Main light: DirectionalLight warm `0xfff4e0`, intensity 3.0, castShadow true
- Ground: high-relief terrain (noise amplitude ×2.5), basalt color
- Particles: directional drift (downward + sideways)
- god-rays cone: tint warm `0xfff4d8`, opacity 0.30-0.40
- Bloom strength: 0.85
- Shadow map: ≥ 2048 (high tier)
- Sound: low-frequency space drone + occasional metallic ping

#### Desert
- Reference: Tarkovsky Stalker, Villeneuve Dune
- toneMappingExposure: 1.0
- Fog: warm sandstone `0x3a2818`, density 0.010
- Main light: low-angle warm sun, long horizontal shadows
- Ground: rolling terrain, occasional debris
- Particles: wind-blown horizontal drift
- god-rays: subtle, side-angle
- Bloom: 0.5
- Sound: wind, distant resonance

#### Hall
- Reference: Sofia Coppola Lost in Translation, abandoned industrial
- toneMappingExposure: 0.95
- Fog: cool gray `0x202832`, density 0.018
- Main light: SpotLight × 2-3 from above, hard cones
- Ground: tiled / concrete / wooden floor surface
- Particles: dust falling slowly through light shafts
- god-rays: vertical pillars, opacity 0.35
- Bloom: 0.6
- Sound: contained reverb, distant footstep

#### Liquid
- Reference: Apichatpong Weerasethakul, underwater
- toneMappingExposure: 0.85 (dim)
- Fog: cool teal `0x0F2027`, density 0.024
- Main light: SpotLight × 2 from above, slow sway, cool `0x406D86`
- Caustic shaders on subject: `sin(uv.x * 8 + t * 0.3) * cos(uv.y * 8 + t * 0.2)` mixed at 0.15-0.25
- Particles: Brownian buoyant `sin(t + offset) * 0.02` on Y axis
- Camera dolly tempo: × 0.45 (extra slow)
- Bloom: 0.4 (restrained)
- Refraction: subject `MeshPhysicalMaterial { transmission: 0.9, ior: 1.33 }`
- Sound: deep submerged drone 30-80 Hz
- Forbidden: lens flare, chromatic aberration, Marvel-CGI energy

#### Cosmic
- Reference: 2001 monolith approach, Solaris, Apollo log
- toneMappingExposure: 1.0
- Fog: null (vacuum)
- Background: starfield `THREE.Points` 8000-15000 with twinkle shader
- Backdrop: 1-2 planet/moon SphereGeometry (radius ≥ 80, far distance)
- Main light: DirectionalLight (sun proxy) `0xfff8e8`, intensity 4.5
- Ambient: `0x080814`, intensity 0.05 (near-black)
- Subject: figure (astronaut / probe / beacon), procedural fallback OK
- Particles: micrometeorite drift (random direction, slow)
- god-rays: omitted (no atmosphere)
- Bloom: 1.2 (high-contrast star highlights)
- Camera: POV ↔ External cycles, lookAt smooth interpolation
- Sound: low-frequency drone 36-82 Hz with LFO modulation, occasional metallic ping

#### Free
Agent decides sub-flavor based on context. Default to Lunar if unclear.

---

## L1 Preset · Interaction intensity (Immersion Depth)

| Level | Features | Pointer parallax PX | Use when |
|-------|----------|--------------------|----------| 
| Light | reveal-on-scroll only, subtle hover, no audio | 0 | Static documentation |
| Medium | pointer parallax (subtle), IntersectionObserver reveals, interaction audio (default muted), section pinning | 0.5 | Standard product marketing |
| Deep | pointer parallax (strong), raycaster pickables, magnetic UI, ambient audio (default muted), scroll-jacked sections | 1.5 | Premium product reveal |
| Cinematic | Deep + page transitions + camera narrative + View Transition API | 1.5-3 | Capsule reveal, atelier reverie |

---

## L2 Atomic axes

### Layout
- **Vertical Scroll** — sections stacked, default
- **Single Page** — all content in viewport, no scroll narrative
- **Multi-Anchor** — anchored sections, named jumps
- **Split** — two-column, often image/text or chapter/scene
- **Stage** — single dramatic frame per chapter (theatrical)

### Bilingual Mode
- **A Hierarchy** — ZH primary (large), EN secondary (smaller, below). Formal. Used in α β δ ε.
- **B Juxtapose** — ZH and EN side by side, same size, dialogue. Used in γ ζ.
- **C Fusion** — mixed inline, Maia for accent. Experimental. Used in η.

### Camera Motion
- **Linear Flythrough** — z-axis dolly, scroll progress 0→1
- **Orbit** — circular orbit around subject, scroll = angle
- **Hover** — subtle drift, no major translation
- **Dynamic** — multi-keyframe (fly-in + orbit + dolly-back), three-stage cinematic

---

## L3 Parallel Sub-systems · Typography

### zh Typography
- **font** — Noto Sans TC / 蘋方 (system) / 思源宋體 / 獅尾 Thin / Maia (decorative-only · 限標題)
- **weight** — slider 300-700, default 400 for body, 300 for display

### en Typography
- **font** — Inter / LINER / Migra / IBM Plex Sans / Cormorant Garamond Italic
- **weight** — slider 300-700, default 300 for italic display, 400 for body

### Cross-language rules (always)
- ZH line-height 1.8, EN 1.4
- CJK/Latin interstice 0.25em
- EN at 85% of ZH size in Mode A
- Display sizes scale via `clamp()`, e.g., `clamp(56px, 9vw, 196px)`

---

## L4 Toggle · Quiet Section

When `visible`: include one short section in the page rhythm — pure visual or extreme minimal symbol, no caption / no annotation / no meta-text. Just shape and breathing room.

Implementation:
```html
<section class="chapter quiet">
  <div class="glyph"><span class="mark">◎</span></div>
</section>
```

```css
.chapter.quiet {
  min-height: 70vh;
  display: grid;
  place-items: center;
}
.chapter.quiet .glyph .mark {
  font-size: 24px;
  color: rgba(255,255,255,0.32);
}
```

When `hidden`: full content, no quiet break.

---

## L5 Tonal Accents · count

`count: 0-3` small accent injections, each one small and singular:

- **Slot 1** — single rotated `-3°` reportage caption card (paper texture, narrative annotation)
- **Slot 2** — single saturated color point that breaks the cool palette (warm LED, lavender highlight, accent yellow `--yellow-115`)
- **Slot 3** — single hand-style ZH note (Maia italic, slightly rotated, like real handwriting)

Each slot used at most once per page. Slots are independent — `count: 2` may use any 2 of 3.

`count: 0` = pure execution, no deviation.

---

## SYSTEM PROMPT scaffold (for prototype generation)

When configuring Claude Design or another agent to generate an immersive prototype:

```
You are an immersive single-file HTML prototype generator for Lost Maxi · Atelier, following AGS v5.0 Stilla Edition.

Read AGS skill for: design tokens (colors / fonts / spacing / radii / shadows / animation), seven-family system, anti-convergence operators, bilingual modes, anti-pattern list, deployment-grade constraints.

When generating, configure 12-axis kit per USER PROMPT spec.

Hard constraints (inherited from AGS):
- Stilla-Iris #8384BD primary, CTA dark ink never white.
- Composition proportion 80/15/5 applied at layout time, never narrated as text.
- No emoji, Greek letters + Unicode marks only.
- Bilingual A/B/C mode per axis.
- Brand voice present-continuous, no declarative completion phrasing.
- Anti-pattern list enforced (no diagonal hero gradients, no emoji cards, no rounded+colored-border combo, no SaaS feature grids).
- Walk own path, do not mimic mainstream designer-website tropes.

Deployment-grade (when prototype targets standalone use):
- Strict single-file, all CSS/JS inline.
- :root tokens inline, no external stylesheet dependency.
- External libs limited to Three.js / Lenis / GSAP via CDN module.
- Resource fallback (HDRI / fonts / GLB) with try-catch.
- Target file:// open works (CDN module load tolerated).

Output language: 繁中 primary, EN supporting.
```

USER PROMPT structure:

```
產出 [Brand] 為「[Purpose] / [Subject]」做的單檔 HTML prototype。

Axes (12 dimensions):

[Preset]
1. Primary Style: [α-η name]
2. Scene Mode: [Particle Forest / Floating Geometry / Path Flythrough / Wave Field / Cinematic Vista / Off]
3. Immersion Depth: [Light / Medium / Deep / Cinematic]

[Atomic]
4. Layout: [Vertical Scroll / Single Page / Multi-Anchor / Split / Stage]
5. Bilingual Mode: [A Hierarchy / B Juxtapose / C Fusion]
6. Camera Motion: [Linear Flythrough / Orbit / Hover / Dynamic]

[Typography]
7. zh Font: [name] · Weight [300-700]
8. en Font: [name] · Weight [300-700]

[Toggle]
9. Quiet Section: [visible / hidden]

[Tonal Accents]
10. count: [0-3]

(If Scene Mode = Cinematic Vista) Sub-flavor: [Lunar / Desert / Hall / Liquid / Cosmic / Free]

Subject brief: [agent-invent / specific spec]
Tone brief: [voice direction]
```

---

## Verification points (post-generation)

For any generated prototype, verify:

| # | Check | Pass condition |
|:-:|--|--|
| 1 | Stilla-Iris primary | `#8384BD` present in :root |
| 2 | CTA constraint | purple bg + dark ink, never white ink |
| 3 | Composition proportion | layout reads as ~80/15/5, but no text mentions the ratio |
| 4 | No emoji | grep finds no emoji |
| 5 | Greek + Unicode marks | iconography present where appropriate |
| 6 | Bilingual mode | matches axis 5 selection |
| 7 | Brand voice register | no "100%" / "閉環" / "已搞定" / "complete" / "shipped" phrases |
| 8 | Anti-pattern free | no diagonal hero gradient / no emoji cards / no rounded+colored-border / no SaaS 3×3 |
| 9 | (Deployment-grade) Single-file | no external `.css` / `.js` references |
| 10 | (Deployment-grade) :root inline | all tokens defined in HTML, no external stylesheet |
| 11 | (Cinematic Vista) sub-flavor faithful | matches sub-flavor RENDER spec |
| 12 | (Immersion Depth) features active | parallax PX matches level, raycaster present if Deep+ |
