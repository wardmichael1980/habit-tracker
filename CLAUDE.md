# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A browser-based habit tracker implemented as a single self-contained HTML file (`index.html`). No build tools, dependencies, or server required — just open in a browser.

## Architecture

Everything lives in `index.html`: markup, styles (`<style>`), and logic (`<script>`). Data is persisted to `localStorage` under the key `habit-tracker-data` as a JSON array of habit objects:

```
[{ "name": "Exercise", "completed": ["2026-03-17", "2026-03-18"] }]
```

Key functions: `loadData()`/`saveData()` for persistence, `getStreak()` for consecutive-day calculation, `render()` rebuilds the full habit list on every state change, `toggle()`/`remove()` mutate data and re-render.

## Development

Open `index.html` directly in a browser. No build step. To test changes, refresh the page. Clear localStorage to reset all data.
