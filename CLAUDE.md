# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A browser-based habit tracker implemented as a single self-contained HTML file (`index.html`). No build tools, dependencies, or server required — just open in a browser. Design inspired by the Yetch Studio Every Day Goal Calendar — dark minimal aesthetic with amber/gold lit indicators.

## Architecture

Everything lives in `index.html`: markup, styles (`<style>`), and logic (`<script>`). Uses Google Fonts (Inter) for typography.

Three fixed habits are tracked: **Coding**, **Reading**, **Exercise**. Each has 10 days arranged as a grid — 3 habit columns with 10 day rows. Clicking a circle toggles it lit (amber/gold glow) or unlit.

Data is persisted to `localStorage` under the key `habit-tracker-data` as a JSON object mapping habit names to arrays of completed day numbers:

```
{ "Coding": [1, 3, 5], "Reading": [2], "Exercise": [] }
```

Key functions: `loadData()`/`saveData()` for persistence, `render()` rebuilds the full grid and footer stats on every state change, `toggle()` toggles a day and triggers ignite/extinguish animations, `clearAll()` resets all progress with confirmation.

## Development

Open `index.html` directly in a browser. No build step. To test changes, refresh the page. Use the Reset button or clear localStorage to reset all data.
