# Accessibility Issues Checklist
**Luminary Studio — Accessibility Evaluation Training Site**

Use this checklist to identify and document the 13 intentional WCAG 2.1 violations present on the training page.

---

## How to Use
- Work through each item independently before revealing answers
- Note the location on the page where you found each issue
- Record the WCAG success criterion and conformance level
- Check the box once you have identified and understood the violation

---

## Checklist

### Structure & Semantics

- [ ] **#1 — Missing page language declaration**
  The `<html>` element is missing a `lang` attribute, preventing screen readers from applying the correct pronunciation and speech synthesis rules.
  **WCAG 3.1.1 — Language of Page (Level A)**

- [ ] **#2 — Logo link has no accessible name**
  The site logo links to the homepage but has no `aria-label`, visible text content, or `title` attribute. Screen reader users hear only "link" with no context about the destination.
  **WCAG 4.1.2 — Name, Role, Value (Level A)**

- [ ] **#6 — Interactive element uses wrong HTML element**
  The primary "View Our Work" call-to-action is a `<div>` with an `onclick` handler rather than a `<button>` or `<a>`. It cannot be activated by keyboard, has no implicit role, and is invisible to assistive technologies.
  **WCAG 4.1.2 — Name, Role, Value (Level A)**

- [ ] **#9 — Clickable cards have no keyboard access or role**
  The team member cards are `<div>` elements styled as interactive controls. They have no `role="button"`, no `tabindex`, and no keyboard event handlers, making them completely inaccessible without a mouse.
  **WCAG 2.1.1 — Keyboard (Level A) + 4.1.2 — Name, Role, Value (Level A)**

---

### Images

- [ ] **#7 — Images missing alt attributes**
  All `<img>` elements on the page (portfolio cards and team photos) have no `alt` attribute at all — not even `alt=""`. Screen readers announce the raw filename or URL. Meaningful images require descriptive alt text; decorative images require `alt=""`.
  **WCAG 1.1.1 — Non-text Content (Level A)**

---

### Colour Contrast

- [ ] **#4 — Hero eyebrow text fails contrast minimum**
  The small uppercase label above the main heading uses `#C8B99A` text on a `#F5F0E8` cream background, yielding approximately **1.9:1** contrast. The minimum required for normal-sized text is **4.5:1**.
  **WCAG 1.4.3 — Contrast Minimum (Level AA)**

- [ ] **#5 — Hero body text fails contrast minimum**
  The hero description paragraph uses `#9A8F83` on `#F5F0E8`, yielding approximately **3.0:1** contrast — below the 4.5:1 minimum for body-sized text.
  **WCAG 1.4.3 — Contrast Minimum (Level AA)**

- [ ] **#8 — Service description text fails contrast on dark background**
  Service card descriptions use `rgba(245,240,232,0.4)` on `#1A1410`, yielding approximately **3.1:1** contrast. Body text requires a minimum of **4.5:1**.
  **WCAG 1.4.3 — Contrast Minimum (Level AA)**

- [ ] **#13 — Footer text and links fail contrast minimum**
  Footer navigation links at `rgba(245,240,232,0.45)` yield approximately **2.9:1** contrast. The copyright line at `rgba(245,240,232,0.25)` yields approximately **1.5:1**. Both fail the Level AA minimum of **4.5:1**.
  **WCAG 1.4.3 — Contrast Minimum (Level AA)**

---

### Keyboard & Focus

- [ ] **#3 — Focus indicator removed globally**
  The CSS rule `* { outline: none; }` is applied to every element on the page, eliminating the visible focus ring for all interactive elements. Keyboard users have no way to see where focus currently is.
  **WCAG 2.4.7 — Focus Visible (Level AA)**

---

### Forms

- [ ] **#10 — Form inputs have no associated labels**
  The contact form relies entirely on placeholder text to communicate field purpose. No `<label>` elements are programmatically associated with any input. Placeholders disappear when the user starts typing, and assistive technologies cannot reliably convey the field's purpose.
  **WCAG 1.3.1 — Info and Relationships (Level A) + 3.3.2 — Labels or Instructions (Level A)**

- [ ] **#11 — Select element has no label**
  The service dropdown `<select>` has no associated `<label>` element and no `aria-label`. Its first option acts as an instructional placeholder but lacks `disabled` and `selected` attributes to properly convey its role.
  **WCAG 3.3.2 — Labels or Instructions (Level A)**

- [ ] **#12 — Form error messages are not announced to screen readers**
  Validation error messages are shown by toggling CSS `display: block`, but no `role="alert"` or `aria-live` region is used. Screen readers receive no automatic notification when errors appear after form submission.
  **WCAG 3.3.1 — Error Identification (Level A) + 4.1.3 — Status Messages (Level AA)**

---

## Summary Table

| # | Issue | WCAG Criterion | Level |
|---|-------|---------------|-------|
| 1 | Missing `lang` attribute on `<html>` | 3.1.1 Language of Page | A |
| 2 | Logo link has no accessible name | 4.1.2 Name, Role, Value | A |
| 3 | Focus outline removed globally | 2.4.7 Focus Visible | AA |
| 4 | Hero eyebrow text ~1.9:1 contrast | 1.4.3 Contrast Minimum | AA |
| 5 | Hero body text ~3.0:1 contrast | 1.4.3 Contrast Minimum | AA |
| 6 | CTA button is a non-semantic `<div>` | 4.1.2 Name, Role, Value | A |
| 7 | All images missing `alt` attributes | 1.1.1 Non-text Content | A |
| 8 | Service description text ~3.1:1 contrast | 1.4.3 Contrast Minimum | AA |
| 9 | Team cards not keyboard accessible | 2.1.1 Keyboard + 4.1.2 Name, Role, Value | A |
| 10 | Form inputs have no `<label>` elements | 1.3.1 Info and Relationships + 3.3.2 Labels | A |
| 11 | Select dropdown has no label | 3.3.2 Labels or Instructions | A |
| 12 | Form errors not announced to screen readers | 3.3.1 Error Identification + 4.1.3 Status Messages | A / AA |
| 13 | Footer links and copyright fail contrast | 1.4.3 Contrast Minimum | AA |

---

*Training material only. All violations are intentional for evaluation purposes.*
