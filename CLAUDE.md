# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

This repo contains standalone, single-file HTML games. There is no build step, package manager, or test suite — each `.html` file is fully self-contained (inline `<style>` and `<script>`, no external dependencies) and runs by opening it directly in a browser.

- `tictactoe.html` — the game, uncommented.
- `tictactoe-commented.html` — identical game logic with explanatory comments added.

## Working in this repo

- Keep files self-contained: don't introduce a bundler, package.json, or external script/CDN dependencies unless asked.
- When editing `tictactoe.html`, mirror any logic changes into `tictactoe-commented.html` (and vice versa) to keep them in sync — they are meant to stay identical apart from comments.
- To verify a change, open the file in a browser; there is no automated test runner.
