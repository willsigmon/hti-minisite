# Repository Guidelines

## Project Structure & Module Organization
- `index.html` is the single-page app containing markup, inline styles, and interaction snippets; group new sections with HTML comments so the sequence of hero → programs → partners stays readable.
- Store media in the repository root for now (`hti-full-logo.png`), but prefer creating `assets/` when adding multiple images or scripts to keep the top level tidy.
- `vercel.json` forces every request to resolve to `index.html`, so any new routes must be implemented as in-page sections with anchor links instead of separate files.

## Build, Test, and Development Commands
- `python3 -m http.server 5500` — quick local preview at http://localhost:5500; mirrors production headers closely enough for layout checks.
- `npx serve .` — alternative static server that respects clean URLs when testing anchor-based navigation.
- `vercel dev` — run if you need to validate the rewrite rules or share a preview link; requires the Vercel CLI and an authenticated session.

## Coding Style & Naming Conventions
- Use 4-space indentation in HTML/CSS blocks; align closing tags with their opener.
- Stick to lowercase, dash-separated class names (`kiwanis-popover-overlay`) and camelCase only when working with inline JavaScript.
- Keep inline CSS organized by section with the existing comment markers; add utility classes sparingly and document any global resets you introduce.

## Testing Guidelines
- Manually verify responsive breakpoints at 360px, 768px, and 1280px using browser dev tools; the layout is mobile-first and relies on fluid typography.
- Re-run the page through Lighthouse or Chrome’s “View Page Source → Open in Browser” to confirm Core Web Vitals stay in the green after heavy visual changes.
- Check all anchor jumps and CTA targets after edits, since the Vercel rewrite masks missing hash IDs.

## Commit & Pull Request Guidelines
- Follow the repository’s energetic, present-tense commit style (`Mobile-first pizzazz: centered copy…`); lead with the headline result, then clarify scope after a colon.
- Include before/after screenshots or screen recordings in PRs, especially for hero or testimonial tweaks; attach the local server URL or Vercel preview link if available.
- List manual QA steps you performed (devices, browsers, accessibility scans) and reference any related issues so reviewers know the change footprint.

## Deployment & Configuration Tips
- Keep `vercel.json` updates minimal; any change affects routing for the entire site.
- When adding third-party embeds or fonts, prefer `<link>` or `<script>` tags hosted via HTTPS CDNs to avoid breaking static hosting on Vercel.
- Double-check cache headers on large assets by requesting them through `curl -I <url>` after deployment to confirm Vercel’s CDN is serving compressed responses.
