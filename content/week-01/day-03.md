+++
title = "Day 03 - 17/09/2026 (Remote)"
weight = 3
+++

### Links

- [Source Code](https://github.com/MinhTrungPham/weekly-reports/tree/main/tuan-01/landing-page)
- [Live Demo](https://landing-page-phi-tan-xz2x97g6ov.vercel.app/)

## Practice

## Building the Naruto Landing Page

### Overview

The main task of the day was building the foundation of a Naruto anime landing page with a **Dark Cinematic + Japanese + Bento Grid** visual style. The page is designed as an immersive introduction to the shinobi world — covering characters, the journey, techniques, and key relationships.

---

### Tech Stack

| Layer         | Choice                              |
| ------------- | ----------------------------------- |
| Framework     | Next.js 16 with App Router          |
| UI            | React 19 + TypeScript               |
| Design System | `@buildo/bento-design-system`     |
| Styling       | Tailwind CSS / PostCSS + custom CSS |
| Code Quality  | ESLint                              |

---

### Project Architecture

The project is organized around a clear separation of layout, UI primitives, sections, and data:

```text
landing-page/
├── app/
│   ├── layout.tsx
│   ├── page.tsx
│   ├── globals.css
│   └── styles/
│       ├── base.css
│       ├── naruto-theme.css
│       ├── motion.css
│       ├── sections.css
│       └── jutsu-orbit.css
├── components/
│   ├── layout/
│   │   ├── MarketingLayout.tsx
│   │   ├── SiteHeader.tsx
│   │   └── SiteFooter.tsx
│   ├── sections/
│   │   ├── NarutoLanding.tsx
│   │   └── naruto/
│   │       ├── AboutSection.tsx
│   │       ├── CharactersSection.tsx
│   │       ├── HeroSection.tsx
│   │       ├── IconicMomentsSection.tsx
│   │       ├── JourneySection.tsx
│   │       ├── JutsuSection.tsx
│   │       ├── NarutoCtaSection.tsx
│   │       ├── QuotesSection.tsx
│   │       ├── RivalrySection.tsx
│   │       ├── ShinobiWorldSection.tsx
│   │       ├── ActionButton.tsx
│   │       └── SectionHeading.tsx
│   └── ui/
│       ├── Container.tsx
│       └── Section.tsx
└── data/
    └── naruto.ts
```

`NarutoLanding.tsx` acts only as a composer that assembles sections in order. All mock content and TypeScript interfaces live in `data/naruto.ts`, keeping section components free of hard-coded data.

---

### What Was Built

**Foundation**

Set up Bento Design System, configured page metadata, and created `MarketingLayout` as a shared wrapper for the header, main content area, and footer. Added anchor-based header navigation.

**Sections**

The landing page is divided into ten independent sections:

| #  | Section          | Purpose                                      |
| -- | ---------------- | -------------------------------------------- |
| 1  | Hero             | Main theme introduction and CTA              |
| 2  | About Naruto     | Story and journey toward recognition         |
| 3  | Shinobi World    | Chakra, Bonds, and Will of Fire              |
| 4  | Characters       | Naruto, Sasuke, Sakura                       |
| 5  | The Journey      | Timeline from Academy to the next generation |
| 6  | Iconic Moments   | Key story highlights                         |
| 7  | Jutsu            | Interactive orbit of techniques              |
| 8  | Quotes           | Notable lines from the series                |
| 9  | Naruto vs Sasuke | Rivalry and bond section                     |
| 10 | CTA              | Call to continue the journey                 |

**Hero section** includes a Japanese/English eyebrow, the main tagline *"The way of the ninja is never a straight line."*, a short shinobi world description, an `Enter the shinobi world` CTA, and a `火の意志 / WILL OF FIRE` badge.

**Mock data and interfaces**

Defined TypeScript interfaces to standardize all section content:
`HeroContent`, `FeatureItem`, `CharacterProfile`, `TeamMember`, `TimelineEntry`, `IconicMoment`, `JutsuItem`, `QuoteItem`, `RivalryContent`.

---

### Visual Design

**Color palette**

```text
Background: #0B0B0F
Surface:    #15151C
Orange:     #FF6B00
Yellow:     #FFA726
White:      #F5F5F5
Muted:      #9CA3AF
```

**Style direction** — dark and cinematic, Japanese-inspired, high contrast, with circular details, kanji accents (`忍`, `術`, `言葉`) and technical borders. Headings are large, bold, and condensed. Body text uses a clean sans-serif. The orange accent reflects Naruto's signature color.

CSS is split into separate files by responsibility (`base`, `naruto-theme`, `motion`, `sections`, `jutsu-orbit`) to keep it maintainable.
