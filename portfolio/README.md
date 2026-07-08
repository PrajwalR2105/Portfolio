# Prajwal R — Portfolio Website

A modern, dark-themed, glassmorphism personal portfolio built with **pure
HTML5, CSS3, and vanilla JavaScript** — no frameworks, no build step.
Content is populated from the resume `PRAJWAL_R_FlowCV_Resume_2026-07-08.pdf`.

## Running it

There's no build process. Just open `index.html` in a browser, or serve the
folder locally for the best experience (some browsers restrict `fetch`/
local file access under `file://`):

```bash
# Option 1: Python
python3 -m http.server 8000
# then visit http://localhost:8000

# Option 2: VS Code
# Right-click index.html → "Open with Live Server"
```

## Project structure

```
portfolio/
│── index.html          Single-page site (all sections, anchor navigation)
│
├── css/
│     style.css          Design tokens, layout, components, animations
│     responsive.css     Breakpoints: 1024px / 768px / 480px
│
├── js/
│     script.js          All interactivity (modular init functions)
│
├── images/
│     profile.jpg        Placeholder headshot (generated gradient avatar)
│     project1.png        Placeholder — Food Delivery Website
│     project2.png        Placeholder — HourlyRecruit Backend
│     project3.png        Placeholder — Binary to Decimal Converter
│     favicon.png        Site icon
│
├── assets/
│     resume.pdf         The actual uploaded resume (powers the Download
│                          Resume buttons)
│
└── README.md
```

## What's real vs. placeholder

- **Text content** — bio, education, skills, projects, and certifications
  are taken directly from the uploaded resume.
- **Skill percentages** — the resume doesn't list numeric proficiency, so
  these are reasonable estimates for visual effect. Adjust
  `data-percent` values in `index.html` (`.skill-bar__fill`) to taste.
- **Project images** — generated placeholder graphics (no real
  screenshots were provided). Swap in real ones by replacing
  `images/project1.png`, `project2.png`, `project3.png`.
- **Profile photo** — a generated placeholder avatar. Replace
  `images/profile.jpg` with a real photo (recommended: square, ≥500×500px).
- **Live Demo / GitHub buttons on projects** — link to `#` as
  placeholders. Update the `href` attributes in the Projects section of
  `index.html` once you have real URLs.
- **Social links** (GitHub / LinkedIn in the hero and footer) — point to
  placeholder URLs (`https://github.com/`, `https://linkedin.com/`).
  Replace with your actual profile URLs.
- **Contact form** — fully validated on the client (required fields,
  email format, minimum message length) but has **no backend**. To
  actually receive messages, either:
  - point the `<form>` at a service like [Formspree](https://formspree.io)
    (add `action="https://formspree.io/f/yourFormId"` and `method="POST"`), or
  - wire up your own backend endpoint and adjust `js/script.js`'s
    `initContactForm()` to send a `fetch()` request instead of just
    showing a success message.
- **Map** — embedded via a keyless Google Maps `output=embed` URL
  centered on Bengaluru (no API key required). Replace the query in the
  `iframe` `src` in `index.html` with a specific address for pinpoint
  accuracy.

## Customizing

- **Colors** — all defined as CSS variables at the top of `css/style.css`
  under `:root` (`--bg`, `--surface`, `--accent-sky`, `--accent-indigo`, etc).
- **Fonts** — Space Grotesk (headings), Inter (body), JetBrains Mono
  (code/data accents), loaded from Google Fonts in `index.html`.
- **Sections** — each section in `index.html` is commented and can be
  reordered, removed, or duplicated independently.
- **Add a new project** — duplicate a `.project-card` block in the
  Projects section, update the image, title, description, features,
  tags, and `data-tags` (used by the filter buttons).

## Features included

Dark theme, glassmorphism cards, gradient accents, animated particle
background, mouse-glow effect, custom cursor (desktop), scroll progress
bar, sticky/scroll-aware navbar with scroll-spy, mobile hamburger menu,
loading screen, hero typing animation, floating hero visuals, animated
counters, animated skill bars, scroll-reveal animations, project filter,
hover effects throughout, validated contact form, keyless map embed,
and a back-to-top button. Fully responsive down to small mobile screens
with no horizontal scrolling.

## Browser support

Modern evergreen browsers (Chrome, Firefox, Safari, Edge). Uses
`IntersectionObserver`, CSS custom properties, and `backdrop-filter` —
all widely supported, with graceful degradation where not (e.g. reduced
motion is respected via `prefers-reduced-motion`).
