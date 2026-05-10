# Karigiri Kit

Most component libraries make your product look like their component library.

Karigiri Kit inverts this. Behaviour is hardcoded and correct. Appearance is entirely yours. Four CSS variables completely rebrand the entire library:

```css
:root {
  --kg-color-primary:        your-brand-primary;
  --kg-color-primary-hover:  your-brand-primary-dark;
  --kg-color-primary-subtle: your-brand-primary-light;
  --kg-font-sans:            'Your Font', sans-serif;
}
```

That is all. Every component updates automatically. No config files. No rebuilds. No design system expertise required.

**[→ Live Demo & Documentation](https://karigiri-kit.divdstack.com/)**

---

**Karigiri (कारीगरी)** means *craftsmanship* in Hindi.

---

## Components

37 components, all stable:

Accordion · Alert · AlertDialog · AspectRatio · Avatar · Badge · Button · Card · Checkbox · Collapsible · ContextMenu · Dialog · Drawer · DropdownMenu · HoverCard · Input · Label · Menubar · NavigationMenu · Pagination · Popover · Progress · RadioGroup · ScrollArea · Select · Separator · Sheet · Skeleton · Slider · Switch · Table · Tabs · Textarea · Toast · Toggle · Tooltip

---

## Installation

```bash
pnpm add @karigiri-kit/core
# or
npm install @karigiri-kit/core
# or
yarn add @karigiri-kit/core
```

```tsx
import { Button } from '@karigiri-kit/core'
import '@karigiri-kit/core/styles'

export default function Page() {
  return <Button variant="primary">Get started</Button>
}
```

---

## Theming

Karigiri Kit uses a two-layer CSS custom property system.

**Layer 1 — Primitive palette.** Raw colour values. Components never reference these directly.

```css
--kg-slate-600: #2B4B7E;
--kg-copper-500: #B5672A;
--kg-red-500:    #EF4444;
```

**Layer 2 — Semantic aliases.** What components actually consume. These reference Layer 1. Override Layer 2 to rebrand.

```css
--kg-color-primary:       var(--kg-slate-600);
--kg-color-primary-hover: var(--kg-slate-700);
```

Because components only reference Layer 2, a brand override is four lines of CSS. No JavaScript required. No build step. No design tokens pipeline.

**Default — Slate × Copper:**

```css
/* nothing — the defaults are already set */
```

**Your brand in green:**

```css
:root {
  --kg-color-primary:        #059669;
  --kg-color-primary-hover:  #047857;
  --kg-color-primary-subtle: #D1FAE5;
}
```

Dark mode works the same way — apply overrides under `[data-theme="dark"]`.

---

## Theme Playground

Not sure which color or font fits your brand? The [live playground](https://karigiri-kit.divdstack.com/playground) lets you configure a theme visually without writing a line of code.

- Pick any primary color and see the full derived scale (base, hover, active, subtle) computed automatically
- Adjust border radius from sharp to fully rounded
- Scale the entire type system up or down
- Preview 90+ Google Fonts rendered in their own face
- Export the result as a `:root { }` CSS block or a JSON token map — paste it directly into your project

---

## Design Token Architecture

Six namespaced token layers, all documented at [karigiri-kit.divdstack.com/tokens](https://karigiri-kit.divdstack.com/tokens/colors):

```
--kg-color-*     brand, semantic, and surface colors (light + dark)
--kg-text-*      fluid type scale (xs → 4xl)
--kg-weight-*    regular · medium · semibold · bold
--kg-space-*     4px-base spacing scale (1 → 20)
--kg-radius-*    border radius scale (sm → full)
--kg-shadow-*    four elevation levels
--kg-duration-*  motion timing (fast · normal · slow)
--kg-ease-*      easing curves (standard · decelerate · accelerate)
```

---

## Philosophy

**Behaviour is non-negotiable.** Focus management, keyboard navigation, ARIA roles, loading states, error states — these are not configurable. They are hardcoded and correct. A button that loses focus on loading is inaccessible. A button that lets you click while loading is broken. These problems are solved once, in the library.

**Appearance is entirely yours.** Every visual decision — every colour, radius, shadow, spacing, font — lives in a CSS custom property. The library ships with a default Slate × Copper brand. You replace it with four lines of CSS.

**The source teaches you something.** Every non-obvious decision in the codebase has a comment explaining why, not what. `// We use aria-disabled instead of disabled so screen readers can still find the button` is useful. `// disable the button` is not. If you read the source, you should learn frontend engineering, not just copy-paste.

---

## Development

```bash
# Install dependencies
pnpm install

# Build all packages
pnpm build

# Run the Next.js demo app
pnpm --filter next-example dev

# Run tests
pnpm --filter @karigiri-kit/core test:run
```

---

## Open Source

> **This repository will be open-sourced soon.**
>
> The codebase is currently private while final packaging and documentation are being completed. The full source — component library, token packages, and documentation site — will be made public shortly.
>
> In the meantime, everything is live and explorable at **[karigiri-kit.divdstack.com](https://karigiri-kit.divdstack.com/)**.

---

*Built by [Divyanshu](https://divdstack.com/)*
