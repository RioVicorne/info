# Khoa Tran — Seamless Editorial Portfolio (Astro) 🚀

> Minimalist personal info and engineering portfolio built with [Astro](https://astro.build), featuring seamless editorial typography, zero card-boxes, and instant dark/light theming.

🔗 **Live Demo:** [https://info-4ab.pages.dev](https://info-4ab.pages.dev)

## ✨ Features
- **Astro Component-Driven**: Modular, type-safe components (`Header`, `Hero`, `Experience`, `Projects`, `Stack`, `Connect`).
- **Seamless Editorial Design**: Flowing typography, unboxed interactive rows, zero cards or chunky borders.
- **Dark & Light Mode**: Instant client-side theme toggling with zero flash of unstyled content (FOUC).
- **Fast Static Site Generation**: Compiles to pure static HTML/CSS with minimal JavaScript footprint.
- **Micro-Interactions**: 1-click email copy with custom toast notification, smooth transitions.

## 🛠️ Tech Stack
- **Framework**: [Astro 4](https://astro.build)
- **Styling**: Modern CSS3 (CSS Variables, Responsive Flexbox, Smooth Transitions)
- **Typography**: Plus Jakarta Sans & JetBrains Mono (Google Fonts)
- **Hosting**: Cloudflare Pages via Wrangler

## 🚀 Getting Started

### Local Development
```bash
# Install dependencies
npm install

# Start local dev server (http://localhost:4321)
npm run dev
```

### Production Build
```bash
# Build static site to dist/
npm run build

# Preview build locally
npm run preview
```

### Deploy to Cloudflare Pages
```bash
npm run build
npx wrangler pages deploy dist --project-name info --branch main
```

## 📄 License
MIT © [Khoa Tran](https://github.com/RioVicorne)
