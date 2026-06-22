# CLAUDE.md — Portfolio Website

Project memory for Claude Code. Filled in from the live site (`src/pages/index.astro`), résumé (`public/OmarAymanResume.pdf`), `package.json`, `astro.config.mjs`, and `.github/workflows/deploy.yml`. Update this file whenever real facts about the developer or the project change — don't let it drift from the site.

---

## 1. What this project is

This is **Omar Ayman Mohamed's personal portfolio website** — a public artifact supporting an active job search for **backend development roles (.NET / Java-Spring, with Node.js and Flutter as supporting range)**.

Primary goals, in order:
1. Make the **backend / .NET engineer** story land immediately — hero headline, featured projects, and skills all tell the same story.
2. Showcase real, shipped work with depth — 19 projects ranging from production-style REST APIs to a computer-vision research project.
3. Be fast, clean, accessible, and recruiter-skimmable in under 30 seconds.

> Strategic note: the site leads with backend/.NET, and explicitly calls out openness to Spring Boot roles too (see contact section copy). Mobile (Flutter) and ML (Stereo R-CNN, fingerprint recognition) are presented as supporting range, not the lead story — keep it that way unless the developer's target role changes.

---

## 2. About the developer

```
Name:          Omar Ayman Mohamed
Role target:   Backend Developer (.NET) — also open to Java/Spring Boot roles
Current role:  IT Operations Engineer at e& Egypt (Etisalat Egypt), Cairo — since May 2025
Education:     BSc Computer Science, Helwan University — Faculty of Computer & Artificial Intelligence
               Aug 2019 – Jun 2023 · GPA 3.4 / 4.0
Location:      Cairo, Egypt
GitHub:        https://github.com/OmarAyman415
LinkedIn:      https://linkedin.com/in/omar-ayman-723b401b4
Email:         omarayman40404@gmail.com
Phone:         +20 100 939 8538
Website/demo:  https://omarayman415.github.io (GitHub Pages, deployed via .github/workflows/deploy.yml on push to main)
Headshot:      none in repo (public/ only has favicon.svg + OmarAymanResume.pdf) — site currently uses a terminal/JSON visual instead of a photo
```

**Positioning line** (used in hero and meta description):
> "Backend & .NET engineer with hands-on experience building REST APIs and microservices — from Entity Framework data layers to Kafka-driven distributed systems."

