# Selected Works — Project Archive Grid

An archival-style project index page presenting a responsive grid of project cards, each with an image, title, ID tag, description, and hashtags — capped with an "archive end" footer strip and a "load next entries" pagination control.

## Preview

The layout includes:
- **Header** — "Student portfolio_v1" logo and a right-aligned nav (Home, Projects, Contact, CV_download button)
- **Section heading** — "SELECTED_WORKS" title with a left accent bar and supporting description
- **Project grid** — six identical-structure cards (responsive 1/2/3-column grid), each showing an image, project title, ID badge, description, and hashtags, with a hover highlight
- **Pagination strip** — "Archive section end / Viewing page 01 of 04" on the left, "Load next entries" link on the right
- **Footer** — copyright notice and social links (Insta, LinkedIn, GitHub)

## Tech Stack

- **HTML5**
- **Tailwind CSS** — loaded two ways simultaneously:
  - via CDN (`@tailwindcss/browser@4`)
  - via a compiled `output.css` stylesheet
- **Font Awesome** (via Kit CDN) — script is loaded but no icons are currently used in the markup

## File Structure

```
.
├── index.html          # Page markup
├── output.css            # Compiled Tailwind stylesheet
└── Emblem.png              # Project card image (reused across all cards)
```

## Getting Started

No build step required if relying on the CDN script alone. If you intend to use `output.css` as your actual styling source (recommended for production), you'll need a Tailwind build process:

1. Clone the repository:
   ```bash
   git clone <repo-url>
   cd <repo-folder>
   ```
2. Install Tailwind and generate `output.css`:
   ```bash
   npm install tailwindcss @tailwindcss/cli
   npx @tailwindcss/cli -i ./input.css -o ./output.css --watch
   ```
3. Open `index.html` directly in a browser, or serve it locally:
   ```bash
   npx serve .
   ```

## Responsive Behavior

- **Below `md` (768px)** — 1 column grid
- **`md` and above** — 2 column grid
- **`lg` (1024px) and above** — 3 column grid
- Grid uses `divide-x`/`divide-y` so internal borders automatically adapt as the column count changes at each breakpoint

## Notes / TODO

- All six project cards currently use identical placeholder content (same image, "Projext title", same description/hashtags) — replace each with real project data
- Repeated typos in the placeholder copy: "Projext" → "Project", "paterns" → "patterns", "arythmetic" → "arithmetic", "ballance" → "balance", "typogrtaphy" → "typography"
- The `CV_download` `<button>` has an `href="#"` attribute — buttons don't support `href` (only `<a>` does); this attribute currently has no effect and can be removed, or the button converted to a styled `<a>` if it should behave as a link/download
- Both the Tailwind CDN script and a linked `output.css` are present at the same time — if `output.css` is a real compiled build, the CDN script is redundant and can be removed to avoid duplicate/conflicting style generation
- "Load next entries" link (`#`) isn't wired to any pagination logic yet — connect to real page-2 data/routing when available

## License

This project is provided as-is for personal portfolio or educational use. Add a license of your choice (MIT, etc.) if distributing publicly.
