+++
title = "Day 02 - 16/09/2026 (Remote)"
weight = 2
+++

## A. Theory

## Part 1. React Basics

### What is React?

React is an open-source JavaScript library developed by Meta for building interactive user interfaces. It organizes UI into reusable components.

### What is a component? How many types are there?

A component is an independent UI unit that receives data and returns an interface. The two common types are **Function Components**, which return JSX, and **Class Components**, which extend `React.Component`. Function Components are preferred today.

### What is JSX?

JSX is a JavaScript syntax extension that allows HTML-like markup inside JavaScript. It is compiled into React elements.

### What are props?

Props are read-only values passed from a parent to a child component. They can contain data or callbacks.

### What is state? How is it different from props?

State is internal data that can change and cause a component to render again. Props come from the parent and should not be changed by the child; state belongs to the component that manages it and is updated through a setter.

### What is the Virtual DOM? Why does React use it?

The Virtual DOM is an in-memory representation of the DOM. React compares the new and old trees, then updates only the necessary parts of the real DOM, making UI updates easier to manage.

### What are Hooks? Name common Hooks

Hooks are functions that let Function Components use state and other React features. Common Hooks include `useState`, `useEffect`, `useContext`, `useReducer`, `useRef`, `useMemo`, and `useCallback`.

### What is `useState` used for?

`useState` creates state in a Function Component and returns the current value and an update function. Calling the update function can re-render the component.

### What is `useEffect` used for?

`useEffect` runs side effects after rendering, such as API calls, event subscriptions, or timers. Cleanup releases resources when dependencies change or the component unmounts.

### What are the lifecycle stages of a React component?

The stages are **Mounting**, **Updating**, and **Unmounting**. In Function Components, `useEffect`, dependencies, and cleanup handle related behavior.

### What is CSR?

Client-Side Rendering lets the browser load JavaScript and create most of the UI on the client. The server usually returns a small initial HTML document and JavaScript files.

### What is React Router?

React Router is a routing library that maps URLs to components and supports dynamic routes, nested routes, client-side navigation, and protected routes.

### Does plain React support routing, SEO, and an API server?

React core does not include routing, server-side SEO, or an API server. React Router, other SEO tools, a separate backend, or Next.js can provide those capabilities.

### What is Context API? When should it be used?

Context API shares data across a component tree without passing props through every level. It suits shared values such as themes, locale, and user data, but should not replace all state management because updates may re-render many consumers.

### What is an SPA?

A Single Page Application loads one main HTML document and changes content with JavaScript during navigation. It feels smooth but requires attention to SEO, JavaScript loading, and state management.

## Part 2. React vs. Next.js

### What is Next.js?

Next.js is a framework built on React that provides routing, rendering strategies, image optimization, metadata, server APIs, and build/deployment tools.

### What is the core difference?

React is a UI library. Next.js is a framework that provides a fuller production architecture, with React as its UI foundation.

### How is routing different?

React needs a library such as React Router and project configuration. Next.js uses file-based routing, where files and folders in `app/` or `pages/` define URLs.

### How does rendering differ?

Plain React commonly uses CSR. Next.js supports CSR, SSR, SSG, and ISR, so each page can use an appropriate strategy.

### Why does Next.js support SEO better?

Next.js can generate HTML on the server or at build time, so search engines receive content in the initial response. It also provides convenient metadata and canonical URL support.

### How does first-load performance differ?

CSR often waits for JavaScript before showing complete content. Next.js can send pre-rendered HTML first, although real performance depends on bundles, data, caching, and rendering strategy.

### How do project structures differ?

React projects use flexible conventions such as `src/components` and `src/pages`. Next.js has stronger conventions around `app/` or `pages/`, `public/`, `layout.tsx`, route handlers, and configuration.

### Does Next.js replace React?

No. Next.js uses React for the UI and adds web application capabilities. It is a React-based framework, not a replacement.

### When should React or Next.js be used?

Use plain React for internal SPAs or dashboards that do not need SSR/SEO and need a freely chosen backend and build setup. Use Next.js when SEO, fast initial loading, integrated routing, SSR/SSG/ISR, full-stack features, or production conventions matter.

## Part 3. Next.js

### What are App Router and Pages Router?

