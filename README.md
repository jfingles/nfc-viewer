# Data Viewer – Offline, serverless viewer for NFC/QR payloads

This repo hosts `viewer.html`, a single-file page that turns the URL hash into a `data:` URL and displays it.
It supports **Base64** (`#b64=`) and **percent-encoded text** (`#t=`) with an optional `?type=` media type.
Works great for NFC tags or QR codes where you want the phone to open content without any server.

- **Serverless & offline**: the payload lives in the URL **hash** and never reaches the hosting server.
- **Flexible media**: images, audio, video, SVG, HTML, JSON… (set `?type=` accordingly).
- **Safe by default**: includes a restrictive CSP, no analytics, no external requests.

## Quick start (GitHub Pages)
1. Put `viewer.html` in your repo and enable **Settings → Pages → Deploy from a branch** (e.g., `main` / root).
2. Open: `https://<user>.github.io/<repo>/viewer.html`

## Usage
- Text/HTML (percent-encoded):
  `https://.../viewer.html#t=%3Ch1%3EHello%3C%2Fh1%3E`
- Binary (Base64):
  `https://.../viewer.html?type=image/png#b64=<BASE64>`
  (use `type=audio/mp4`, `image/svg+xml`, etc. as needed)

> Tip: keep URLs reasonably short; for larger payloads prefer `#b64=...`.
