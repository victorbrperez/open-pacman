# AGENTS.md

Pac-Man in vanilla JS/HTML/CSS. No build, package manager, tests or linter. Open `src/index.html` in a browser (or serve `src/`).

## Architecture
- No modules: `src/index.html` loads scripts in order `maze.js` → `game.js` → `render.js` → `main.js`. Everything is a global; keep that order when adding files.
- `maze.js`: maze data; `game.js`: state/update logic (`createGame`, `update`); `render.js`: canvas drawing (`draw`); `main.js`: loop, keyboard, overlay screens.
- Overlay markup is rebuilt via `innerHTML` in `main.js` (`showOverlay`), so the button must be re-bound after each rebuild.

## Workflow
- Spec Driven Development (learning project). Skills in `.agents/skills/` (`spec`, `spec-impl`): specs live in `specs/NN-slug.md`; `spec-impl` only proceeds if the spec status is "Approved", and creates a git branch named after the spec.
- Code in English, comments in Spanish. Code style: spaces inside parentheses (`foo( x )`).