App Router under `app/` is the modern system, supporting nested layouts, Server Components, streaming, and route handlers. Pages Router under `pages/` is older but supported, with APIs such as `getStaticProps` and `getServerSideProps`.

### Server Component vs. Client Component

Server Components render on the server and suit data access without sending all component code to the browser. Client Components use `"use client"`, send JavaScript to the browser, and are needed for state, event handlers, effects, or browser APIs.

### What is SSR?

Server-Side Rendering creates HTML on the server for each request and sends it to the browser. It suits request-dependent content and SEO.

### What is SSG?

Static Site Generation creates HTML at build time. Static pages can be served quickly through a CDN and suit documentation and infrequently changing content.

### What is ISR?

Incremental Static Regeneration updates generated static pages after an interval or through revalidation without rebuilding the entire site.

### How does file-based routing work?

Next.js maps files to URLs: `app/about/page.tsx` creates `/about`, while `app/blog/[slug]/page.tsx` creates a dynamic `/blog/:slug` route.

### What is a dynamic route?

A dynamic route contains URL segments that vary with data, written in square brackets such as `[id]` or `[slug]`.

### What is `layout.tsx` for?

`layout.tsx` defines shared UI for a route and its child routes, such as a header, sidebar, or provider. It remains during navigation within the same branch.

### What are API Routes and Route Handlers?

Route Handlers are server endpoints in `route.ts` files inside `app/`. They handle methods such as `GET`, `POST`, `PUT`, and `DELETE`, and suit internal APIs, webhooks, or small endpoints.

### What are `getStaticProps` and `getServerSideProps`?

These Pages Router APIs load data at build time for static pages or on every request for SSR, respectively. They are not used in App Router.

### How does `next/image` optimize images?

`next/image` supports responsive sizing, lazy loading, suitable formats, caching, explicit dimensions to reduce layout shift, and configured remote images.

### What is Middleware?

Middleware runs before a request completes. It can inspect cookies or tokens, redirect, rewrite, add headers, and restrict access. It should remain lightweight.

### How do you navigate between pages?

Use `Link` from `next/link` for internal links. Use `useRouter` from `next/navigation` in Client Components for programmatic navigation; Server Components can use `redirect`.

### How are metadata and SEO handled?

App Router supports `metadata` or `generateMetadata` for titles, descriptions, and Open Graph data. Pages Router can use `next/head`. Sitemaps, robots, and canonical URLs should also be configured.

### Does Next.js support TypeScript?

Yes. Next.js supports `.ts`, `.tsx`, type checking, and `tsconfig.json`; type checking can be included in the build workflow.

### Where can Next.js be deployed?

Next.js can run on Vercel, AWS, Google Cloud, Azure, Render, Railway, Docker, or a private server. Suitable static pages can also be deployed to a CDN or static host, subject to SSR, ISR, image, and API support.

## B. Practice

## Completing the Portfolio

### Objectives

Complete a personal portfolio website built with React and Ant Design, populate it with real content, optimize the responsive layout, and prepare it for the mentor demo.

Expected deliverables:

- A complete personal portfolio page.
- Responsive layout on both desktop and mobile.
- Sections for introduction, skills, projects, experience, and contact.
- A deployed website link.
- A weekly report link shared with the mentor via Slack.

### Build Process

**Step 1: Install and configure the project**

- Install and verify the required libraries: React, React DOM, React Router DOM, Ant Design, Lucide React.
- Create the basic folder structure.

**Step 2: Build the component structure**

- Create reusable UI components: Button, Card, Modal, Tag, Drawer, IconButton.
- Create the main site layout.
- Create `SiteHeader` with a personal logo, navigation, contact button, and mobile drawer navigation.
- Create `SiteFooter`.
- Set up routing with `react-router-dom`.
- Create `PortfolioLayout` to manage the shared layout.

**Step 3: Build the landing page**

The landing page is divided into the following sections:

- Hero / Introduction
- About Me
- Skills
- Projects
- Experience / Education
- PEEP Report
- Contact

Sections are linked with anchor navigation so users can jump quickly within the page.

**Step 4: Update personal content**

- Replace placeholder content with real information from the personal CV.
- Add skills grouped by category: Programming, Backend, Frontend, Database, Tools & AI.
- Add project entries with descriptions, technologies used, and roles.
- Add education and experience entries.
- Add contact information and social links.

**Step 5: Refine the UI and verify**

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
