# 🌙 Night Audio Book

> An interactive bedtime storybook with text-to-speech narration. Two volumes, 31 enchanting stories each, designed for children ages 6+, featuring the hero **Amine** — and in Tome 2, his little sister **Leyla**.

## 📖 Read Now

### ⭐ Tome 1 (GitHub Pages)
**[👉 Open Tome 1 in your browser](https://theb2a.github.io/night-audio-book/livre-histoires.html)**

### ⭐ Tome 2 — with Leyla (GitHub Pages)
**[👉 Open Tome 2 in your browser](https://theb2a.github.io/night-audio-book/livre-histoires-tome2.html)**

No installation needed — hosted directly on GitHub Pages!

### Alternative Links
- **jsDelivr CDN**: https://cdn.jsdelivr.net/gh/theb2a/night-audio-book@main/livre-histoires.html (Tome 1) · https://cdn.jsdelivr.net/gh/theb2a/night-audio-book@main/livre-histoires-tome2.html (Tome 2)
- **GitHub Raw**: https://raw.githubusercontent.com/theb2a/night-audio-book/main/livre-histoires.html (Tome 1) · https://raw.githubusercontent.com/theb2a/night-audio-book/main/livre-histoires-tome2.html (Tome 2)

## Features

✨ **31 Interactive Stories**
- 11 Hero tales (6 featuring Amine as the protagonist)
- 5 Funny stories
- 8 Stories about good manners
- 7 Family-centered tales

🔊 **Text-to-Speech Narration**
- Play, pause, and resume reading at any point
- Stop and return to the menu anytime
- Automatically detects French voice on your device
- Reading stops when you turn the page

🎨 **Beautiful Illustrations**
- Animated SVG graphics for each story
- Warm, child-friendly color palette
- Dedicated hero character designs

📖 **Interactive Table of Contents**
- Jump to any story instantly
- Browse by category
- Track your reading progress

## Getting Started

### Option 1: Read from GitHub Pages (Recommended)

Click **"Open the book in your browser"** at the top of this page. The book is served directly from GitHub Pages — no installation, no setup, just instant access.

### Option 2: Open Locally

1. **Download or clone this repo:**
   ```bash
   git clone https://github.com/theb2a/night-audio-book.git
   cd night-audio-book
   ```

2. **Open `livre-histoires.html` in your browser:**
   ```bash
   # On Mac/Linux
   open livre-histoires.html

   # On Windows
   start livre-histoires.html
   ```

3. **(Optional) Serve locally to test on other devices:**
   ```bash
   python -m http.server 8000
   # Visit http://localhost:8000/livre-histoires.html
   # Or from another device: http://YOUR_IP:8000/livre-histoires.html
   ```

### How to Use

1. **Start Reading**: Click "Commencer ▶" on the cover
2. **Navigate**: Use arrow buttons or swipe left/right (on touch devices)
3. **Listen**: Click 🔊 to start audio narration
4. **Control Playback**: 
   - ⏸️ Pause — pauses the reading
   - ▶️ Resume — continues from where you left off
   - ⏹️ Stop — stops playback and returns to normal view
5. **Browse Stories**: Click 📖 Sommaire to see all stories

## Project Structure

```
.
├── livre-histoires.html         # Tome 1 (single file, no build needed)
├── livre-histoires-tome2.html   # Tome 2, with Amine & Leyla (single file, no build needed)
├── GUIDE-RAPIDE.md              # Quick modification guide
├── RAPPORT-QA.md                # Tome 1 quality assurance & validation report
├── README-CONTINUATION.md       # Development notes & feature roadmap
└── README.md                    # This file
```

## Stories Overview

### Hero Tales 🦸
- **Amine, le nouveau héros** — Amine rescues a kitten
- **Amine et l'étoile tombée** — Amine helps a fallen star
- **Super-Amine apprend à voler** — Amine discovers the power of flight
- **Amine et le bouclier des copains** — Amine protects his friends from rain
- **Amine, gardien de la nuit** — Amine comforts a scared neighbor
- **Le super-pouvoir secret d'Amine** — Kindness is the real superpower
- Plus 5 autres héros (Steve, Noobi, Goku, et plus)

### Funny Stories 😄
Tales of hiccupping creepers, flying cows, and silly dancing robots.

### Good Manners ✨
Stories about saying "thank you," sharing, waiting your turn, and more.

### Family Tales ❤️
Heartwarming stories about family bonds and togetherness.

## Tome 2 — Amine & Leyla 👧🦸

A full second volume (`livre-histoires-tome2.html`), same structure as Tome 1 (31 stories, 11/5/8/7 split), introducing Amine's 2-year-old little sister **Leyla**. 10 of the 31 stories feature them together; the rest are brand-new tales with the existing cast (Steve, Noobi, Goku, and more).

🎯 **New: Audio Progress Gauge**
- Shows live reading progress while the story is narrated aloud
- Always moves forward smoothly, even on browsers that don't support fine-grained playback events (e.g. iOS Safari)
- Reaches 100% when the story finishes

## Technology

- **Pure HTML5** — no build tools, no dependencies
- **Responsive Design** — works on desktop, tablet, and mobile
- **Web Speech API** — native browser text-to-speech (no external libraries)
- **SVG Animations** — smooth, performant graphics
- **CSS Variables** — easy theme customization

## Browser Support

✅ Chrome/Edge 80+  
✅ Firefox 75+  
✅ Safari 14+  
✅ iOS Safari 14+  
✅ Android Chrome  

## Customization

### Change a story
Open `livre-histoires.html` and find the `STORIES` array. Each story looks like:
```javascript
{cat:'hero',scene:'amine',title:'Amine, le nouveau héros',text:[
  "First paragraph.",
  "Second paragraph.",
  "..."
]}
```

### Add a new story
Add a new object to the `STORIES` array before the closing `]`. Choose a `scene` from the `SCENES` object.

### Change colors
Find the `:root` CSS block near the top and modify variables like `--night-1`, `--lamp`, `--cat-hero`, etc.

### Add your own illustration
Create a new SVG scene in the `SCENES` object:
```javascript
myNewScene(){return `<svg viewBox="0 0 200 200">...</svg>`;},
```

See `GUIDE-RAPIDE.md` for detailed modification instructions.

## Quality Assurance

This project has been validated with comprehensive testing covering:
- Data integrity (31 stories, all references valid)
- SVG rendering (22 scenes, all animations working)
- Audio controls (Play, Pause, Resume, Stop state machine)
- Navigation (page turning, sommaire, bounds checking)
- Accessibility (ARIA labels, focus states, reduced-motion support)
- Console errors (none detected)

See `RAPPORT-QA.md` for the full validation report.

## Future Ideas

- 💾 Remember reading progress across sessions
- 🎵 Ambient sounds (rain, forest, etc.)
- 📱 Progressive Web App (installable on phones)
- 🌍 Multi-language support
- 🎨 Child-customizable themes (favorite colors)
- 👨‍👩‍👧‍👦 Multi-child profiles with separate progress

## License

MIT — feel free to fork, modify, and share with your own children!

## About Amine

Amine is the brave hero of this bedtime book, designed to inspire children as they drift off to sleep. Every story celebrates kindness, courage, and the magic of helping others.

---

**Bonne nuit! Sweet dreams! 🌙**
