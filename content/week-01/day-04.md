+++
title = "Day 04 - 18/09/2026 (On-site)"
weight = 4
+++

## Goal

Update personal content and refine the UI for a personal portfolio website.

### Tasks

**Update personal content**

- Replace placeholder content with real information from the personal CV.
- Add skills grouped by category: Programming, Backend, Frontend, Database, Tools & AI.
- Add project entries with descriptions, technologies used, and roles.
- Add education and experience entries.
- Add contact information and social links.

**Refine the UI and verify**

- Redesign the About Me section and add a profile snapshot card with key metrics.
- Switch the color palette from beige/orange to a cool blue theme.
- Add rounded corners to buttons, cards, tags, and sections.
- Add subtle shadows for visual depth.
- Replace the default favicon with a custom logo.
- Verify responsive behavior across different screen sizes.
- Run a production build to confirm there are no errors.

### Link Demo

- [Personal Portfolio](https://minhtrungportfolios-ebon.vercel.app/)
- [Source Code](https://github.com/MinhTrungPham/weekly-reports/tree/main/tuan-01/my%20portfolios)

## Summary

The first three days of the week focused on two parallel tracks: building a solid theoretical foundation in React and Next.js, while applying that knowledge through two real shipped products.

### Lessons from Day 2 — React & Next.js

Day 2 was an intensive theory session that formed a complete mental model of the modern frontend ecosystem:

- **React is a UI library**, not a framework — routing, SSR, and API servers require additional tooling or a switch to Next.js.
- **Virtual DOM and reconciliation** are the core mechanisms that let React update the UI efficiently without direct manipulation of the real DOM.
- **Hooks** (`useState`, `useEffect`, `useContext`…) have fully replaced Class Components in modern React development.
- **Next.js extends React** with File-based Routing, Server/Client Components, SSR/SSG/ISR, API Route Handlers, and built-in SEO support — making it the right choice for most production projects.
- The distinction between **Server Components** and **Client Components** (`"use client"`) is a critical concept to master when working with the App Router.

### Lessons from Day 3 — Naruto Landing Page

Day 3 was the first hands-on session with Next.js, building a landing page themed around the Naruto anime:

- Applied the **App Router** with a clean separation of concerns: layout, section components, UI primitives, and a data layer (`naruto.ts`).
- **Bento Grid** combined with a Dark Cinematic aesthetic produced a strong visual identity; the key takeaway is to lock in the design system (colors, typography, spacing) early.
- Splitting CSS into dedicated files by responsibility (`base`, `theme`, `motion`, `sections`) makes the codebase far easier to scale and maintain than a single large stylesheet.
- **TypeScript interfaces** standardize the shape of data for each section, avoiding hard-coded values and making it easy to extend content later.

### Lessons from Day 4 — Personal Portfolio

Day 4 marked the completion of the first personal product ready for a demo:

- **Real content matters more than placeholders** — populating the portfolio from an actual CV makes it significantly more valuable for professional presentation.
- **Design consistency** requires early decisions on color palette, border-radius, shadow, and typography; late changes (beige/orange → cool blue) are costly if values are not tokenized upfront.
- **Production builds** must be run before deploying; build errors often differ from development-mode errors, especially in Next.js (Server Components, dynamic imports, metadata).
- **Responsive testing** cannot be skipped — a layout that looks fine on desktop may break on mobile if not checked early.
- Deploying to **Vercel** early provides a real demo link, making it easier to report progress and gather feedback quickly.

### Looking Back at Week One

Three days of interleaved theory and practice demonstrated one clear truth: React and Next.js knowledge only becomes solid when validated through real code. Two deployed products — the Naruto landing page and the personal portfolio — are concrete evidence of the learning that took place in the first week.
