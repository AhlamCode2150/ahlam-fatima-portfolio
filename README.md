# hello, i'm ahlam. 🏎️💫

A single-page personal portfolio with a Y2K aesthetic and a Formula 1 obsession baked into every corner — chrome gradients, scanlines, checkered borders, and a scroll experience animated with GSAP.

**Live site:** https://ahlamcode2150.github.io/ahlam-fatima-portfolio/

## Sections

- **About** — a short intro, and a webcam-framed photo slot
- **Things I care about, unfortunately** — the "unfortunately.log" of interests
- **Certified giggles** — a meme wall pulling fresh posts live from [meme-api.com](https://meme-api.com)
- **The webcam booth** — `blurry_flash_cam.exe`: takes a photo through the browser camera and saves it to a personal strip, stored locally in the browser (nothing is uploaded anywhere)
- **Race calendar** — `lights_out.ics`: an F1-style race schedule laid out like a countdown board

## Tech stack

- Plain HTML/CSS/JS — no build step, no framework, no dependencies to install
- A small component templating layer (`support.js` + `image-slot.js`) that powers the reactive bits (`<sc-if>`, `<sc-for>`, live state) directly in the browser
- [GSAP](https://gsap.com/) + ScrollTrigger for scroll-driven animation, loaded from a CDN
- Google Fonts: Anton, Bebas Neue, Space Mono
- Browser `getUserMedia` for the webcam booth, `localStorage` for saving snapshots client-side
- [meme-api.com](https://meme-api.com) for the live meme feed

## Running locally

No build tools needed — it's static. Just serve the folder so the relative script paths and camera permissions work correctly (opening the file directly via `file://` will block the webcam):

```bash
npx serve .
# or
python -m http.server 8000
```

Then open the printed local URL in your browser.

## Project structure

```
.
├── index.html       # the entire site
├── support.js       # component/templating runtime
├── image-slot.js    # image drop-in component
├── assets/          # static images
└── uploads/         # user-dropped images
```

## Notes

- The webcam booth and meme feed both make requests from the visitor's own browser (camera access and the meme API call) — nothing routes through a backend, since there isn't one.
- Built and iterated on as a personal design project — expect Y2K chrome, scanlines, and a lot of Space Mono.
