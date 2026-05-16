# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Two independent HTML files for the **Tubus Servicios** brand — an authorized Yutong bus dealer and service center in Valencia, Carabobo, Venezuela. There is no build system; both files are opened directly in a browser.

## Files

### `index.html` — Static Landing Page

A fully self-contained single-file website. No build step. All CSS lives in a `<style>` block; all JS is inline at the bottom of `<body>`. Open directly in a browser to preview.

**Theming:** Supports dark (default) and light modes. Theme is persisted in `localStorage` under the key `tubus_theme`. An inline `<script>` in `<head>` reads it before paint to avoid flash. CSS tokens live on `:root` (dark) and `[data-theme="light"]`.

**Design tokens (dark defaults):**
- Background: `--bg` `#07080d`, `--bg-2`, `--bg-3`
- Primary blue: `--primary` `#003e99`, `--primary-2` `#002d70`, `--primary-light` `#4d8fef`
- WhatsApp green: `--wa` `#25d366`
- Container max-width: `--container` `1200px`

**Page sections (by anchor):** `#servicios`, `#nosotros`, `#contacto`, `#galeria`

**Image carousel (`#galeria`):** Slides are stored as JSON in `localStorage` under the key `tubus_banner_slides`. An admin panel (hidden by default) is shown when `?admin` is present in the URL, allowing slides to be added, reordered, and saved without a server.

**Placeholder data that needs real values:**
- Phone: `0412 · 000 00 00` — in `tel:+584120000000` href and display text
- Email: `contacto@tubusservicios.com`
- WhatsApp: `https://wa.me/584120000000`
- Address: generic "Valencia, Estado Carabobo, Venezuela"

### `TuBus Express.html` — Angular App Shell

Compiled `index.html` output of an Angular application. The referenced JS/CSS assets (`chunk-*.js`, `styles-VG3QSET3.css`, `polyfills-*.js`, `main-*.js`) are **not present** in this directory — this shell is non-functional without the full Angular `dist/` folder alongside it.

**Tech stack:** Angular, Tailwind CSS, Inter + Poppins fonts.

**CSS color system (light theme only):**
- `--tubus-primary`: `rgb(0, 29, 86)` (dark navy)
- `--bg-primary` / `--bg-secondary` / `--bg-tertiary`: white → light gray scale
- `--text-primary` through `--text-tertiary`: near-black → mid-gray
- `--transition-fast/normal/slow`: `.15s`, `.3s`, `.5s` `ease-in-out`

## Assets

- `Tubus Servicios.svg` — full wordmark logo
- `Icono autobus.svg` / `Icono autobus azul.svg` — bus icon (default / blue variant)
- `Icono B con recuadro.svg` / `Icono B con recuadro (1).svg` — "B" icon variants
- `Colores.png` — brand color reference
