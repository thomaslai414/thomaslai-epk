# Thomas Lai — Official Website

Official website for Thomas Lai, a Taiwanese-Canadian theatrical, maximalist pop artist from Montréal. Features music, live performances, postcards, press materials, and an innovative dynamic sky system.

**Live:** [thomaslaimusic.com](https://www.thomaslaimusic.com)

---

## 🌅 Design System: "Open Sky"

The site centers around a **living sky** that responds to your local time, creating a unique visual experience that evolves throughout the day. The sky shifts through five states — Dawn, Day, Golden Hour, Dusk, and Night — each with its own color palette and atmospheric effects.

### Sky States

- **Dawn** (5:00–7:30 AM): Soft pastels, glacial blues with warm accents
- **Day** (7:30 AM–5:00 PM): Bright, fresh sky blues and whites
- **Golden Hour** (5:00–6:30 PM): Warm, nostalgic palette (identical to dawn visually)
- **Dusk** (6:30–9:30 PM): Deep purples and teals, ferris wheel bulbs illuminate
- **Night** (9:30 PM–5:00 AM): Navy and deep indigo with aurora effects

### Interactive Elements

- **Living Canvas**: Dynamic background that updates based on your system time or manual control
- **Atmospheric Effects**: 
  - Birds that react to cursor movement
  - Windborne motes that drift naturally
  - Twinkling stars visible at night
  - Shooting stars after dark
- **Paper Design**: Postcards and UI elements maintain consistent paper aesthetic across all sky states
- **Sky Control**: Users can manually override time or sync to live local time

---

## 📁 Repository Structure

```
index.html              # Main SPA: Home, Music, Live, Shop, About, Press
links/index.html        # Streamlined link hub (alternative entry point)
images/                 # Asset directory (photos, sky gradients, covers, etc.)
CNAME                   # Custom domain configuration (thomaslaimusic.com)
README.md               # This file
```

### Main Site (`index.html`)

A single-page application (~72KB) with all content, styles, and scripts embedded. Includes:

- **Navigation**: Smooth client-side routing to 6 main pages
- **Home**: Hero section with ferris wheel animation, announcements, newsletter signup
- **Music**: Debut single "Ferris Wheel Romance" with streaming links & embedded player
- **Live**: Performance gallery, audio player, tour dates
- **Shop**: Free digital postcard collection with email signup
- **About**: Artist bio, influences, story
- **Press**: Electronic Press Kit (EPK), one-sheets, photos, audio assets

**Features:**
- Fully responsive (mobile-first, fluid typography with `clamp()`)
- Accessible (semantic HTML, focus states, ARIA labels)
- Modern CSS Grid & Flexbox layouts
- Canvas-based sky rendering with interactive controls
- CSS custom properties for easy customization
- **Cart system** for postcards (visual feedback, toast notifications)

### Links Hub (`links/index.html`)

A lightweight alternative landing page (~29KB) perfect for:
- Social media bio links
- QR code destinations
- Streamlined access to all platforms in one place

**Features:**
- Collapsible "vinyl record" streaming service card
- Social profile links (Spotify, Apple Music, YouTube, Instagram, TikTok)
- Email newsletter signup
- Same sky system as main site
- Minimal, touch-friendly design

---

## 🎨 Design System

### Typography

- **Display**: Abril Fatface (serif) — headlines, hero text
- **Body**: Hanken Grotesk (sans-serif) — body copy, UI
- **Labels**: Space Mono (monospace) — tags, metadata
- **Handwriting**: Caveat (cursive) — postcards, signatures

### Color Palette

**Core Colors:**
- `--cobalt: #2E63D8` — Primary action, buttons
- `--blue: #2C5BA8` — Postal ink, secondary accents
- `--teal: #57C7E3` — Glacial accent
- `--gold: #F2B64B` — Ferris wheel bulbs

**Paper Colors:**
- `--paper: #FFFDF6` — Off-white
- `--cream: #FFF6E8` — Warm cream
- `--kraft: #EFE3CB` — Kraft paper brown

**Dynamic (changes per sky state):**
- `--ink` — Text color (adapts from dark to light across states)
- `--ink-dim` — Secondary text
- `--chrome` — Glass/frosted effect (backdrop blur)
- `--accent-soft` — Context-aware accent color

---

## ✨ Key Features

### Music Integration

- **Streaming Buttons**: One-click access to Spotify, Apple Music, YouTube, TIDAL, Pandora, Boomplay, iTunes, Yandex Music
- **Audio Player**: Embedded Spotify playlist
- **WAV/A Cappella**: Available on request for press/sync

### Community & Engagement

- **Newsletter**: beehiiv embed for free postcard collection
- **Postcards**: Digital collection with lore tied to album cycle
- **Email Signup**: Incentivized with "collectable digital postcards"

### Accessibility

- Semantic HTML structure
- Focus-visible outlines on all interactive elements
- Sufficient color contrast across all sky states
- Proper heading hierarchy (h1 → h6)
- ARIA labels for buttons, landmarks
- Works with `prefers-reduced-motion`

### Performance

- Self-contained HTML (no external dependencies except fonts & embeds)
- WebP images with JPEG fallbacks
- Lazy loading for images
- Smooth scroll behavior
- Optimized Canvas API for sky effects

---

## 🎯 Content Pages

| Page | Purpose | Key Elements |
|------|---------|---|
| **Home** | Landing & announcements | Hero, ferris wheel SVG, dispatch cards, newsletter signup |
| **Music** | Single release hub | Album art, credits, streaming buttons, embedded player |
| **Live** | Performance showcase | Stage photos, audio recordings, tour dates |
| **Shop** | Postcard collection | Digital postcard previews, email signup CTA |
| **About** | Artist bio | Portrait, bio text, influences, personal story |
| **Press** | Media kit & EPK | One-sheets, photos, audio assets, press contact |

---

## 🌐 Browser Support

- Modern ES6+ JavaScript (no transpilation)
- CSS Grid & Flexbox
- CSS Custom Properties (variables)
- Canvas API for sky rendering
- WebP with fallbacks
- Mobile: iOS Safari 13+, Chrome Android

**Recommended:** Latest 2 versions of Chrome, Safari, Firefox, Edge

---

## 🔧 Customization

### Changing Sky Colors

Edit the `:root` CSS variables in `index.html` (lines 12–31):

```css
:root{
  --cobalt:#2E63D8;       /* primary action */
  --blue:#2C5BA8;         /* postal ink blue */
  --teal:#57C7E3;         /* glacial teal */
  --gold:#F2B64B;         /* ferris wheel bulbs */
  /* ... etc */
}
```

### Modifying Sky States

Update the `SKIES` and `SKY_IMG` objects in the JavaScript section to adjust colors and background images per time of day.

### Adding New Pages

All pages are defined as `.page` sections within `main`. Add a new section and register it in the routing logic (`data-page` attribute and nav link).

### Updating Streaming Links

In `links/index.html`, edit the `FWR_LINKS` object (lines 246–255) with your streaming URLs:

```javascript
const FWR_LINKS = {
  spotify : 'https://...',
  apple   : 'https://...',
  // ...
};
```

---

## 📊 Analytics & Third-Party

- **Newsletter**: beehiiv embed (https://beehiiv.com)
- **Music**: Spotify & Apple Music embeds
- **Analytics**: None currently (can be added via GTM or similar)

---

## 🚀 Deployment

The site is deployed via GitHub Pages. The `CNAME` file points to a custom domain (`thomaslaimusic.com`).

**To deploy locally or redeploy:**

1. Simply serve `index.html` (no build step needed)
2. All assets must be in the `/images/` directory
3. `/links/index.html` serves independently at `/links/`

---

## 📝 Credits & Copyright

- **Design & Development**: Thomas Lai
- **Art Direction**: Theatrical, maximalist pop aesthetic
- **Debut Single**: "Ferris Wheel Romance" (April 17, 2026)
- **Label**: Independent (CanCon: MALP)

All content and design are proprietary. © 2026 Thomas Lai · Montréal · All rights reserved.

---

## 📮 Contact

- **Press & Inquiries**: [thomaslaimusic@gmail.com](mailto:thomaslaimusic@gmail.com)
- **Newsletter**: [thomaslaimusic.beehiiv.com](https://thomaslaimusic.beehiiv.com)
- **Social**: [@thomaslaimusic](https://instagram.com/thomaslaimusic)

---

**More about Thomas Lai:**  
Theatrical, maximalist pop from Montréal. Stream music, explore performances, discover free postcards, and connect at [thomaslaimusic.com](https://www.thomaslaimusic.com).
