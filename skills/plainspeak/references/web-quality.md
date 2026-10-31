# Web quality checklist

Use this when building or reviewing a site, landing page, or UI.

## Content and UX
- No placeholder text. No generic AI copy. Write specific copy about the product.
- No walls of text unless the user asked for long-form.
- No stock images or AI-generated filler images. Use real product images or none.
- Gradients should be subtle. Avoid harsh or heavy gradients.
- No unnecessary popups, cookie banners beyond what the law requires, or video backgrounds.
- One primary call to action per section. Do not stack competing CTAs.
- Show pricing when it is public. Do not hide it behind a form.
- Show real reviews only. No fabricated testimonials or logos.
- Every page has one clear purpose.
- Include a useful 404 page and useful error and success messages.
- Forms only where needed. Every control has a label.
- No empty buttons or links. No broken links.

## Responsive and accessible
- Design mobile first. Test the layout at phone width.
- Use semantic HTML: landmarks, one h1, ordered headings.
- Give every image accurate alt text. Decorative images get empty alt.
- Keep color contrast readable. Make all controls work by keyboard with visible focus.
- Use descriptive link text. Avoid "click here."
- Respect `prefers-reduced-motion`.

## SEO and metadata
- Unique title and meta description on each page.
- Canonical tag, favicon, Open Graph and social share tags.
- `sitemap.xml` and `robots.txt`.
- Structured data only when it matches the page content.
- `llms.txt` only when it helps.
- Internal links where they help the reader.
- Correct HTTP status codes. Keep redirect chains short.
- No console errors.

## Performance
- Lazy-load images below the fold. Compress images.
- Keep JavaScript bundles small. Avoid unneeded dependencies.
- Load non-critical scripts without blocking rendering.
- Compress responses where the host supports it.

## Visual design
- Avoid generic template defaults. Pick a deliberate typeface pair and palette.
- Spacing and alignment should follow a consistent scale.
- Use the frontend-design skill for aesthetic direction when it is available.
