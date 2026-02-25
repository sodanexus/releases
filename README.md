# 🎵 VIQ – Release Landing Page Generator

Internal tool to generate music release landing pages, ready to be uploaded to GitHub Pages in seconds.

---

## 🚀 Features

### 🛠 Generator

- **Auto-fill links** via the Odesli API — paste a Spotify (or other platform) link and all platform links are filled automatically  
- **12 supported platforms**: Spotify, Apple Music, YouTube, YouTube Music, Deezer, SoundCloud, Amazon Music, Tidal, Bandcamp, Pandora, Anghami, Store  
- **Cover optimization** — automatic resize to 1000×1000px JPEG on import, with preview  
- **Dominant color extraction** — the primary color of the cover is automatically extracted and injected into the landing page and OG image  
- **OG image generation** — a 1200×630px image is automatically generated for Discord, Facebook, Twitter/X  
- **Live preview** — the landing page and OG update in real time without regenerating  
- **Auto slug** — generated from the song title, customizable  
- **URL validation** — green/red visual indicator for each link  
- **URL cleaning** — automatic removal of tracking parameters (utm, etc.) on blur  
- **Config duplication** — clone a page while keeping artist + social links, clearing title + release links  
- **ZIP export** — generates a `[slug]/` folder containing `index.html`, `cover.jpg`, and `og.jpg`  
- **Drag & drop** support for the cover area  

---

### 🌐 Generated Landing Page

- **Animated particles** floating upward, tinted with the cover’s primary color  
- **Entry animation** on the cover (zoom + fade)  
- **Hover zoom** effect on the cover  
- **Responsive layout** — optimized for mobile and desktop  
- **Dynamic background** — blurred cover in background with dark overlay  
- **Share button** — native on mobile (Web Share API), link copy fallback  
- **Social links** — Instagram, TikTok, Facebook, website  
- **Favicon** = release cover  
- **Full Open Graph tags** — `og:image`, `og:title`, `og:description`, `twitter:card`, `canonical`

---

### 🖼 OG Image

- Cover aligned to the right edge, softly faded on the left  
- Background = blurred cover across the entire image  
- Artist name large (serif), title in light weight  
- Decorative line in the primary color  
- Release type in spaced lettering  
- Gradient color bar at the bottom  
- Subtle `viqmusic.net` domain at bottom left  

---

## 📦 Generated ZIP Structure

[slug]/
├── index.html       # Complete landing page
├── cover.jpg        # Optimized 1000×1000 cover
└── og.jpg           # 1200×630 OG image for social sharing

---

## 🚀 Deployment

1. Generate the ZIP from the generator  
2. Unzip and upload the `[slug]/` folder into the `releases` GitHub repository  
3. The page goes live at: https://go.viqmusic.net/[slug] 

---

## 🧠 Stack

Vanilla HTML / CSS / JavaScript  
Zero server dependencies. Zero frameworks.

Libraries used:
- `JSZip` — client-side ZIP generation  
- `Odesli API` via `cloudflare.com` — link auto-fill  
- `SimpleIcons CDN` — platform logos  

---

## ⚠️ License

© 2026 VIQ — All Rights Reserved.
