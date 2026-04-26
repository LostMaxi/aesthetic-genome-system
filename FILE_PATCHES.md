# File Patches · v4.0 → v5.0

Two existing AGS files need only small line-level edits (no full rewrite). Apply these to the matching files in your AGS folder, then re-upload to Claude Design.

---

## Patch 1 · `colors_and_type.css`

**Line 53** — change CSS comment text only.

### Before
```css
:root {
  /* ==========================================================
     COLOR — Lost Maxi.Art v2.1 Stilla-Iris constraint palette
     80 cool structure · 15 accent · 5 breathing
     ========================================================== */
```

### After
```css
:root {
  /* ==========================================================
     COLOR — Lost Maxi.Art v2.1 Stilla-Iris constraint palette
     composition proportion 80/15/5 · layout rule, not visible text
     ========================================================== */
```

Diff: just one line changed. All token values, font-faces, and other declarations untouched.

---

## Patch 2 · `source/README.md`

Two leak lines to remove or reframe.

### 2a · Line 43

**Before**
```markdown
- **80/15/5 比例**: 冷色結構 ≥80% · 跳色焦點 ≤15% · 留白呼吸 ~5%
```

**After**
```markdown
- **Composition proportion**: 冷色結構 ~80% · 跳色焦點 ~15% · 留白 ~5% (layout rule applied at composition-review time, not narrated as visible text)
```

### 2b · Line 129

**Before**
```markdown
◎ 95% 已建好，5% 永遠開放。
```

**After**
```markdown
(remove this line entirely)
```

Replace with blank line or just delete.

---

## Verification

After applying both patches, run grep on the AGS folder:

```bash
grep -rn "95\|永遠開放\|forever open\|95% built" .
```

Expected result: zero matches (excluding numerical 0.95 lerp factors, etc., in non-comment code).

After re-upload to Claude Design, future prototype runs should no longer surface "95% built · 5%永遠開放" or similar in product copy.
