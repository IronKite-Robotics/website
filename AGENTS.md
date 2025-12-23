# Repository Guidelines

## Project Structure & Module Organization
- Root-level static site served via GitHub Pages; `index.html` holds all markup and inline styles.
- `CNAME` binds the deployed site to the configured custom domain; update it if the domain changes.
- `README.md` is intentionally minimal; add high-level context there when features expand.
- If you add assets, keep them in a new `assets/` folder and reference with relative paths to preserve GitHub Pages compatibility.

## Build, Test, and Development Commands
- No build step required; the site is a static HTML page.
- Local preview: `python3 -m http.server 4000` (from repo root) then visit `http://localhost:4000`.
- Optional: use any static server (e.g., `npx serve`) if you already have it installed; avoid introducing dependencies unless necessary.

## Coding Style & Naming Conventions
- Aesthetic: Maintain a pure typographic Swiss minimalist style (bold Helvetica Neue, tighter letter-spacing, generous white space, 4px graphic lines).
- HTML/CSS only; follow semantic HTML and keep accessibility basics (proper headings, alt text).
- Indentation: 4-space indent in HTML/CSS blocks to match existing file.
- Keep file names lowercase with hyphens if new pages are added.
- Inline CSS is acceptable for this single-page layout; if styles grow, extract to `assets/styles.css` and minify if sizable.

## Agent Behavior
- Proactiveness: Thoroughly fulfill requests, including implied follow-ups.
- Security: Never expose or commit secrets/API keys.
- Interaction: Professional, concise, and direct tone; no conversational filler.
- Verification: Always verify changes using Playwright and standard preview tools before finishing.

## Testing Guidelines
- **ALWAYS check changes against common desktop and mobile resolutions using Playwright tools:**
  - Desktop: 1920×1080, 1366×768, 1024×768
  - Mobile: 375×667 (iPhone SE), 393×873 (Android standard), 812×1024 (iPad)
  - Use `playwright_browser_resize` to test viewport dimensions and `playwright_browser_take_screenshot` to verify visual appearance.

## Commit & Pull Request Guidelines
- Commit messages: short, present-tense summaries (e.g., `Add hero copy`, `Update CNAME for new domain`); include scope when relevant.
- Keep commits small and focused on one change set (content, styling, or infra).
- Pull requests: include a short summary of changes, before/after screenshots for visual updates, and note any new manual steps (e.g., DNS changes).
- Link related issues when available and confirm local preview before requesting review.

## Deployment Notes
- Deployment is automatic on push to default branch through GitHub Pages; verify the custom domain resolves after DNS updates.
- When adding assets, ensure paths remain relative so the pages render correctly in the Pages environment.
