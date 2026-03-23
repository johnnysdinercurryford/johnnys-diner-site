# Johnny's Diner Website

## About
Family-owned diner in Orlando, FL since 1995. This is the restaurant's official website.

## Tech Stack
- **Framework:** Astro 6 (static site generator)
- **Styling:** Tailwind CSS 4 (via Vite plugin)
- **Fonts:** Lobster (display/headings), Inter (body)
- **Node:** Requires 22+
- **Deployed to:** Cloudflare (static build)

## Commands
```bash
npm run dev      # Start local dev server (localhost:4321)
npm run build    # Build static site to dist/
npm run preview  # Preview production build locally
```

## Project Structure
```
src/
  pages/          # Each .astro file = one page on the site
    index.astro   # Homepage (hero, hours, highlights, location)
    menu.astro    # Full menu with category navigation
    about.astro   # Restaurant history timeline
    contact.astro # Contact form + map
    careers.astro # Job application form
  layouts/
    Layout.astro  # Master layout (nav, footer, mobile menu)
  data/
    menu.json     # All menu items, categories, and prices
  styles/
    global.css    # Tailwind config + brand colors
public/           # Static assets (favicons, images)
```

## Brand Colors
- `diner-red`: #E53935 (primary brand color)
- `diner-red-dark`: #C62828
- `diner-cream`: #FFFAF8 (light backgrounds)
- `diner-warm`: #FFF5F0
- `diner-dark`: #1A1A1A (text)
- `diner-gray`: #4A4A4A (secondary text)
- `diner-border`: #E8E0DC

Use these as Tailwind classes: `text-diner-red`, `bg-diner-cream`, etc.

## Common Tasks

### Update Menu Prices or Items
Edit `src/data/menu.json`. The menu page reads from this file automatically.
Structure: categories > subcategories > items (each with name + price).

### Update Hours
Edit the hours section in `src/pages/index.astro` (search for "Hours").

### Update Contact Info
- Phone: search for `407-868-8267` or `4078688267` across pages
- Address: search for `Curry Ford` across pages

### Add a New Page
1. Create `src/pages/your-page.astro`
2. Import Layout: `import Layout from '../layouts/Layout.astro';`
3. Wrap content in `<Layout title="Page Title">...</Layout>`
4. Add a nav link in `src/layouts/Layout.astro`

### Deployment
After making changes:
```bash
npm run build
```
Then commit and push to GitHub. Cloudflare rebuilds automatically on push.

## Git Workflow
- Always run `npm run build` before committing to catch errors
- Write clear commit messages describing what changed
- Push to `master` branch for automatic deployment

## Important Notes
- The site is static HTML — no server, no database
- Forms (contact, careers) use Formspree for submissions
- Google Maps embed is on the contact and home pages
- All content is in English
- Keep the warm, family-friendly tone in any copy changes
