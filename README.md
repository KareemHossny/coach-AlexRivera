# Cleanora — Landing Page

![React](https://img.shields.io/badge/React-19-20232a?logo=react)
![Vite](https://img.shields.io/badge/Vite-8-646CFF?logo=vite)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript)
![Tailwind](https://img.shields.io/badge/Tailwind_CSS_v4-06B6D4?logo=tailwindcss)
![shadcn/ui](https://img.shields.io/badge/shadcn/ui-000000)
![React Router](https://img.shields.io/badge/React_Router_v6-CA4245?logo=reactrouter)
![Vercel](https://img.shields.io/badge/Vercel-000000?logo=vercel)

Production-grade marketing landing page for Cleanora — premium 1-on-1 fitness coaching. Built with React 19, Vite 8, Tailwind CSS v4, and shadcn/ui.

---

## Architecture

```
index.html            → Vite HTML entry point
src/
├── main.tsx           → React root + BrowserRouter
├── App.tsx            → Routes, error boundary, 404
├── styles.css         → Tailwind v4 + design tokens (oklch)
├── config/
│   └── site.ts        → Single source of truth for all content
├── components/
│   ├── sections/      → Page sections (Nav, Hero, Services, etc.)
│   └── ui/            → shadcn/ui primitives (Radix-based)
├── hooks/
│   └── use-mobile.tsx → Responsive breakpoint hook
└── lib/
    └── utils.ts       → cn() class-merging utility
```

### Component Tree

```
<App>
  <ErrorBoundary>
    <Routes>
      <Route "/" → <Home>
        <Nav />
        <main>
          <Hero />          ← Stats, CTA, badges
          <Transformations /> ← Client results grid
          <Services />        ← 6 service cards
          <Process />         ← 4-step workflow
          <Testimonials />    ← Client quotes
          <Coach />           ← Bio + credentials
          <Pricing />         ← 3-tier pricing table
          <FAQ />             ← Accordion
          <LeadForm />        ← Lead capture
          <FinalCTA />        ← Bottom CTA
        </main>
        <Footer />
        <Toaster />
      </Route>
      <Route "*" → <NotFound /> />  ← 404 page
    </Routes>
  </ErrorBoundary>
</App>
```

---

## Tech Stack

| Category | Tools |
|----------|-------|
| Framework | React 19 |
| Build | Vite 8 + TypeScript 5 |
| Styling | Tailwind CSS v4, tw-animate-css, CSS custom properties (oklch) |
| UI Library | shadcn/ui (Radix primitives — Accordion, Dialog, DropdownMenu, etc.) |
| Routing | React Router v6 (BrowserRouter) |
| Icons | Lucide React |
| Forms | react-hook-form, zod |
| Toast | Sonner |
| Charts | Recharts |
| Carousel | Embla Carousel |
| Deployment | Vercel (static SPA) |

### shadcn/ui Components Included

Accordion, Alert, AlertDialog, AspectRatio, Avatar, Badge, Breadcrumb, Button, Calendar, Card, Carousel, Chart, Checkbox, Collapsible, Command, ContextMenu, Dialog, Drawer, DropdownMenu, Form, HoverCard, Input, InputOTP, Label, Menubar, NavigationMenu, Pagination, Popover, Progress, RadioGroup, Resizable, ScrollArea, Select, Separator, Sheet, Sidebar, Skeleton, Slider, Switch, Table, Tabs, Textarea, Toggle, ToggleGroup, Tooltip.

---

## Sections

| Section | Description |
|---------|-------------|
| **Nav** | Fixed top bar with logo, navigation links, CTA button |
| **Hero** | Headline, subheadline, primary/secondary CTAs, credential badges, stats bar (500+ clients, 4.9★, 12 yrs, 94%) |
| **Transformations** | Client result cards with images and descriptions |
| **Services** | 6-column service grid (1-on-1 Coaching, Nutrition, Training, Check-Ins, Accountability, Lifestyle) |
| **Process** | 4-step horizontal workflow (Apply → Consultation → Plan → Results) |
| **Testimonials** | Client quote cards with avatars |
| **Coach** | Bio section with photo, text, credential list |
| **Pricing** | 3-tier pricing (Starter $249/mo, Premium $449/mo, VIP Custom) |
| **FAQ** | Accordion-style Q&A |
| **LeadForm** | Name, email, phone, goal selector, message textarea |
| **FinalCTA** | Bottom call-to-action |
| **Footer** | Logo, blurb, contact info, link columns, social links |

---

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| — | — | No environment variables required. The site is fully static. |

If you connect a backend (form handler, CRM, database), add keys to `.env` and reference via `import.meta.env.VITE_*`.

---

## Local Development

```bash
# 1. Install dependencies
npm install

# 2. Start dev server
npm run dev

# 3. Build for production
npm run build

# 4. Preview production build
npm run preview
```

---

## Customization

All content is driven by `src/config/site.ts`. To rebrand for your own business:

| Field | Location |
|-------|----------|
| Brand name, logo, tagline | `coach.name`, `coach.logo` |
| Hero headline + CTA | `hero.headline`, `hero.primaryCta` |
| Services | `services[]` |
| Pricing | `pricing.plans[]` |
| Testimonials | `testimonials[]` |
| FAQ | `faqs[]` |

Design tokens (colors, fonts, shadows) are in `src/styles.css` under `:root`.

---

## Deployment (Vercel)

1. Push to GitHub and import to Vercel
2. No configuration needed — Vite is auto-detected
3. SPA fallback (`vercel.json`) ensures client-side routes resolve correctly on refresh

```bash
npm run build
npx vercel --prod
```

---

## Author

**Cleanora** — Premium 1-on-1 Fitness Coaching
