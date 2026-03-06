# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Single-file web app (`raffle.html`) — a raffle draw tool for The Beacon of Lansdown Project. No build system, no dependencies, no package manager. Open the file directly in a browser to run it.

## Workflow

- **Auto-commit and push** after every change, without asking for confirmation.
- Remote: `https://github.com/softabacus/raffle-draw` (branch: `main`)

## Architecture

Everything lives in `raffle.html` as a self-contained file with inline `<style>` and `<script>`.

Key JS globals:
- `pool` — array of remaining undrawn numbers
- `history` — array of drawn numbers (newest first)
- `secureRandInt(n)` — crypto-safe RNG using `crypto.getRandomValues()` with rejection sampling to avoid modulo bias
- `initPool()` — builds the pool from the min/max inputs and resets state
- `draw()` — picks a winner, runs the spin animation, updates UI
