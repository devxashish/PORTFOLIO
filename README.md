```markdown
<p align="center">
  <img src="https://img.shields.io/badge/PORTFOLIO-DevAashish-blue?logo=github" alt="project" />
  &nbsp;
  <img src="https://img.shields.io/github/stars/devxashish/PORTFOLIO?style=social" alt="stars" />
  &nbsp;
  <img src="https://img.shields.io/badge/React-19-blue?logo=react" alt="react" />
  &nbsp;
  <img src="https://img.shields.io/badge/TailwindCSS-3.3-cyan?logo=tailwindcss" alt="tailwind" />
  &nbsp;
  <img src="https://img.shields.io/badge/Framer_Motion-✓-pink?logo=framer" alt="framer-motion" />
  &nbsp;
  <img src="https://img.shields.io/badge/Firebase-✓-orange?logo=firebase" alt="firebase" />
</p>

# PORTFOLIO
A modern, animated React portfolio — minimal, fast, and focused.

---

## About
- What this project is  
  A single-page portfolio application implemented with React (Create React App), styled with Tailwind CSS and enhanced with Framer Motion animations.

- What problem it solves  
  Presents a compact, responsive developer portfolio to showcase skills, projects, and contact information in a polished, animated UI.

- Who it's built for  
  Developers and engineers who want a lightweight, maintainable portfolio template that demonstrates modern UI motion, responsive layout, and easy content updates.

---

## Project Highlights
- Clean SPA using React Router for page navigation.
- Lightweight styling with Tailwind CSS for rapid UI composition.
- Smooth, production-ready animations powered by Framer Motion.
- Component-driven structure for easy maintenance and extension.
- Projects section supports filtering (All / Major / Mini) and optional project credentials display.

---

## Features

| Feature | Status | Notes |
|---------|:------:|-------|
| Single-page routing (React Router) | ✅ | Routes: /, /about, /skills, /projects, /profile, /contact |
| Animated UI (Framer Motion) | ✅ | Entrance & hover transitions across pages and components |
| Responsive layout (Tailwind CSS) | ✅ | Grid & utility classes used throughout |
| Skills listing with icons | ✅ | Static list in src/js/Skills.js using react-icons |
| Projects list with filters | ✅ | Static projects array in src/js/Projects.js; supports "All", "Major", "Mini" |
| Project preview links & credentials | ✅ | Some projects include previewUrl and credentials (displayed on card) |
| Sticky, animated navigation | ✅ | Navbar component with active-route highlighting |
| Firebase dependency present | ✅ | Firebase is listed in package.json and a firebase.js file exists (see Security notes) |

---

## Tech Stack
- React (Create React App)
- React Router
- Framer Motion
- Tailwind CSS
- Firebase (library present)
- React Icons / Lucide
- html2pdf.js listed as a dependency (available in repo)
- Build toolchain: PostCSS / Autoprefixer

Badges
- React • Tailwind • Framer Motion • Firebase • JavaScript

---

## Architecture

High-level overview
- UI: Function components (pages under src/js) using React + Tailwind for layout and styling.
- Routing: BrowserRouter + Routes configured in src/App.js.
- Animations: Framer Motion used for entrance, hover and staggered animations.
- Data: Projects and skills are currently defined as static arrays within their respective page modules (for example, src/js/Projects.js).
- Components: Reusable presentational components live under src/components (ProjectCard is used by Projects page).

Data flow
- Static page data (skills, projects) is imported and rendered by page components.
- Navigation is client-side; page transitions are animated via Framer Motion.
- Firebase is included as a dependency and a firebase.js file is present — this indicates a place to wire up realtime or storage features if desired (no external secrets are committed here).

---

## Folder Structure

```
PORTFOLIO/
├─ .gitignore
├─ README.md
├─ package.json
├─ package-lock.json
├─ postcss.config.js
├─ tailwind.config.js
├─ public/
└─ src/
   ├─ index.js
   ├─ index.css
   ├─ logo.svg
   ├─ reportWebVitals.js
   ├─ setupTests.js
   ├─ firebase.js
   ├─ js/
   │  ├─ Navbar.js
   │  ├─ Home.js
   │  ├─ About.js
   │  ├─ Skills.js
   │  ├─ Projects.js
   │  ├─ Profile.js
   │  └─ Contact.js
   └─ components/
      └─ ProjectCard.js