**Top 3 differentiators** (already substantiated on the site — keep claims to what's there):
1. Cross-stack range: ships the same backend patterns (REST APIs, JWT auth, microservices) across .NET, Java/Spring Boot, and Node.js rather than being locked to one ecosystem.
2. Currently employed maintaining production infrastructure at e& Egypt, one of Egypt's largest telecom operators — real operational/reliability experience, not just project work.
3. Breadth with depth: 19 documented projects spanning backend APIs, mobile (Flutter/Drift), and applied computer vision (Stereo R-CNN validated on the KITTI benchmark).

---

## 3. Skills to display

Matches `skills` array in `src/pages/index.astro` exactly — keep these in sync if the array changes.

```
Core .NET Stack: C#, ASP.NET Core, ASP.NET MVC, .NET Framework, Entity Framework / EF Core
Languages:       Java, JavaScript, Python, Dart, PHP, C++, SQL
Frameworks:      Spring Boot, Spring Security, Express.js, Node.js, React, Flutter, JavaFX
Databases:       SQL Server, PostgreSQL, MySQL, MongoDB, SQLite
Tools:           Docker, Apache Kafka, Git & GitHub, JPA / Hibernate, Drift ORM, WebSockets
Concepts:        RESTful APIs, Microservices, OOP & SOLID, Design Patterns, DSA, JWT Auth, MVC
```

> Rule: don't list skills that couldn't be defended in an interview. Anything on the site is fair game for questions.

---

## 4. Projects

Source of truth is the `projects` array in `src/pages/index.astro` (18 entries) — don't duplicate the full list here, it will drift. Summary of the flagship (`featured: true`) projects:

### Instagram Clone *(flagship)*
- ASP.NET MVC, Entity Framework, SQL Server, Bootstrap.
- Photo/video sharing with private messaging and auth.
- Repo: https://github.com/OmarAyman415/Instagram

### E-Commerce REST API *(flagship)*
- Java, Spring Boot, PostgreSQL, JPA/Hibernate.
- Products/carts/orders with Spring Security role-based access control.
- Repo: https://github.com/OmarAyman415/shop

*(15 more non-featured projects exist — Microservices/Kafka, Real-Time Chat, Lift Tracker, Stereo R-CNN, Compiler Scanner, Fingerprint Recognition, Course Management, Game Store API, Java Microservices, Spring Boot Auth, Dragon 2D Game, Graphics Package, Discord Bot, InstaProject Design Docs, Medical Website, YouTube Downloader. Full details and repo links are in the code.)*

> Note: "Job Board REST API" was removed from the site (no public repo to link).

---

## 5. Content & tone conventions

- Concise and direct. Short sentences, active voice, no buzzword padding — matches current hero/about copy.
- Lead every project with what it is/does, then the stack and a defensible technical highlight.
- **No invented metrics, titles, or credentials.** Anything added must trace back to the résumé or existing site copy. Leave a `TODO:` comment for anything missing — never fabricate.
- Tone: professional and confident, with a light technical/developer motif (terminal `whoami` card in hero, monospace section numbers).

---

## 6. Tech stack & commands

Confirmed from `package.json`, `astro.config.mjs`, `.github/workflows/deploy.yml`:

```bash
# install
npm install

# dev server
npm run dev

# build for production
npm run build

# preview production build
npm run preview
```

Framework: Astro 5 (single page, `src/pages/index.astro`, static output)
CSS approach: Tailwind CSS 4 via `@tailwindcss/vite`, theme tokens in `src/styles/global.css` (CSS custom properties, light/dark via `.dark` class)
Hosting: GitHub Pages, auto-deployed on push to `main` via `withastro/action@v3` + `actions/deploy-pages@v4`
Fonts: Archivo (display), Space Grotesk (body), JetBrains Mono (code/labels) — Google Fonts

---

## 7. Design direction

```
Color palette:    Light: navy/slate text on near-white surface, sky-blue accent (#0369a1) + teal accent2 (#0f766e).
                   Dark:  near-black canvas (#060a14), light text, brighter sky/teal accents (#38bdf8 / #2dd4bf).
Font preference:  Archivo (display) + Space Grotesk (body) + JetBrains Mono (code)
Style:            Minimal developer-dark-mode aesthetic — terminal motif, blueprint grid background, glow blobs, scroll-reveal animations.
Existing design:  Match current design — it's deliberate and cohesive. Improve within the existing system, don't replace it.
```

---

## 8. Working agreements for Claude Code

- **Detect before you edit.** Read `src/pages/index.astro`, `src/components/ProjectCard.astro`, `src/layouts/Layout.astro`, and `src/styles/global.css` to match existing conventions (CSS custom properties, `.card`/`.reveal`/`.stagger` utility classes, theme tokens) — don't impose new patterns.
- **Small, reviewable commits.** One logical change per commit; clear messages (e.g. `feat: add project cards section`).
- **Never touch:** `.env`, secrets, API keys, or deploy credentials. Never commit them.
- **Responsive + accessible by default.** Mobile-first, semantic HTML, alt text on images, sufficient color contrast (this site already does scrollspy, `aria-pressed` filter chips, `prefers-reduced-motion` handling — preserve that).
- **Performance matters.** Optimize images, avoid layout shift, keep the bundle lean (currently no images at all beyond the favicon — if a headshot is added, ship it optimized/responsive).
- **Ask when content is ambiguous.** Proceed confidently on implementation details; ask before inventing copy, metrics, or facts about the developer.
- **Data lives in code, not docs.** The `skills`, `projects`, `timeline`, and `facts` arrays in `index.astro` are the source of truth — don't duplicate them at length elsewhere (including this file).

---

## 9. Current session tasks

Replace this list each time there's specific work to do. (Left empty — fill in per session.)
