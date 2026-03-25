# nextjs-portfolio

> Developer portfolio on Next.js 13 App Router — Framer Motion scroll reveals, animated achievement counters, type-animation hero, and a live contact form via Resend.

---

## Features

- **App Router architecture** — Server Components by default; `"use client"` only where animation or interactivity actually requires it
- **Framer Motion scroll reveals** — `whileInView` + `viewport={{ once: true }}` fires each animation exactly once per element
- **Animated achievement counters** — `react-animated-numbers` with odometer-style count-up on section entry
- **Type animation hero** — Cycling typewriter phrases with configurable sequence and deletion speed
- **Live contact form** — Server-side handler posts to Resend API; form gives optimistic feedback before the API responds
- **Tab-based About section** — Skills, Education, and Certifications without any page navigation
- **Fully responsive** — Mobile-first layout with Tailwind breakpoints

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Next.js 13 App Router | File-based routing, Server Components, Route Handlers |
| Framer Motion | Declarative spring animations with scroll triggers |
| Resend | Transactional email API for the contact form |
| react-type-animation | Typewriter hero with configurable phrase sequences |
| react-animated-numbers | Odometer-style counter animations |
| Tailwind CSS | Utility-first design system |
| Heroicons | Icon set aligned with Tailwind's design language |

---

## Getting Started

```bash
git clone https://github.com/YOUR_USERNAME/nextjs-portfolio.git
cd nextjs-portfolio && npm install
```

Create `.env.local`:
```env
RESEND_API_KEY=re_your_key_here
```

Get a free Resend API key at [resend.com](https://resend.com).

```bash
npm run dev     # http://localhost:3000
npm run build   # production build
npm run start   # serve production build
```

---

## Project Structure

```
src/app/
├── page.jsx                     # Root page — imports all sections
├── api/
│   └── send/
│       └── route.js             # Route Handler → Resend API
└── components/
    ├── HeroSection.jsx          # type-animation typewriter
    ├── AboutSection.jsx         # Tab-based (Skills / Education / Certs)
    ├── AchievementsSection.jsx  # react-animated-numbers counters
    ├── ProjectsSection.jsx      # Filterable project cards
    ├── ProjectCard.jsx
    ├── ProjectTag.jsx
    ├── EmailSection.jsx         # Contact form → /api/send
    ├── Navbar.jsx + MenuOverlay.jsx
    ├── NavLink.jsx
    ├── TabButton.jsx
    └── Footer.jsx
```

---

## Customization

**Projects** — Edit the `projectsData` array in `ProjectsSection.jsx`. Each entry takes `id`, `title`, `description`, `image`, `tag`, `gitUrl`, and `previewUrl`.

**Achievements** — Edit the metrics array in `AchievementsSection.jsx`.

**Contact email** — Update the `to` field in `app/api/send/route.js` with your email address.

---

## Deploy

```bash
# Vercel (recommended for Next.js)
npm i -g vercel && vercel

# Add RESEND_API_KEY in Vercel Environment Variables
```

---

## License

MIT
