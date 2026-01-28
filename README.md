# Madduru Mani Teja — Portfolio

A responsive portfolio site built with **React + Vite**, **Tailwind CSS**, and **Framer Motion**. Content is sourced from the resume only.

## Tech Stack

- **React 18** + **Vite**
- **Tailwind CSS** for styling
- **Framer Motion** for animations (text reveal, scroll fade/slide, subtle background motion)

## Features

1. **Sticky header** — Navigation: About, Skills, Gallery, Achievements, Contact
2. **Hero section** — Name, role, tagline, intro, and profile photo (animated)
3. **Skills** — From resume (Languages, AI/ML, Frontend, Database, Platforms & Tools, Behavioral)
4. **Gallery** — Profile photo with hover zoom and lightbox
5. **Achievements / Projects** — Deepfake Face Detection, Health AI Assistant; GATE, LeetCode, CodeChef, certifications
6. **Contact** — Email, GitHub, LinkedIn, phone, and resume download
7. **Responsive** — Mobile and desktop layouts

## Setup

### Prerequisites

- Node.js (v18+)
- npm or yarn

### Install and run

```bash
# Install dependencies
npm install

# Run dev server
npm run dev
```

Open `http://localhost:5173` in the browser.

### Assets (PHOTO & Resume)

The app expects **PHOTO.jpg** and **RESUME.pdf** in the `public/` folder so they are served at `/PHOTO.jpg` and `/RESUME.pdf`.

- If they are in the project root, copy them into `public/`:

  ```bash
  cp PHOTO.jpg RESUME.pdf public/
  ```

  On Windows (PowerShell):

  ```powershell
  Copy-Item PHOTO.jpg, RESUME.pdf -Destination public\
  ```

- Or move them manually into `public/`.

### Build

```bash
npm run build
```

Output is in `dist/`.

### Preview production build

```bash
npm run preview
```

---

## Deploy to Netlify

### Option A: Deploy via Netlify UI (drag & drop)

1. Build locally:
   ```bash
   npm run build
   ```
2. Open [Netlify](https://app.netlify.com) and sign in.
3. Go to **Sites** → **Add new site** → **Deploy manually**.
4. Drag and drop the **`dist`** folder into the deploy area.
5. After deploy, your site URL will be shown (e.g. `https://random-name.netlify.app`).

### Option B: Deploy via Netlify CLI

1. Install Netlify CLI:
   ```bash
   npm install -g netlify-cli
   ```
2. Build and deploy:
   ```bash
   npm run build
   netlify deploy --prod --dir=dist
   ```
3. Follow the prompts (log in, create/link site). Your live URL will be printed at the end.

### Option C: Deploy from Git (Netlify continuous deployment)

1. Push this project to a Git host (GitHub, GitLab, Bitbucket).
2. In Netlify: **Add new site** → **Import an existing project**.
3. Connect the repo and set:
   - **Build command:** `npm run build`
   - **Publish directory:** `dist`
4. Click **Deploy site**. Netlify will build and deploy on every push to the default branch.

### Important for SPA (React Router / hash routing)

This portfolio is a single-page app with sections. If you add client-side routing later, set **Redirects** in Netlify so all paths fall back to `index.html`:

- **Netlify UI:** Site → **Site configuration** → **Redirects** → add:
  - **Rule:** `/*`
  - **To:** `/index.html`
  - **Status:** `200`

- Or add a `public/_redirects` file (or `netlify.toml`) with:
  ```
  /*    /index.html   200
  ```

For this current setup (no routes), the default Netlify behavior is enough.

---

## Project structure

```
├── public/
│   ├── PHOTO.jpg      # Profile photo (copy from root if needed)
│   ├── RESUME.pdf     # Resume PDF (copy from root if needed)
│   └── vite.svg       # Favicon
├── src/
│   ├── components/
│   │   ├── Header.jsx    # Sticky nav
│   │   ├── Hero.jsx      # About / hero
│   │   ├── Skills.jsx     # Technical & behavioral skills
│   │   ├── Gallery.jsx   # Image gallery + lightbox
│   │   ├── Achievements.jsx  # Projects & certifications
│   │   └── Contact.jsx   # Email, GitHub, LinkedIn, resume
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css        # Tailwind + base styles
├── index.html
├── package.json
├── tailwind.config.js
├── postcss.config.js
└── vite.config.js
```

## Updating contact links

Resume mentions GitHub and LinkedIn but not full URLs. To add yours, edit `src/components/Contact.jsx` and set:

- `contact.github` to your GitHub profile URL (e.g. `https://github.com/yourusername`)
- `contact.linkedin` to your LinkedIn profile URL (e.g. `https://linkedin.com/in/yourusername`)

---

## License

Private portfolio. Use and modify for your own site.
