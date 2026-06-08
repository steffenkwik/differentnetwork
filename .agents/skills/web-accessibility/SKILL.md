---
name: web-accessibility
description: Implement WCAG 2.1 accessibility standards for semantic HTML, keyboard navigation, ARIA attributes, and screen reader support. Use when building accessible UI components, auditing accessibility, implementing screen reader-friendly forms, or managing focus for modals and dropdowns.
license: MIT
metadata:
  author: supercent-io/skills-template
  source: https://explainx.ai/skills/supercent-io/skills-template/web-accessibility
  version: "1.0"
---

# Web Accessibility (A11y)

Implement WCAG 2.1 accessibility standards for semantic HTML, keyboard navigation, ARIA attributes, and screen reader support.

## When to use this skill

- **New UI Component Development**: Designing accessible components
- **Accessibility Audit**: Identifying and fixing accessibility issues in existing sites
- **Form Implementation**: Writing screen reader-friendly forms
- **Modals/Dropdowns**: Focus management and keyboard trap prevention
- **WCAG Compliance**: Meeting legal requirements or standards

## Input Format

### Required Information
- **Framework**: React, Vue, Svelte, Vanilla JS, etc.
- **Component Type**: Button, Form, Modal, Dropdown, Navigation, etc.
- **WCAG Level**: A, AA, AAA (default: AA)

### Optional Information
- **Screen Reader**: NVDA, JAWS, VoiceOver (for testing)
- **Automated Testing Tool**: axe-core, Pa11y, Lighthouse (default: axe-core)
- **Browser**: Chrome, Firefox, Safari (default: Chrome)

### Input Example
```
Make a React modal component accessible:
- Framework: React + TypeScript
- WCAG Level: AA
- Requirements:
  - Focus trap (focus stays inside the modal)
  - Close with ESC key
  - Close by clicking the background
  - Title/description read by screen readers
```

## Instructions

### Step 1: Use Semantic HTML

Use meaningful HTML elements to make the structure clear.

Tasks:
- Use semantic tags: `<button>`, `<nav>`, `<main>`, `<header>`, `<footer>`, etc.
- Avoid overusing `<div>` and `<span>`
- Use heading hierarchy (`<h1>` ~ `<h6>`) correctly
- Connect `<label>` with `<input>`

```html
<!-- ❌ Bad example: using only div and span -->
<div class="header">
  <span class="title">My App</span>
  <div class="nav">
    <div class="nav-item" onclick="navigate()">Home</div>
    <div class="nav-item" onclick="navigate()">About</div>
  </div>
</div>

<!-- ✅ Good example: semantic HTML -->
<header>
  <h1>My App</h1>
  <nav aria-label="Main navigation">
    <ul>
      <li><a href="/">Home</a></li>
      <li><a href="/about">About</a></li>
    </ul>
  </nav>
</header>
```

Form Example:
```html
<!-- ❌ Bad example: no label -->
<input type="text" placeholder="Enter your name">

<!-- ✅ Good example: label connected -->
<label for="name">Name:</label>
<input type="text" id="name" name="name" required>

<!-- Or wrap with label -->
<label>
  Email:
  <input type="email" name="email" required>
</label>
```

### Step 2: Implement Keyboard Navigation

Ensure all features are usable without a mouse.

Tasks:
- Move focus with Tab and Shift+Tab
- Activate buttons with Enter/Space
- Navigate lists/menus with arrow keys
- Close modals/dropdowns with ESC
- Use tabindex appropriately

Decision Criteria:
- Interactive elements → `tabindex="0"` (focusable)
- Exclude from focus order → `tabindex="-1"` (programmatic focus only)
- Do not change focus order → avoid using `tabindex="1+"`

Example (React Dropdown):
```tsx
import React, { useState, useRef, useEffect } from 'react';

interface DropdownProps {
  label: string;
  options: { value: string; label: string }[];
  onChange: (value: string) => void;
}

function AccessibleDropdown({ label, options, onChange }: DropdownProps) {
  const [isOpen, setIsOpen] = useState(false);
  const [selectedIndex, setSelectedIndex] = useState(0);
  const buttonRef = useRef<HTMLButtonElement>(null);
  const listRef = useRef<HTMLUListElement>(null);

  const handleKeyDown = (e: React.KeyboardEvent) => {
    switch (e.key) {
      case 'ArrowDown':
        e.preventDefault();
        if (!isOpen) {
          setIsOpen(true);
        } else {
          setSelectedIndex((prev) => (prev + 1) % options.length);
        }
        break;

      case 'ArrowUp':
        e.preventDefault();
        if (!isOpen) {
          setIsOpen(true);
        } else {
          setSelectedIndex((prev) => (prev - 1 + options.length) % options.length);
        }
        break;

      case 'Enter':
      case ' ':
        e.preventDefault();
        if (isOpen) {
          onChange(options[selectedIndex].value);
          setIsOpen(false);
          buttonRef.current?.focus();
        } else {
          setIsOpen(true);
        }
        break;

      case 'Escape':
        e.preventDefault();
        setIsOpen(false);
        buttonRef.current?.focus();
        break;

      case 'Tab':
        setIsOpen(false);
        break;
    }
  };

  return (
    <div className="dropdown">
      <button
        ref={buttonRef}
        aria-haspopup="listbox"
        aria-expanded={isOpen}
        aria-label={label}
        onClick={() => setIsOpen((o) => !o)}
        onKeyDown={handleKeyDown}
      >
        {options[selectedIndex]?.label ?? label}
      </button>
      {isOpen && (
        <ul ref={listRef} role="listbox" aria-label={label} tabIndex={-1}>
          {options.map((opt, i) => (
            <li
              key={opt.value}
              role="option"
              aria-selected={i === selectedIndex}
              onClick={() => {
                onChange(opt.value);
                setIsOpen(false);
                buttonRef.current?.focus();
              }}
            >
              {opt.label}
            </li>
          ))}
        </ul>
      )}
    </div>
  );
}
```

