# 🚀 PORTFOLIO — Ashish

A polished, accessible single-page portfolio website built with modern web tooling — React + Tailwind CSS, enhanced with motion, icons and optional Firebase integration. This repository contains the source for a responsive portfolio site with pages for Home, Skills, Projects, Profile (Resume) and Contact.

---

## Why this project exists
This project showcases professional web UI, animation, and component-driven design for a personal portfolio. It presents projects, skills, and contact details in a fast, responsive SPA so recruiters, clients, and contributors can evaluate work and reach out quickly.

---

## Key highlights
- Clean, component-based SPA using React (Create React App)
- Tailwind CSS for utility-first styling and responsive layouts
- Framer Motion for smooth page transitions and micro-interactions
- Firebase dependency present — used for backend needs (contact, hosting, etc.) where configured
- Resume PDF available in `public/` (verify content)
- Intentionally minimal build configuration for easy deployment (Netlify / Vercel / GitHub Pages)

---

## Features at a glance

| Feature | Implemented | Notes |
|---|:---:|---|
| Client-side routing (Home, Skills, Projects, Profile, Contact, About) | ✅ | Routes defined in `src/App.js` |
| Responsive design | ✅ | Tailwind utility classes throughout (`src/js/*`) |
| Page transitions / animations | ✅ | Uses `framer-motion` (`AnimatePresence` and `motion`) |
| Resume download | ✅ (file exists) | `public/Ashish_Resume.pdf` — verify contents |
| Contact page | ✅ | `src/js/Contact.js` present — verify backend behaviour |
| Firebase present | ✅ (dependency + `src/firebase.js`) | Verify whether secrets are checked in; use env vars |
| Unit / integration tests | ⚠️ | CRA test scaffold present (`src/setupTests.js`) — no dedicated tests found |

---

## Tech stack (detected from package.json)

- React 19
- Create React App (react-scripts)
- Tailwind CSS 3
- Framer Motion
- Firebase (client SDK)
- lucide-react, react-icons
- html2pdf.js
- Build toolchain: PostCSS / Autoprefixer

