# Thomas Lai Official Site

Welcome to the source code for **thomaslaimusic.com**, the official web presence of Thomas Lai, a theatrical maximalist pop artist from Montréal, Canada.

**[→ Visit the live site](https://www.thomaslaimusic.com)**

---

## Overview

This is a **self-contained, single-page application** built with vanilla HTML, CSS, and JavaScript. No build tools, no frameworks, no dependencies—just clean, performant code that works in every modern browser.

The site centers around a **living sky** that reflects your local time of day, creating a dynamic, immersive visual experience. Beyond the sky, you'll find music streaming links, live performance galleries, a digital postcard collection, and a full electronic press kit.

---

## ✨ Key Features

### 🌅 **Living Sky System**

The background updates automatically based on your local time, cycling through five states:

| State | Time | Palette | Vibe |
|-------|------|---------|------|
| **Dawn** | 5:00–7:30 AM | Glacial blues + warm pastels | Soft, awakening |
| **Day** | 7:30 AM–5:00 PM | Fresh sky blues + whites | Bright, energetic |
| **Golden Hour** | 5:00–6:30 PM | Warm, nostalgic tones | Reflective glow |
| **Dusk** | 6:30–9:30 PM | Deep purples + teals | Theatrical twilight |
| **Night** | 9:30 PM–5:00 AM | Navy + deep indigo | Starlit, mysterious |

**Interactive Elements:**
- Twinkling stars (night only)
- Shooting stars (dusk & night)
- Animated birds (day only)
- Floating motes (all states)
- Tap the "LIVE SKY" button to preview any state manually
- Works with `prefers-reduced-motion` for accessibility

### 🎵 **Music Hub**

- **Debut Single**: "Ferris Wheel Romance" (April 17, 2026)
- Streaming buttons for 8+ platforms (Spotify, Apple Music, TIDAL, YouTube, etc.)
- Embedded audio player
- Full credits and production details

### 📮 **Newsletter & Postcards**

- beehiiv-powered email signup
- Free digital postcard collection tied to the album cycle
- No spam, unsubscribe anytime

### 🎬 **Performance Gallery**

- Live photos and stage recordings
- Audio snippets from recent performances
- Tour date announcements

### 🎁 **Shop**

- Digital postcard previews
- Email signup incentivized by exclusive artwork

### 🗂️ **Press Kit (EPK)**

- One-sheets
- High-res photos
- Audio assets (WAV on request)
- Media contact info

### 🔗 **Link Hub** (`/links/`)

A lightweight alternative landing page perfect for:
- Social media bios
- QR codes
- All platforms in one minimal page

---

## 📁 Repository Structure

```
index.html              # Main SPA (single-page app)
links/index.html        # Lightweight link hub alternative
images/                 # Assets (photos, sky backgrounds, album art, etc.)
CNAME                   # Custom domain file (thomaslaimusic.com)
README.md               # This file
```

### Main Site (`index.html`)

A ~72 KB fully self-contained HTML file with:
- All CSS (inline `<style>`)
- All JavaScript (inline `<script>`)
- Semantic structure
- Responsive mobile-first layout
- Smooth client-side routing to 6 pages

**Pages:**
1. **Home** — Hero with ferris wheel animation, announcements, newsletter
2. **Music** — Streaming links, player, credits
3. **Live** — Performance photos & audio
4. **Shop** — Digital postcards
5. **About** — Artist bio and story
6. **Press** — EPK, one-sheets, assets

### Links Hub (`links/index.html`)

A ~29 KB streamlined alternative with:
- All streaming service links
- Social media buttons
- Newsletter signup
- Same living sky as main site
- Touch-friendly design

---

## 🎨 Design

### Typography

| Use | Font | Weight | CSS Variable |
|-----|------|--------|---|
| Headlines, hero | Abril Fatface | 400 | `--display` |
| Body text, UI | Hanken Grotesk | 300–700 | `--body` |
| Labels, metadata | Space Mono | 400, 700 | `--mono` |
| Postcards, signatures | Caveat | 500, 600 | `--hand` |

All fonts are loaded from Google Fonts with preconnect hints for performance.

### Color Palette

**Static Colors:**
- `--cobalt: #2E63D8` — Primary actions, buttons
- `--blue: #2C5BA8` — Postal ink, secondary accents
- `--teal: #57C7E3` — Glacial accent
- `--gold: #F2B64B` — Ferris wheel bulbs, highlights
- `--paper: #FFFDF6`, `--cream: #FFF6E8`, `--kraft: #EFE3CB` — Paper backgrounds

**Dynamic (changes per sky state):**
- `--ink` — Text color (dark or light depending on sky)
- `--ink-dim` — Secondary text
- `--accent-soft` — Context-aware accent
- `--chrome`, `--chrome-line` — Glassmorphic effects
- `--shadow` — Adaptive drop shadow

---

## ⚡ Performance & Accessibility

### Performance

- **Zero dependencies** — no npm, no build step, no JavaScript framework
- **Self-contained** — all CSS and JS inline (single HTTP request)
- **WebP + fallbacks** — modern image format with JPEG backups
- **Lazy loading** — images load on demand
- **Canvas optimization** — efficient sky rendering at 60 FPS
- **File size** — main site ~72 KB, links hub ~29 KB

### Accessibility

- Semantic HTML5 structure
- Focus-visible outlines on all interactive elements
- Sufficient color contrast across all sky states
- Proper heading hierarchy (h1 → h6)
- ARIA labels for buttons and landmarks
- `prefers-reduced-motion` support (disables animations)
- Mobile-friendly touch targets

---

## 🔧 How to Customize

### Change Sky Colors

Edit the CSS variables in the `<style>` block (around line 12):

```css
:root {
  --cobalt: #2E63D8;
  --blue: #2C5BA8;
  --teal: #57C7E3;
  --gold: #F2B64B;
  /* ... etc */
}
```

### Modify Sky States & Timing

In the `<script>` block, update the `SKIES` and `SKY_IMG` objects:

```javascript
const SKIES = {
  dawn:   ['#8FA8E8', '#D9A8C8', '#FFE6D6'],
  day:    ['#5FA9EE', '#9FCFF6', '#EAF6FF'],
  golden: ['#8FA8E8', '#D9A8C8', '#FFE6D6'],
  dusk:   ['#262B6E', '#4A5AA8', '#3D7A9E'],
  night:  ['#040A1E', '#0B1733', '#13233F']
};
```

Adjust the `stateForMinutes(m)` function to change time boundaries.

### Update Streaming Links

In `links/index.html`, find the `FWR_LINKS` object and update URLs:

```javascript
const FWR_LINKS = {
  spotify: 'https://open.spotify.com/...',
  apple: 'https://music.apple.com/...',
  // ... etc
};
```

### Add or Remove Pages

1. Add a new `<section class="page" data-page="your-page">` in the HTML
2. Add a link in the navigation with `data-goto="your-page"`
3. Style with CSS as needed

---

## 🌐 Browser Support

**Requires:**
- ES6+ JavaScript (no transpilation)
- CSS Grid & Flexbox
- CSS Custom Properties (variables)
- Canvas API
- WebP image format (with JPEG fallbacks)

**Tested & Recommended:**
- Chrome/Edge: Latest 2 versions
- Firefox: Latest 2 versions
- Safari/iOS Safari: 13+
- Mobile browsers: Android Chrome, iOS Safari

---

## 📊 Technical Stack

| Layer | Technology |
|-------|-----------|
| **Markup** | HTML5 semantic |
| **Styling** | CSS3 (Grid, Flexbox, custom properties, backdrop-filter) |
| **Script** | Vanilla JavaScript (ES6+, Canvas API) |
| **Fonts** | Google Fonts (preconnect for performance) |
| **Images** | WebP + JPEG fallbacks, lazy loading |
| **Embeds** | beehiiv (newsletter), Spotify (player) |
| **Deployment** | GitHub Pages + custom domain (CNAME) |

---

## 🚀 Deployment

The site is hosted on **GitHub Pages** and points to a custom domain via the `CNAME` file.

**To serve locally:**

```bash
# Option 1: Python
python3 -m http.server 8000

# Option 2: Node (http-server)
npx http-server

# Option 3: Ruby
ruby -run -ehttpd . -p8000
```

Then open `http://localhost:8000`

**To deploy:**
1. Push changes to the `main` branch
2. GitHub Pages automatically builds and deploys
3. Changes are live at thomaslaimusic.com in ~60 seconds

---

## 📝 Credits

- **Design & Development**: Thomas Lai
- **Creative Direction**: Theatrical maximalist pop aesthetic
- **Debut Single**: "Ferris Wheel Romance" (April 17, 2026)
- **Label**: Independent (CanCon: MALP)

---

## 📮 Contact

- **Email**: thomaslaimusic@gmail.com
- **Instagram**: [@thomaslaimusic](https://instagram.com/thomaslaimusic)
- **Newsletter**: [thomaslaimusic.beehiiv.com](https://thomaslaimusic/newsletter)
- **Website**: [thomaslaimusic.com](https://thomaslaimusic.com)

---

**Thomas Lai** is a theatrical, maximalist pop artist from Montréal. Explore his music, discover postcards, and experience the living sky at [thomaslaimusic.com](https://thomaslaimusic.com).
