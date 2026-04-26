---
name: ags-design
description: Use this skill to generate well-branded interfaces and assets for the AGS (Aesthetic Genome Design System / 美學基因組設計系統 v5.0, Lost Maxi.Art Stilla Edition), either for production or throwaway prototypes/mocks. Contains essential design guidelines, Stilla-Iris colors, bilingual ZH/EN typography, five brand fonts, assets, UI kit components, and a 12-axis construction kit framework for immersive prototyping. Activate on keywords such as "AGS", "Stilla-Iris", "碇紫鳶尾", "Lost Maxi", "Aesthetic Genome", or requests phrased around α β γ δ ε ζ η families, "anti-algorithm", "anti-convergence", or "not generic / not AI-slop".
user-invocable: true
---

Read the `README.md` file within this skill, and explore the other available files. For immersive single-page prototypes, also read `kit-dimensions.md`.

If creating visual artifacts (slides, mocks, prototypes, etc), copy assets out of `fonts/` and `assets/` and create static HTML files for the user that load `colors_and_type.css`. If working on production code or deployment-grade prototypes, copy assets, inline tokens, and read the rules here to become an expert in designing with this brand.

## Workflow

1. **Identify family.** Ask or infer which of the seven families (α Restrained, β Kando, γ Organic, δ Luxury, ε System, ζ Dynamic, η Anti-Algorithm) fits the user's intent. Load its genotype JSON from `source/families/{family}.json` and let it set topology budget, font choices, radii, easing, density.
2. **For immersive prototypes, configure 12-axis kit.** When generating single-page immersive prototypes, configure the 12-Dimension Construction Kit (see `kit-dimensions.md`):
   - L1 Preset × 3: Primary Style (DOM aesthetic) / Scene Mode (Canvas) / Immersion Depth (Interaction)
   - L2 Atomic × 3: Layout / Bilingual Mode / Camera Motion
   - L3 Parallel Sub-systems × 4: zh font + weight, en font + weight
   - L4 Toggle × 1: Quiet Section
   - L5 Tonal Accents × 1: count 0-3
3. **Run anti-convergence.** Pick 2 of 6 operators (dimensional budget / prohibition / mutation, topology graft, semiotic graft, temporal clash) and apply. Two raw applications of the same family must not converge.

## Hard constraints

- Primary color is Stilla-Iris `#8384BD`. CTAs use purple background + dark ink (`#101820`), never white ink.
- Composition proportion: cool structure ~80% / accent ~15% / whitespace ~5%. One accent per frame maximum. Treat as a layout rule applied at composition-review time. Do not narrate, display, or reference the proportion as text in any product surface — colophon, footer, edition stamp, hero copy, status line, marketing copy.
- No emoji. Greek letters (Σ Λ Φ α β γ δ ε ζ η) and Unicode geometric marks (◎ △ □ ·) are the iconography.
- No bluish-purple diagonal hero gradients, no emoji cards, no "rounded card + colored left-border accent" template.
- Bilingual ZH/EN treated as topological element — three modes (primary-secondary / juxtapose / fusion).
- Brand voice keeps a present-continuous register. Avoid declarative completion phrasing in any product surface — colophon, footer, edition stamps, marketing copy, status messages. Prefer "in motion" / "continues" / "ongoing" verbs.

## Deployment-grade (when prototype targets standalone use)

When generating single-file HTML prototype for direct hosting / `file://` use:

- Strict single-file (CSS + JS inline, no external `.css` / `.js`).
- All CSS variables defined inline at `:root` — do not depend on external design-system stylesheets. Either inline `colors_and_type.css` content, or duplicate only the tokens you need.
- External libs limited to Three.js / Lenis / GSAP via CDN module (importmap). Other resources inline (SVG / canvas texture / base64).
- HDRI / fonts / GLB / images on CDN must have try-catch with procedural / system-font fallback.
- Target: open in `file://` directly, must still render core content (CDN module load tolerated).
- Scale tolerance: up to ~2500 lines single-file. Beyond, prefer module split with clear bundling instruction.

## Default ask

If the user invokes this skill without other guidance, ask:
- Which family (α-η)?
- ZH/EN bilingual or ZH-only?
- Static surface or 12-axis immersive prototype?
- Deployment-grade (single-file standalone) or studio-bound (allows external assets)?

## Files to explore

- `README.md` — full context, content + visual foundations, iconography
- `kit-dimensions.md` — 12-axis construction kit reference, Cinematic Vista RENDER templates per sub-flavor
- `colors_and_type.css` — tokens + semantic type, bilingual rules, all @font-face declarations
- `fonts/` — five brand instruments (獅尾 Thin, LINER, Maia, Yu Gothic, Noto Sans CJK TC)
- `source/families/*.json` — per-family genotype coordinates
- `source/families.md`, `ctsm-parameters.md`, `bilingual-typography.md` — deep references
- `ui_kits/explorer/` — reference UI kit (Family Explorer)
- `preview/` — cards that populate the Design System tab

◎ AGS · v5.0 · Stilla Edition
