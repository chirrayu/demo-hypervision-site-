# UPES HyperVision — Technical Innovation Society

Official website repository for UPES HyperVision, the premier technical society of the School of Computer Science (SoCS), UPES Dehradun. Founded in 2011, HyperVision connects academic learning with industry needs through hackathons, autonomous systems research, and software engineering initiatives.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | React 19 with TypeScript |
| Build Tool | Vite 8 |
| Styling | Tailwind CSS v4 |
| Animation | Motion (Framer Motion successor) |
| Icons | Lucide React |
| Runtime | Node.js with Express (for server-side concerns) |
| Language | TypeScript 7 |

---

## Project Structure

```
.
├── public/
│   ├── events/          # Event photography (webp)
│   ├── gallery/         # Campus life gallery images
│   ├── sponsors/        # Partner and sponsor logos
│   └── team/            # Team member profile photos
├── src/
│   ├── components/      # All page section components
│   ├── data/
│   │   └── hypervisionData.ts   # Single source of truth for all site content
│   └── assets/
│       └── scraped/     # Raw scraped assets used during development
├── index.html
├── vite.config.ts
└── .env.example
```

---

## Getting Started

```bash
# Install dependencies
npm install

# Start local development server (port 3000)
npm run dev

# Type-check without emitting
npm run lint

# Build for production
npm run build
```

---

## Changes Made Compared to the Live Site (upeshypervision.in)

