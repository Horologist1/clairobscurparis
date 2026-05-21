# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this project is

A static HTML website for a tabletop RPG / collaborative-fiction project titled **"Clair Obscur: Belle Époque"**, set in Paris, 1905. The site is the in-fiction artefact set: a multi-edition newspaper (*Paris Nouveau*), character sheets, a noble dossier, and supporting prose/lore in `.md`, `.txt`, and `.docx` files. There is no build system, no package.json, no tests — open `index.html` (or any other `.html`) directly in a browser to view.

Working language of the prose is Spanish; the rendered newspaper UI is **bilingual French/Spanish** toggled at runtime (see *Bilingual content* below).

## Repository layout

- `index.html` — landing/cover page with a sidebar nav.
- `noticias.html`, `noticias1.html` … `noticias25.html` — individual newspaper editions (one HTML file per in-fiction date). Numbering is **chronological by file index**, not by filename order in the directory; `noticias.html` is the *earliest* edition (18 Mars 1905), `noticias25.html` is the latest (2 Novembre 1905). Note that some numbers are skipped (no `noticias23.html`/`noticias24.html`).
- `ficha.html` — character sheet template. Uses CDN `html2canvas` + `jspdf` to export the rendered sheet to PDF.
- `nobles_florista.html` — separate dossier page for European nobility.
- `news/` — newspaper article images. `news/Other/` is a working pool of unattached images (Mucha plates, period photos) used as raw material for new editions.
- `personajes_imagenes/` — character portraits referenced by `ficha.html` and the newspapers.
- `*.md`, `*.txt`, `*.docx` — design/lore documents. The `.docx` files (`Dossier de personajes*.docx`, `Sistema_de_Maestría_y_Poderes_Artísticos.docx`, `Anaïs Vernier - Nuria.docx`) are the canonical character/system references. Markdown files like `esquema_partida_opera.md`, `introduccion_partida.md`, `breves_pool.md`, `periodistas_pool.md`, `ideas_primera_plana_1_abril_1905.md` are session prep, pools of short items ("brèves"), and journalist by-line lists meant to be drawn from when authoring new editions.

## Bilingual content pattern

Every edition uses parallel `<span class="lang-fr">…</span>` and `<span class="lang-es">…</span>` (or `<div>`/`<h2>`/`<p>`) blocks for the same text. CSS hides one set; clicking the 🔍 button calls `toggleLanguage()`, which toggles `body.spanish` and persists the choice in `localStorage` under the key `newspaperLanguage`. **When adding new newspaper content, always author both `.lang-fr` and `.lang-es` versions** — a missing language pair renders as a blank section in that mode.

## Shared cross-edition navigation

The left-rail `.date-navigation` block in `noticias*.html` lists every edition and is **hand-duplicated** in each file. When you add a new edition:

1. Create the new `noticiasN.html` (copy an existing edition as scaffolding).
2. Add a new `<li class="date-item">` linking to it in `noticias.html` **and** in every other `noticias*.html` file, keeping the list in reverse-chronological order with the current page's `<a>` carrying the `active` class.

There is no template engine — propagating nav changes is a manual find/replace across all editions.

## Asset references

Image `src` paths are relative and case-sensitive on case-sensitive filesystems. Newspaper images live under `news/…`; character art under `personajes_imagenes/…`. Some images in `news/` have `~` backup variants (e.g. `madeleine.jpg~`) — these are editor backup files, not used by the HTML.

## Content tone

The setting blends real Belle Époque historical figures (Sarah Bernhardt, Matisse, Proust, Méliès, Guimard, Mucha…) with a fictional magic system where artists ("Maestros del Arte") wield reality-bending powers through their craft. Newspaper articles are written in period-appropriate journalese with a thin veneer over the supernatural events driving the campaign. When authoring or editing prose, match this register — formal, slightly florid, in-world — and keep the supernatural implications oblique rather than explicit.