```

Notes:
- The tree reflects files referenced by imports in the code (pages under src/js and a ProjectCard in src/components).
- Projects and skills are provided as static arrays inside the relevant page modules.

---

## Installation

Clone and run locally:

```bash
# clone
git clone https://github.com/devxashish/PORTFOLIO.git
cd PORTFOLIO

# install dependencies
npm install

# start dev server
npm start

# build for production
npm run build
```

These scripts are defined in package.json and rely on Create React App tooling.

---

## Usage

- Development: run npm start and open http://localhost:3000
- Navigation:
  - / — Home
  - /about — About
  - /skills — Skills
  - /projects — Projects (filterable)
  - /profile — Profile / Resume
  - /contact — Contact
- Updating content:
  - Edit skill entries in src/js/Skills.js
  - Edit projects in src/js/Projects.js (title, description, tech array, previewUrl, credentials, type)

Example: quickly add a new project (src/js/Projects.js)
```javascript
projects.push({
  title: "New Project",
  description: "Short blurb about the project",
  tech: ["React", "Tailwind"],
  previewUrl: "#",
  type: "mini"
});
```

---

## Screenshots
(Placeholders — add real screenshots by replacing these sections.)

<details>
<summary>Home — Placeholder</summary>

![Home Placeholder](./.github/screenshots/home-placeholder.png)

</details>

<details>
<summary>Projects — Placeholder</summary>

![Projects Placeholder](./.github/screenshots/projects-placeholder.png)

</details>

---

## Live Demo
Live demo will be available after the upcoming redesign.

---

## Roadmap

- Current
  - Polished SPA with animated transitions
  - Responsive layout and component-driven pages
  - Static projects and skills listing

- Next Version
  - Replace static projects with a content-backed source (Firebase or headless CMS)
  - Add contact form backend (serverless functions / Firebase)
  - Improve accessibility (a11y audits & fixes)

- Future Vision
  - Content-admin interface for non-developers to update portfolio
  - Optional theme support (light / dark)
  - Export resume/profile to PDF via an integrated flow (html2pdf.js is available in dependencies)

---

## Performance

What’s present
- TailwindCSS for compact, utility-first styling (reduces unused CSS when purged in production).
- Create React App production build produces optimized bundles (minified, hashed filenames).
- Framer Motion uses performant transforms and hardware-accelerated animation patterns.

Suggested improvements
- Adopt code-splitting for large pages or heavy libraries.
- Enable Tailwind purge/content scanning for production to reduce CSS size.
- Audit bundle with source-map-explorer / webpack-bundle-analyzer to locate large dependencies.

---

## Security

- Firebase is included as a dependency and there is a firebase.js file in the repo. Do NOT commit credentials or API keys.
- Recommended: Use environment variables (.env.local) for any Firebase config or secret values — add .env to .gitignore.
- Never put secrets, service account JSON, or API keys directly in the repository.

Example .env (do not commit):
```
REACT_APP_FIREBASE_API_KEY=your_api_key_here
REACT_APP_FIREBASE_AUTH_DOMAIN=your_auth_domain_here
```

---

## Developer

Owner: Ashish  
GitHub: https://github.com/devxashish

This project represents the evolution of my engineering journey — a concise, modern portfolio that demonstrates practical front-end craftsmanship.

---

## Contributing

Thank you for considering a contribution. To keep PRs focused:

- Fork the repo and create a descriptive branch: feature/..., fix/..., chore/...
- Keep changes small and focused; one feature or fix per PR.
- Update or add tests where applicable (CRA testing setup exists).
- Ensure linting and formatting remain consistent (Tailwind utility patterns).
- For content updates (skills/projects), update the arrays in src/js/Skills.js and src/js/Projects.js respectively.
- Open an issue with a short description before larger changes so we can discuss scope.

A suggested PR template:
- What changed
- Why it improves the project
- Any breaking changes

---

## License

No license file is present in this repository at the moment. A license will be added later.

---

Built with passion for creating modern software that solves real-world problems. 🚀
```