The following sections describe every material difference between this rebuilt codebase and the original production site at [upeshypervision.in](https://www.upeshypervision.in/).

### 1. Complete Technology Migration

The original site appears to be a static or minimally dynamic HTML/CSS/JS website. This repository is a full React 19 + TypeScript single-page application built with Vite, using component-based architecture throughout. Every section is a discrete React component with typed props, state management, and lifecycle hooks.

### 2. Centralized Data Layer

All site content — team members, events, projects, sponsors, milestones, statistics, and capabilities — is consolidated in a single typed data file: `src/data/hypervisionData.ts`. The original site has its content embedded directly in markup. This separation means any content update (new team member, new event) requires editing only one file, not hunting through HTML.

### 3. Animated Particle Network Hero Section

The Hero section features a custom canvas-based particle animation written entirely in vanilla Canvas2D API. It renders a cybernetic particle network where:

- Particles pulse with varying alpha and glow effects
- Mouse cursor interaction repels nearby particles in real time
- Particles connect to each other and to the cursor position via luminous filaments
- The particle count scales responsively with viewport width

The original site has a static hero background without interactive animation.

### 4. Glassmorphism Design System

A consistent glassmorphism visual system runs across every component, implemented via Tailwind utility classes and custom CSS tokens:

- `glass-card` — interactive card with hover glow and border shimmer
- `glass-card-static` — non-interactive frosted panel
- `glass-pill` — small badge and tag style with backdrop blur
- `glass-nav` — sticky navbar that applies blur only after scroll threshold
- `glass-modal` — modal overlay with deep frosted glass background
- `glass-input` — form input with dark glass surface styling

None of these treatments exist in the original site.

### 5. Interactive Project Cards with Modal Inspector

The Featured Work (Projects) section renders project cards in an asymmetric editorial 12-column grid. Clicking any card opens a full frosted-glass modal inspector that shows:

- Full project overview and system architecture description
- Production benchmark metrics
- Complete technology stack as pill tags
- Links to the live platform and the GitHub repository

The original site does not have a dedicated projects section with this level of detail.

### 6. Events Section with Category Filtering and Photo Lightbox

The Events section is split into two switchable tabs:

**Flagship Events tab:**
- A large hero card for the next upcoming event with date, location, participant count, and a direct registration link
- A filterable archive grid of past events, filterable by category (hackathon, bootcamp, symposium, workshop)
- Clicking any past event card opens a frosted-glass modal with full event description, metadata table, and a gallery thumbnail grid for that event's photos

**Milestones tab:**
- A vertical timeline tracing HyperVision's history from 2011 to the present, with year markers, milestone titles, and descriptive narrative for each node

### 7. Live Countdown Clock and Editable Upcoming Event Panel

The Join / Upcoming Event section includes a real-time countdown clock (days, hours, minutes, seconds) that calculates live against a configurable target date. The event panel (title, subtitle, badge, venue, prize pool, tracks, registration URL) is editable in-browser via a form modal. Changes persist to `localStorage` so they survive page refresh without a redeployment. A reset button restores the default event data.

This feature does not exist on the original site.

### 8. Membership Application Modal

A full membership application form is accessible from the Hero CTA and other call-to-action buttons throughout the site. The form collects:

- Full name, UPES SAP ID, and student email
- Academic year (1st Year through Postgraduate)
- Primary domain of interest (AI/ML, Robotics, Web Systems, Cybersecurity, Design, Operations, PR)
- GitHub, portfolio, or LinkedIn URL
- Motivational statement

On submission, the form validates required fields, generates a reference ID in the format `HV-XXXXXX`, and displays a confirmation screen. The application is reviewed by faculty and domain leads.

### 9. Gallery with Full-Screen Lightbox Navigation

The Campus Life and Gallery section renders a 3-column image grid. Clicking any image opens a full-screen lightbox with:

- Keyboard-navigable previous and next buttons (ChevronLeft / ChevronRight)
- Image caption with tag, title, and description
- Counter showing current image position out of total (e.g., `3 / 6`)
- Click-outside-to-close behavior

### 10. Partners and Sponsors Section with Structured Tiers

Six partners are displayed with their real logos (scraped and locally hosted as `.webp` files), category labels, tier designations, and descriptions. Partner logos render in grayscale by default and transition to full color on hover. Partners included:

- Decathlon (Flagship Sponsor)
- GeeksforGeeks (Ecosystem Partner)
- NIT Kurukshetra (Strategic Research)
- W3Grads (Educational Partner)
- WICCI (Outreach Partner)
- Runaway (Creative Partner)

### 11. Sticky Scroll-Aware Navbar with Mobile Drawer

The navbar is transparent with no background at the top of the page. Once the user scrolls past 20px, it adopts the `glass-nav` style (dark backdrop blur with border). On mobile viewports, nav links collapse into a full-width drawer that slides open from the hamburger icon. The desktop nav links are enclosed in a `glass-pill` container.

### 12. Capability Bento Grid

The What We Do section displays six engineering disciplines in a 3-column bento grid. Each card shows an icon, a numbered identifier, a title, a description, and a comma-separated technology list as unboxed metadata. Cards have hover state color transitions on icons, titles, and technology tags. The six disciplines are:

1. AI and Machine Learning
2. Autonomous Robotics and Drone Tech
3. Distributed Web and Cloud Systems
4. Cybersecurity and Systems Hardening
5. DevOps and Cloud Infrastructure
6. Competitive Programming and Mentorship

### 13. Statistics Bar with Real Data

The About section includes a 6-column statistics grid with the following verified figures:

| Metric | Value |
|---|---|
| Active Members | 100+ |
| Projects Completed | 50+ |
| Events Organized | 30+ |
| Industry Partners | 15+ |
| SIH Teams Arbitrated | 330+ |
| Founded | 2011 |

### 14. Team Section with Role Hierarchy and Social Links

The Team section organizes members into labelled clusters: Faculty, Executive Board, Strategic Directorate, Design, Technical, Editorial, Social Media, Events, PR and Outreach, and Operations. Each member card shows name, role, department, initials avatar (fallback when no photo), and links to LinkedIn and GitHub where available. The current roster spans 26 named members.

### 15. Image Assets Converted to WebP

All images — event photos, gallery images, team portraits, and sponsor logos — are stored as `.webp` files in the `public/` directory. WebP provides significantly smaller file sizes compared to the JPEG and PNG formats used on the original site. Images are also loaded with `loading="lazy"` and `decoding="async"` attributes throughout.

### 16. Accessibility and Focus Management

Focus-visible ring outlines using `focus-visible:ring-2 focus-visible:ring-cyan-400` are applied to all interactive elements (links, buttons, inputs). Modals set `role="dialog"` and `aria-modal="true"`. Decorative elements use `aria-hidden="true"`. The gallery lightbox uses descriptive `aria-label` attributes on navigation buttons.

---

## Content That Matches the Original Site

- Society name, tagline, and founding year (2011)
- Campus location: School of Computer Science (SoCS), UPES Bidholi Campus, Dehradun
- Contact email: upes.hypervision@stu.upes.ac.in
- Social links: LinkedIn, Instagram, GitHub
- Core events: Code Hustle, SIH Internal Round, Drone Tech Bootcamp, Pehchaan, Avritti, Code Connect
- Faculty advisors: Dr. Virender Kadyan and Dr. Bhavana Kaushik
- National initiative: MeitY SwaYaan collaboration with NIT Kurukshetra

---

## Contact

**Email:** upes.hypervision@stu.upes.ac.in  
**LinkedIn:** https://www.linkedin.com/in/upeshypervision/  
**Instagram:** https://www.instagram.com/upeshypervision/  
**GitHub:** https://github.com/upes-hypervision  
**Code Hustle Live Platform:** https://code-hustle-11.vercel.app/
#   d e m o - h y p e r v i s i o n - s i t e -  
 