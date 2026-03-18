# Responsive Testing Checklist — Oracle Team Landing Page

> Issue #1: debug ปัญหา CSS layout บน mobile
> Oracle: Khanti (ขันติ)

## Breakpoints

| Breakpoint | Width | Target Devices |
|-----------|-------|----------------|
| XS | ≤ 320px | iPhone SE, Galaxy S mini |
| SM | 321–480px | iPhone 14/15, Pixel |
| MD | 481–768px | iPad mini, tablets portrait |
| LG | 769–1024px | iPad, tablets landscape, small laptops |
| XL | 1025px+ | Desktop |

---

## Checklist per Breakpoint

### 320px (XS — Small phones)

- [ ] Card grid is single column
- [ ] No horizontal scroll/overflow
- [ ] Text is readable without zooming (≥ 14px)
- [ ] Touch targets ≥ 44×44px
- [ ] Modal fills entire screen
- [ ] Modal close button is tappable and visible
- [ ] Images scale without overflow
- [ ] Navigation is accessible (stacked or hamburger)
- [ ] Hero title fits without truncation
- [ ] Safe area insets respected (notched phones)

### 480px (SM — Large phones)

- [ ] Card grid is single column
- [ ] No horizontal scroll/overflow
- [ ] Font sizes scale up slightly from 320
- [ ] Touch targets ≥ 44×44px
- [ ] Modal fills entire screen
- [ ] Padding/margins feel balanced
- [ ] Forms and inputs are usable

### 768px (MD — Tablets)

- [ ] Card grid switches to 2 columns
- [ ] No horizontal scroll/overflow
- [ ] Modal is 90% width/height with border radius
- [ ] Font sizes comfortable for tablet reading
- [ ] Touch targets ≥ 44×44px
- [ ] Navigation layout adapts
- [ ] Content doesn't feel too wide or too narrow

### 1024px (LG — Small laptops)

- [ ] Card grid shows 3 columns
- [ ] Modal is centered, max-width 720px
- [ ] Container has max-width constraint
- [ ] Layout feels balanced, not cramped
- [ ] Hover states work (if applicable)

### 1025px+ (XL — Desktop)

- [ ] Card grid uses auto-fill (responsive columns)
- [ ] Modal is standard centered dialog (600px)
- [ ] Full desktop experience intact
- [ ] No regressions from mobile fixes

---

## Cross-cutting Checks

- [ ] `overflow-x: hidden` on html/body — no horizontal scroll at any breakpoint
- [ ] All images have `max-width: 100%; height: auto`
- [ ] Fluid typography working (clamp values)
- [ ] `-webkit-text-size-adjust: 100%` set
- [ ] Modal `-webkit-overflow-scrolling: touch` for iOS momentum scroll
- [ ] Safe area insets (env()) applied for notched devices
- [ ] Orientation change (portrait ↔ landscape) doesn't break layout
- [ ] Dark mode (if supported) renders correctly at all breakpoints

---

## Testing Tools

- Chrome DevTools → Device Toolbar (responsive mode)
- Safari → Responsive Design Mode
- Real devices: iOS Safari, Android Chrome
- BrowserStack or Sauce Labs for broader coverage

---

## Status

- **Created**: 2026-03-18
- **Status**: Ready for testing
- **Fixes file**: `mobile.css`
