# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

This repo contains standalone, single-file HTML games. There is no build step, package manager, or test suite — each `.html` file is fully self-contained (inline `<style>` and `<script>`, no external dependencies) and runs by opening it directly in a browser.

- `tictactoe.html` — the game.

## Architecture (tictactoe.html)

Vanilla JS in a single IIFE, no framework:

- The 3x3 grid of `.cell` buttons is built dynamically in JS (not present in the static HTML) and cached in a `buttons[]` array for lookup by index.
- Game state lives in three plain variables: `cells[]` (9-slot board, null/'X'/'O'), `turn`, and `over`, plus a `scores` tally that persists across rounds until page reload.
- `winner()` checks the 9-cell array against the 8 fixed `LINES` (rows/cols/diagonals).
- `play(i)` is the single entry point for a move: mutates `cells`, updates the DOM for that cell, checks `winner()`/draw, and either ends the round or flips `turn`.
- `newBoard()` resets board state but not `scores`.
- Theming is CSS custom properties on `:root` with a `prefers-color-scheme: dark` override block — no JS-driven theme switching.

## Working in this repo

- Keep files self-contained: don't introduce a bundler, package.json, or external script/CDN dependencies unless asked.
- To verify a change, open the file directly in a browser; there is no automated test runner.
- Commit and push to GitHub regularly as you work — after each logical change, not just at the end of a session — with clean, descriptive commit messages, so work is never lost.
