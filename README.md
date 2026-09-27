# Color Palette Generator

A beautiful, interactive color palette generator for designers and developers. Pick a base color and instantly generate a full shade scale with accessibility (WCAG) contrast scores — then copy or export your palette with one click.

Originally generated with [v0.app](https://v0.app).

## Features

- **Interactive color picker** — pick a base color via the visual color wheel (react-colorful) or enter a hex code directly
- **Auto-generated shade scale** — full palette of shades derived from your base color with hue, saturation, and lightness values
- **Contrast checking** — WCAG contrast ratios between palette colors, with pass/fail levels
- **Tuning controls** — sliders for vibrancy and hue shift to fine-tune the generated palette
- **Randomize** — one-click random palette generation
- **Copy to clipboard** — click any color to copy its hex code
- **Export / download** — download your palette for use in your project
- **Dark / light mode** — app-level theme toggle (built on `next-themes`)
- **Smooth animations** — Framer Motion transitions throughout the UI

## Tech Stack

- [Next.js 14](https://nextjs.org/) (App Router, static export)
- [React 18](https://react.dev/)
- [TypeScript](https://www.typescriptlang.org/)
- [Tailwind CSS](https://tailwindcss.com/) + `tailwindcss-animate`
- [shadcn/ui](https://ui.shadcn.com/) components (Radix UI primitives: slider, switch, popover, toast, label)
- [react-colorful](https://github.com/omgovich/react-colorful) — color picker
- [Framer Motion](https://www.framer.com/motion/) — animations
- [Lucide](https://lucide.dev/) icons

## Quick Start

Requirements: Node.js 18+ and npm (or pnpm).

```bash
# install dependencies
npm install

# run the dev server
npm run dev
# open http://localhost:3000

# build a static production bundle (outputs to ./out)
npm run build
```

Serve the static build with any static host:

```bash
npx serve out
```

## Project Structure

```
app/
  layout.tsx            # root layout (theme provider, fonts, metadata)
  page.tsx              # home page -> renders the generator
  globals.css           # Tailwind + global styles
components/
  color-palette-generator.tsx   # main palette generator UI (client component)
  theme-provider.tsx            # next-themes wrapper
  ui/                           # shadcn/ui primitives (button, slider, switch, toast, ...)
lib/
  utils.ts              # cn() class-name helper
public/                 # static assets
next.config.mjs         # Next.js config (static export, unoptimized images)
tailwind.config.js      # Tailwind config
components.json         # shadcn/ui config
```

## Environment Variables

None. The app is fully client-side and needs no secrets or backend.

## Deployment

This app is statically exported (`output: 'export'` in `next.config.mjs`), so it deploys anywhere that serves static files:

- **Cloudflare Pages** — this repo deploys there as a static site (see homepage link)
- **Vercel** — originally generated/synced from a v0.app deployment
- **GitHub Pages / Netlify / any static host** — serve the `./out` directory produced by `npm run build`

## License

MIT.

---

Built by Girish Lade — [ladestack.in](https://ladestack.in)
