# axe DevTools Audit Report — Week 7

**Date**: 2025-11-21
**Page scanned**: http://localhost:8080/tasks - No-JS Mode
**axe version**: 4.10.3

---

## Summary

- **Automatic Issues**: 4
    - **Critical**: 1
    - **Serious**: 3
    - **Moderate**: 0
    - **Minor**: 0

---

## Violations Found

### 1/2 Color Contrast (Serious)
**WCAG**: 1.4.3 Contrast (Minimum) - Level AA
**Issue**: Button text (#6c757d) on #0172ad background = 1.11 Contrast (needs 4.5:1)
**Element**: `<button>Delete</button>` in task list & `<button type="submit">Add Task</button>` in task form.
**Impact**: Low vision, colour-blind people struggle to read
**Fix**: Change button colour to #5a6268 (meets 4.53:1)

---

### 3. Links must have discernible text (Serious)
**WCAG**: 2.4.4 Link Purpose & 4.1.2 Name, Role, Value - Level A
**Issue**: Element does not have text that is visible to certain screenreaders.
**Element**: `<a href="/about"></a>`
**Impact**: People using screen readers don't know what the field is for
**Fix**: Add `aria-label`s to the text to make it readable. || https://dequeuniversity.com/rules/axe/4.10/link-name?application=AxeFirefox

---

### 4. Images must have Alternative Text (Critical)
**WCAG**: 1.1.1 Non-text Content - Level A
**Issue**: People using screenreads won't know what an image is.
**Element**: `<img src="/static/img/icon.png" width="16" height="16">`
**Impact**: People can't understand parts of the website.
**Fix**: Add `alt=""` to the `<img src="..." alt="...">`

---

## Needs Review (Manual Check Required)

### 1. Undescriptive Text (Best Practice)
**WCAG**: 4.1.2 Name, Role, Value - Level A
**Issue**: Delete text is just "Delete" (not descriptive)
**Element**: `<button type="submit">Delete</button>` // SAMPLE: In practice there is an ARIA Label so it would be good.
**Manual check**: Review if context makes purpose clear

---

## Passed Checks (Sample)

- ✅ HTML lang attribute
- ✅ Unique IDs
- ✅ Valid ARIA attributes
- ✅ Landmark roles
- ✅ Skip link present

---

## Priority Fixes (Week 7)

Based on severity + inclusion risk:
1. **Missing form labels** (Critical, WCAG A) - FIX NOW
2. **Color contrast** (Serious, WCAG AA) - FIX NOW
3. **Link purpose** (Best practice) - Defer to Week 10
