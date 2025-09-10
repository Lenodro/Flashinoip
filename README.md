# Flashino PWA

Eine kleine Web App für Schüler: IP eingeben und die Seite im App-Fenster öffnen (PWA, Standalone).

## Features
- IP-Eingabe und Laden der Zielseite im iframe
- PWA: installierbar, erkennt Standalone-Modus
- Hinweis zum „Zum Home-Bildschirm hinzufügen“ auf iOS
- App-Shell-Caching via Service Worker

## Ordnerstruktur
- `index.html` – UI und Logik
- `manifest.webmanifest` – PWA-Manifest
- `sw.js` – Service Worker
- `assets/` – Logo und Icons

## Entwicklung
- Lokalen Server starten, z. B.:
  - Python: `python3 -m http.server 5173`
  - Node: `npx serve`
- Öffnen: `http://localhost:5173`
- Auf iOS „Teilen → Zum Home-Bildschirm“ hinzufügen, dann aus dem Homescreen starten.

## Hinweise
- Einbettung per iframe erfordert, dass die Zielseite das erlaubt (keine `X-Frame-Options: DENY/SAMEORIGIN` und passende `Content-Security-Policy: frame-ancestors ...`).
- Vermeide Mixed Content: Wenn die PWA via https läuft, darf das iframe nicht http sein (oder PWA ebenfalls im Intranet via http bereitstellen).

## Deployment zu GitHub Pages
- Settings → Pages → Deploy from branch → `main` / root
- oder GitHub Actions Workflow `.github/workflows/deploy-gh-pages.yml` verwenden.
