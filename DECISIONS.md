# Decisions

## 2026-11-17 — Everything runs in the browser
- **Chosen:** one `index.html`, no server, no libraries. Files and the webcam never leave the visitor's device.
- **Why:** privacy (people drop personal photos and their face), free hosting on Vercel, and anyone can download the file and use it offline.
- **Rejected:** server-side conversion (costs money, and would mean storing people's pictures).

## 2026-11-17 — GIFs need ImageDecoder; no silent fallback
- **Chosen:** decode GIF frames with the browser's `ImageDecoder` (Chrome, Edge). Where it's missing (Firefox), show a clear message suggesting Chrome/Edge or MP4.
- **Why:** drawing a GIF any other way only gives its first frame, which would look like a bug.
- **Rejected:** bundling a GIF decoder library (adds code to maintain for one browser).

## 2026-11-17 — Public repo + Vercel
- **Chosen:** public GitHub repo `Allouche-Adam/ascii-lab`, deployed on Vercel; credit and links to the author in the page.
- **Affects:** the share picture (`og.png`) needs the site's full address in `og:image`.
