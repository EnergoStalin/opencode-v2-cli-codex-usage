# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.1] - 2026-09-28

### Fixed
- **Header Spacing**: Removed extra column gap from the header row container to match other sidebar plugins (`Token Usage`, `Gemini Usage`), ensuring a single consistent space between the title and collapsed summary.
- **Percentage Formatting**: Formatted whole percentage values cleanly as integers (e.g. `95%` instead of `95.0%`).
- **Standalone Packaging**: Added root entrypoint shims (`index.js`, `tui.js`, `core.js`) and inlined the server plugin definition so the package loads standalone without requiring `@opencode/plugin` in `node_modules`.

### Documentation
- Cleaned up installation instructions in `README.md` to focus on standard global CLI settings (`cli.json`) and project configuration (`opencode.jsonc`).

---

## [1.0.0] - 2026-09-25

### Added
- **Initial Release**: OpenCode V2 CLI plugin that displays remaining OpenAI Codex usage limits, countdowns, credits, and banked reset credits in the terminal sidebar.
- **Zero-Setup Authentication**: Reads active OpenAI OAuth credentials directly from OpenCode's SQLite database (`~/.local/share/opencode/opencode.db`)—no separate Codex CLI installation or login required.
- **Fallback Authentication**: Added backward-compatible fallback for `~/.codex/auth.json` with security checks.
- **OpenCode V2 Architecture**: Built with `@opencode/plugin/tui` targeting the `sidebar.content` slot using Solid.js universal components.
- **Persistent State**: Integrated with OpenCode's durable storage (`context.storage.store`) to persist collapse/expanded state across restarts and hot reloads.
- **Live Timers**: Real-time 1-second countdown ticker for window reset times, alongside 60-second background polling.
- **Full Quota Metrics**: Supports primary window (5h), secondary window (Weekly), additional feature limits, plan type, credits balance, and available reset credits.
- **Theming**: Native integration with OpenCode semantic theme tokens (`context.theme.text.*`).
