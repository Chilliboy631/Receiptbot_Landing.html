# SlipStack /blog — drop-in package

Static, no build step. Matches your Vercel "static multi-page HTML" setup.

## Files
- `index.html` — the blog landing page (list of posts)
- `whatsapp-receipt-automation-south-africa.html` — post #1
- `feed.xml` — RSS feed
- `sitemap.xml` — blog sitemap

## Install (once)
1. Copy this whole `blog/` folder into your `website/` folder, so you get:
   `website/blog/index.html`, `website/blog/whatsapp-receipt-automation-south-africa.html`, etc.
2. Add a **Blog** link to your main site header/footer nav → `/blog/`.
3. Deploy as usual: `cd website && vercel deploy --prod`.
4. Tell Google it exists: submit `https://www.slipstack.co.za/blog/sitemap.xml` in
   Google Search Console (or add its URLs to your existing root sitemap).

## Adding a new post (repeat weekly)
1. Copy the post HTML file, rename to the new slug (use hyphens, keywords in the slug).
2. Update: `<title>`, `<meta name="description">`, `<link rel="canonical">`, the OG tags,
   the `<h1>`, the byline date, the JSON-LD (`headline`, dates, FAQ Q&As), and the body.
3. Add a `.post` card to `index.html` (newest first).
4. Add an `<item>` to `feed.xml` (newest first) and bump `<lastBuildDate>`.
5. Add a `<url>` to `sitemap.xml`.
6. Deploy.

## Notes
- Styling is inlined in each file so they're fully self-contained. If you'd rather
  share one `blog.css`, lift the `<style>` block into `blog/blog.css` and link it.
- The header/footer here approximate your brand chrome. Share one live page
  (e.g. `contact.html`) and the exact nav/footer can be mirrored.
- `og:image`, `/logo.png`, `/privacy.html` are referenced — point them at real assets
  (or create the privacy page — happy to draft a POPIA-compliant one).