Badges
- React: ![React](https://img.shields.io/badge/React-19.x-61DAFB)
- Tailwind: ![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-3.x-38B2AC)
- Firebase: ![Firebase](https://img.shields.io/badge/Firebase-%20-present-FFCA28)

(Replace badges with official shield links if you prefer.)

---

## Architecture overview

This is a client-side rendered React application (Create React App) with a small, focused component hierarchy:

- Entry point: `src/index.js` -> `src/App.js`
- Routes and pages: `src/App.js` uses `react-router-dom` Routes
  - Page components: `src/js/{Home,About,Skills,Projects,Profile,Contact}.js`
- Styling: Tailwind CSS configured in `tailwind.config.js` + `src/index.css`
- Animations: `framer-motion` used for page transitions (`AnimatePresence`, `motion`)
- Assets: `public/` contains static assets and `index.html`
- Backend/config: `src/firebase.js` present (inspect to validate environment variables / secrets)

How it fits together:
- The app runs in the browser as an SPA. Navigation is handled by `react-router-dom`, `App.js` wires routes to page components. Each page implements the UI and uses Tailwind utilities. Framer Motion provides enter/exit transitions for polished navigation. Firebase appears present for optional backend tasks (contact or hosting) — confirm configuration.

---

## Folder structure (top-level, trimmed)

```
.
├─ public/                # static assets, index.html, resume PDF
├─ src/
│  ├─ js/                 # page components: Home, Projects, Skills, Contact, About, Navbar, Profile
│  ├─ index.js            # React entry
│  ├─ index.css           # global styles (Tailwind imports)
│  ├─ App.js              # Router + top-level layout
│  ├─ firebase.js         # Firebase config (inspect / secure)
│  └─ reportWebVitals.js, setupTests.js
├─ package.json
├─ tailwind.config.js
├─ postcss.config.js
└─ README.md
```

---

## Installation

Prerequisites
- Node.js (recommended LTS). Project does not declare `engines` in package.json — choose a current LTS release (e.g., 18.x or 20.x).
- npm (bundled with Node) or Yarn.

Install and run locally:

```bash
# clone
git clone https://github.com/devxashish/PORTFOLIO.git
cd PORTFOLIO

# install
npm install

# start dev server
npm start
```

The app will run at http://localhost:3000 by default.

Production build:

```bash
npm run build
# serve the build or deploy to your host of choice
```

Environment & secrets
- If using Firebase, ensure any keys/credentials are not committed to repository. Use environment variables or a `.env.local` file and update `src/firebase.js` to read from process.env. (TODO: confirm whether `src/firebase.js` includes secrets; remove if present.)

---

## Usage

- Navigate the SPA using the navbar. Pages present include Home, Skills, Projects, Profile (Resume) and Contact.
- The resume file is available at `/Ashish_Resume.pdf` (public folder).
- Projects and detailed entries are presented from `src/js/Projects.js` — update this file to add or change projects.

---

## Project screenshots
No screenshot images were found in the repository. Add screenshots or a `docs/screenshots/` folder with representative images for Home, Projects and Contact pages.

TODO: add screenshots (desktop and mobile) and link them here.

---

## Live demo
No live demo URL was detected in the repository. If deployed, add the link here.

TODO: add Live Demo URL (Netlify / Vercel / GitHub Pages).

---

## Featured projects
The Projects page component exists (`src/js/Projects.js`) and is the intended place to list featured work. At present, specific featured-project metadata is stored directly in the Projects component (open that file to edit). If you manage multiple projects, consider moving data to a JSON file or CMS.

TODO: extract project metadata and add clear README entries for each featured project.

---

## Roadmap & future vision

Planned / recommended improvements (based on repository state):
- Improve accessibility (a11y) audit, fix semantic roles and keyboard interactions.
- Extract project metadata to a structured source (JSON or headless CMS).
- Add unit & e2e tests for critical UI flows (Contact form, Projects rendering).
- Consider migration off react-scripts to a faster bundler (Vite) for smaller builds.
- Provide CI/CD (GitHub Actions) with automatic preview deployments.

---

## Performance notes

- Tailwind keeps CSS small when properly purged in production; ensure purge/content paths are correct (tailwind.config.js includes `./src/**/*.{js,jsx,ts,tsx}`).
- react-scripts build produces hashed static files; run `npm run build` and inspect bundle sizes.
- If bundle size is high, consider code splitting and lazy-loading components (React.lazy + Suspense).

---

## Security notes

- Inspect `src/firebase.js` for any API keys pushed to the repository. API keys for Firebase (client SDK) are not secret by themselves, but any server credentials or service account files must never be committed. If secrets are found: rotate and move to environment variables.
- Use environment variables (`.env.local`) for deployment secrets and add `.env*` to `.gitignore`.
- Sanitize any form inputs (Contact form) before sending to backend services.

---

## Contributing

Contributions are welcome. There is currently no `CONTRIBUTING.md` or ISSUE_TEMPLATE in the repo.

Suggested minimal contributing steps:
1. Fork the repository.
2. Create a feature branch: `git checkout -b feat/your-feature`.
3. Make changes, add tests where applicable.
4. Open a PR with a clear description and screenshots.

TODO: add CONTRIBUTING.md and ISSUE_TEMPLATE to guide contributors.

---

## Developer information

- Author / owner: Ashish (GitHub: `devxashish`)
- Key files:
  - `src/App.js` — routing and app shell
  - `src/js/*` — pages and components
  - `src/firebase.js` — firebase initialisation (review & secure)
  - `public/Ashish_Resume.pdf` — resume (verify)
- Build: `react-scripts build` (CRA)

---

## License

No license file was found in the repository root.

TODO: add a LICENSE (e.g., MIT) if you want to allow reuse. Until a license is added, repository defaults to “all rights reserved.”

---

## Footer

If you’re a recruiter, client, or contributor: this code demonstrates React best-practices for small SPAs, responsive layouts with Tailwind, and motion-driven polish using Framer Motion. For changes, open a PR and reference the relevant file under `src/js/`.  

Thank you — Ashish (maintainer) · GitHub: @devxashish