### Step 3: Add ARIA Attributes

Use ARIA only when semantic HTML is not enough. First rule of ARIA: don't use ARIA if a native element does the job.

Common attributes:
- `aria-label` — accessible name when no visible text
- `aria-labelledby` / `aria-describedby` — reference other elements for name/description
- `aria-live` — announce dynamic updates (`polite`, `assertive`)
- `aria-hidden="true"` — hide decorative content from screen readers
- `aria-expanded`, `aria-haspopup`, `aria-selected`, `aria-current` — state
- `role` — define widget role (`dialog`, `listbox`, `option`, `alert`, etc.)

```tsx
// Live region for status messages
<div aria-live="polite" aria-atomic="true">
  {statusMessage}
</div>

// Decorative icon hidden from screen readers
<span aria-hidden="true">★</span>

// Icon-only button with accessible name
<button aria-label="Close dialog">
  <svg aria-hidden="true">...</svg>
</button>
```

### Step 4: Focus Management (Modals)

Trap focus inside modals, restore focus on close, and close with ESC / backdrop click.

```tsx
import React, { useRef, useEffect } from 'react';

interface ModalProps {
  isOpen: boolean;
  onClose: () => void;
  title: string;
  children: React.ReactNode;
}

function AccessibleModal({ isOpen, onClose, title, children }: ModalProps) {
  const modalRef = useRef<HTMLDivElement>(null);
  const previouslyFocused = useRef<HTMLElement | null>(null);

  useEffect(() => {
    if (!isOpen) return;

    previouslyFocused.current = document.activeElement as HTMLElement;

    const modal = modalRef.current;
    const focusable = modal?.querySelectorAll<HTMLElement>(
      'a[href], button:not([disabled]), textarea, input, select, [tabindex]:not([tabindex="-1"])'
    );
    const first = focusable?.[0];
    const last = focusable?.[focusable.length - 1];
    first?.focus();

    const handleKeyDown = (e: KeyboardEvent) => {
      if (e.key === 'Escape') {
        onClose();
        return;
      }
      if (e.key === 'Tab' && focusable && focusable.length > 0) {
        if (e.shiftKey && document.activeElement === first) {
          e.preventDefault();
          last?.focus();
        } else if (!e.shiftKey && document.activeElement === last) {
          e.preventDefault();
          first?.focus();
        }
      }
    };

    document.addEventListener('keydown', handleKeyDown);
    return () => {
      document.removeEventListener('keydown', handleKeyDown);
      previouslyFocused.current?.focus();
    };
  }, [isOpen, onClose]);

  if (!isOpen) return null;

  return (
    <div
      className="modal-backdrop"
      onClick={onClose}
    >
      <div
        ref={modalRef}
        role="dialog"
        aria-modal="true"
        aria-labelledby="modal-title"
        className="modal"
        onClick={(e) => e.stopPropagation()}
      >
        <h2 id="modal-title">{title}</h2>
        {children}
        <button onClick={onClose} aria-label="Close dialog">Close</button>
      </div>
    </div>
  );
}
```

### Step 5: Color Contrast & Visual Focus

- **WCAG AA**: 4.5:1 for normal text, 3:1 for large text (≥18.66px bold or ≥24px)
- **WCAG AAA**: 7:1 for normal text, 4.5:1 for large text
- Non-text UI components / states: ≥3:1
- Never convey information by color alone — pair with text/icons
- Provide a visible focus indicator; never `outline: none` without a replacement

```css
/* Visible focus indicator */
:focus-visible {
  outline: 2px solid #2563eb;
  outline-offset: 2px;
}
```

### Step 6: Test

- **Automated**: axe-core, Pa11y, or Lighthouse accessibility audit
- **Keyboard**: Tab through the whole page — every interactive element reachable and operable, focus visible, no traps
- **Screen reader**: VoiceOver (macOS/iOS), NVDA/JAWS (Windows), TalkBack (Android)
- **Zoom**: Usable at 200% zoom without loss of content/function

```bash
# Example: axe-core via @axe-core/cli
npx @axe-core/cli https://example.com

# Pa11y
npx pa11y https://example.com
```

## Accessibility Checklist

- [ ] Semantic HTML elements used (no `div`/`span` for interactive controls)
- [ ] Correct heading hierarchy (`h1`–`h6`)
- [ ] All form inputs have associated `<label>`s
- [ ] Fully keyboard operable (Tab, Shift+Tab, Enter, Space, arrows, ESC)
- [ ] Visible focus indicators on all interactive elements
- [ ] Modals trap focus and restore it on close
- [ ] ARIA used only where needed, with correct roles/states
- [ ] Live regions announce dynamic content
- [ ] Color contrast meets WCAG AA (4.5:1 / 3:1)
- [ ] Information not conveyed by color alone
- [ ] Images have meaningful `alt` text (or empty `alt` if decorative)
- [ ] Passes automated audit (axe-core / Lighthouse)
- [ ] Verified with a screen reader

---

Source: [explainx.ai — supercent-io/skills-template/web-accessibility](https://explainx.ai/skills/supercent-io/skills-template/web-accessibility)
