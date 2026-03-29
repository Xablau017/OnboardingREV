# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static single-page onboarding guide for Grupo Boticário resellers. There is no build system — the entire application is a single `index.html` file with embedded CSS and JavaScript.

## Running the App

Open `index.html` directly in a browser. No server, build step, or dependencies required.

## Architecture

All code lives in `index.html`:

- **CSS** (`<style>` block): Custom properties define the theme (`--verde`, `--ouro`, `--creme`, `--bege`). Layout uses flexbox/grid; animations use `@keyframes` and class toggling.
- **HTML**: Eight `<section>` elements (hero, marcas, lucros, ferramentas, primeiros-passos, dicas, organizacao, apoio) linked from fixed sidebar nav dots (`.nav-dots`).
- **JavaScript** (`<script>` block, ~36 lines): Two `IntersectionObserver` instances — one updates the active nav dot (scroll spy), one triggers `.revealed` class for fade-in animations on scroll.

## Key Patterns

- Smooth scroll navigation via `<a href="#section-id">` anchor links.
- Reveal animations: elements start with opacity/transform; the observer adds `.revealed` to trigger transition.
- Responsive breakpoints are handled entirely in the embedded CSS with media queries.
