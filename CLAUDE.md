# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

For contributor workflow details, start with `AGENTS.md` (`Repository Guidelines`) and then return here for Claude-specific notes.

## Project Overview

This is a single-page HTML promotional website for the HUBZone Technology Initiative (HTI), a 501(c)(3) organization focused on closing North Carolina's digital divide by providing refurbished Chromebooks to families in need.

## Architecture

**Single-File Structure**: This is a self-contained HTML file (`hti-mobile-mini-site.html`) with no build system, dependencies, or external tooling.

**Key Components**:
- Inline CSS styling (lines 7-482)
- Semantic HTML sections (lines 484-703)
- Vanilla JavaScript for scroll interactions (lines 705-841)

## Design System

**Color Palette**:
- Primary Navy: `#1e3a5f`
- Accent Teal: `#4a9b9f` / `#6db3b7`
- Alert/Youth Programs: `#ff6b6b`
- Kiwanis Yellow: `#fff9c4` / `#ffeb3b`

**Layout**: Mobile-first design with:
- Fixed container: 430px max width
- Full-height sections with scroll snap
- Touch-optimized interactions

## Section Structure

The page contains 8 main sections (all with class `.section`):
1. Hero (`.hero`) - Organization branding and mission statement
2. Mission (`.mission`) - Three core mission cards
3. Process (`.process`) - 4-step transformation workflow
4. Youth Programs (`.youth-programs`) - Program highlights with Kiwanis alignment
5. Impact (`.impact`) - Statistics grid and outcomes
6. Success Stories (`.stories`) - Testimonial cards
7. CTA (`.cta`) - Call-to-action with donation links
8. Footer (`.footer`) - Contact information and social links

## JavaScript Behavior

**Touch Interactions** (lines 712-743):
- Swipe detection with 50px threshold
- Section-to-section navigation
- Scroll lock during transitions (800ms)

**Visual Effects**:
- Intersection Observer for section tracking (lines 760-773)
- Counter animation for statistics (lines 804-840)
- Fade-in animations for cards (lines 786-801)

## Development Notes

**No Build Process**: Open the HTML file directly in a browser. No compilation, transpilation, or bundling required.

**Testing**: Manual testing only. Check on:
- Mobile viewports (primary target)
- Touch gesture handling
- Animation performance
- Scroll snap behavior

**Key Contact Information** (update these when needed):
- Organization: HUBZone Technology Initiative
- Location: 501 S. Chestnut Street, Henderson, NC 27536
- Email: info@hubzonetech.org
- Website: www.hubzonetech.org
- Social: Facebook (/HTIHUBZone), LinkedIn (/company/htihubzone), Instagram (@hubzonetech)
- Tax ID: EIN 83-3153294

## Modification Guidelines

When editing this file:

1. **Preserve inline structure** - All CSS/JS must remain embedded
2. **Maintain mobile-first approach** - Primary viewport is 430px max width
3. **Test scroll interactions** - Swipe gestures and section navigation are critical UX
4. **Keep accessibility** - Semantic HTML and readable color contrasts
5. **Update stats carefully** - Counter animation logic expects numeric values (lines 804-818)

## Critical Files

- `hti-mobile-mini-site.html` - The entire application (single file)

That's it. This is an intentionally simple, zero-dependency promotional microsite.
