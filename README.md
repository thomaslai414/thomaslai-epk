# Thomas Lai — Official Site

A theatrical, maximalist pop experience from Montréal. This is the official website showcasing music, live performances, free postcards, and press materials.

## 🌅 Design System: "Open Sky"

This site features a unique dynamic design philosophy centered around a **living sky** that responds to the visitor's local time. The canvas continuously transforms throughout the day—from dawn, through golden hour, into dusk, and finally the night sky with aurora effects.

### Visual Elements

- **Sky States**: Dawn → Day → Golden Hour → Dusk → Night (with aurora)
- **Living Canvas**: 
  - Birds that bank away from your cursor
  - Windborne motes that scatter like seeds
  - Deep field of constellating stars that respond to your hand
  - Shooting stars after dark
- **Paper Objects**: Postcards and stamps maintain their paper colors across all lighting conditions
- **Color Palette**: 
  - Glacial blues and teals for ink
  - Ferris wheel bulbs (warm gold) that illuminate at dusk
  - Paper whites and cream backgrounds

## 🎨 Typography

- **Display**: Abril Fatface (serif)
- **Body**: Hanken Grotesk (sans-serif)
- **Labels**: Space Mono (monospace)
- **Handwriting**: Caveat (cursive)

## 📁 File Structure

```
index.html          # Single-page application with all content & styles
```

The entire site is built as a self-contained HTML file with embedded CSS and JavaScript for maximum portability and performance.

## ✨ Features

### Music & Performance
- Debut single "Ferris Wheel Romance" showcase
- Live performance gallery with interactive lighting
- "Listen Live" section for audio streaming

### Community
- Free postcard collection
- Press materials and EPK information
- Newsletter integration via beehiiv embed

### Interactive Elements
- Responsive navigation with smooth scrolling
- Dynamic sky canvas with real-time computation
- Hover effects on images and buttons
- Focus-visible states for accessibility
- Cart functionality with visual feedback

## 🌐 Browser Support

The site uses modern CSS and JavaScript features:
- CSS Grid & Flexbox for layout
- CSS custom properties (variables)
- Canvas API for interactive sky rendering
- Modern ES6+ JavaScript

## 🎯 Key Pages

- **Home**: Landing page with hero imagery and sky
- **Music**: Single releases and audio player
- **Live**: Performance photos and venue information
- **Shop**: Postcard collection and merchandise
- **Press**: EPK and media materials

## 📱 Responsive Design

The site is fully responsive with:
- Fluid typography using `clamp()` for scale
- Mobile-first navigation with horizontal scrolling for links
- Touch-friendly button sizing
- Adaptive grid layouts

## 🔧 Customization

### Changing Sky Colors
Edit the CSS variables in the `:root` selector:
```css
--cobalt: #2E63D8;        /* primary action */
--blue: #2C5BA8;          /* postal ink blue */
--teal: #57C7E3;          /* glacial teal */
--gold: #F2B64B;          /* ferris wheel bulbs */
```

### Updating Sky States
Modify the `body[data-sky="..."]` selectors to change how colors adapt to time of day.

### Adding Content
All content is contained within semantic HTML sections that can be easily duplicated and modified.

## ♿ Accessibility

- Semantic HTML structure
- Focus-visible outlines on interactive elements
- Sufficient color contrast across all sky states
- Proper heading hierarchy
- ARIA-compliant button states

## 📄 License

This website is the official Thomas Lai online presence. All content and design are proprietary.

---

**More about Thomas Lai:**  
Theatrical, maximalist pop from Montréal. Stream music, explore performances, and connect with the work at this site.
