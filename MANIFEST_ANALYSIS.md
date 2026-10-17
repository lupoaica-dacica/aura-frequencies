# PWA Manifest Issues Found

## Issues Identified in Current manifest.json

### ❌ Critical Issues (Must Fix)

1. **Missing `purpose` field in icons**
   - Current: Icons only have `src`, `sizes`, `type`
   - Required: Each icon needs `purpose: "any"` and/or `purpose: "maskable"`
   - Impact: PWA doesn't support adaptive icons on modern OS

2. **Screenshot is too small**
   - Current: `1617x1012` pixels
   - Issue: Landscape orientation might not meet all requirements
   - Required: Need both portrait (minimum 320x320) and landscape (minimum 320x320)
   - Better: Use 540x720 (portrait) and 720x540 (landscape)

3. **Screenshot missing `form_factor` field**
   - Current: No `form_factor` field
   - Required: Should specify `"narrow"` (mobile) or `"wide"` (desktop)
   - Impact: Better display in install prompts

4. **Shortcut icon missing `type` field**
   - Current: Icon in shortcuts array has no `type`
   - Required: Should be `"type": "image/png"`
   - Impact: Browser can't determine how to load icon

### ⚠️ Warning Issues (Should Fix)

5. **Non-standard custom properties**
   - `"features"`: This is not a standard manifest property
   - `"widgets"`: This is proprietary (MS Adaptive Cards)
   - Impact: May cause validation warnings in PWA checkers

6. **Description might be too short**
   - Current: "This is a PWA Starter app"
   - Standard: Should be more descriptive
   - Recommended: At least 20-30 characters, explain what app does

7. **Short name might be too long for some platforms**
   - Current: "starter" (7 characters)
   - Issue: Some platforms display "Pro" or full app names on iOS
   - Recommended: Keep under 12 characters (OK at 7, but clarify)

### ✅ Good Items (Keep These)

- Theme and background colors are valid
- Display mode "standalone" is correct
- Start URL is set properly
- ID and scope are correct
- Icons have correct sizes (24, 48, 192, 512)
- Orientation is set to "any"

## Priority Fixes

### P1 (Must Fix Today):
1. Add `purpose` field to all icons
2. Add `form_factor` to screenshots
3. Add `type` field to shortcut icon
4. Consider adding portrait-oriented screenshot

### P2 (Should Fix Soon):
1. Update app name to "Aura Frequencies"
2. Improve description
3. Keep or remove non-standard fields

### P3 (Nice to Have):
1. Optimize screenshot sizes
2. Add more screenshots
3. Add more shortcuts

