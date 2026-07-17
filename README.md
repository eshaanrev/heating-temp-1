# Heating &amp; Bathrooms Website Template

A fast, responsive, single-page marketing site template for combined heating and
bathroom businesses — boilers, central heating, and full bathroom design &amp;
installation. No build step, no dependencies, no framework.

## Structure

```
heating-bath-template/
├── index.html    markup + copy + SEO metadata + JSON-LD
├── styles.css    design tokens, layout, components, animations
├── script.js     scroll reveal, mobile nav, sticky header, parallax, form
└── README.md
```

## Sections

Breakdown bar (24/7) · Nav · Hero · Trust bar · Services grid (6: heating + bathrooms) ·
Breakdown CTA · Free design consultation + finance · Service area · Testimonials (3) ·
Contact + form · Footer

## Customizing for a client

Every client-specific string is a bracketed placeholder. Find and replace across
`index.html`:

| Placeholder | Replace with |
| --- | --- |
| `[Business Name]` | The client's business name |
| `(555) 123-4567` | Their phone number (also in every `tel:+15551234567` link) |
| `hello@yourbusiness.com` | Their email (also in the `mailto:` links) |
| `[Street Address]`, `[City]`, `[ST]`, `[ZIP]` | Their showroom / address |
| `[Service Area]` | The region they cover |
| `[Town One]` … `[Town Eight]` | The towns in the service-area chips |
| `[Year]` | Year founded |
| `[##]`, `[###]`, `[#.#]` | Trust-bar stats and boiler guarantee years |
| `[#.##]% APR`, `[##] months` | Real finance terms |
| `[License Number]` | License / registration number (footer) |
| `[Customer Name]` | Real testimonial attribution |
| `https://www.example.com/` | The live domain (canonical + Open Graph + JSON-LD) |

Also update: the `<title>`, `<meta name="description">`, the Open Graph block, the
JSON-LD schema, the favicon emoji, and the footer social links (Houzz by default).

> **Finance disclosure:** the `.finance-fine` paragraph is a placeholder. Replace it with
> whatever disclosure your lender requires — the example APR and term are not real offers
> and must not ship as-is.

### Images

Image placeholders are `<div class="media" data-label="…">` elements. Each has a fixed
`aspect-ratio`, so swapping in a real photo causes **no layout shift**:

```html
<img src="images/bathroom.jpg" alt="Finished walk-in shower and vanity"
     width="1200" height="1500" loading="lazy" />
```

Keep the `width`/`height` attributes and give every image a descriptive `alt`. Bathroom
photography carries this template — real finished-project photos are worth commissioning.

### Colors & type

All theming lives in the `:root` block at the top of `styles.css`. The palette pairs a
warm graphite primary with a brass accent and a spa-teal secondary on warm stone
neutrals — a premium, showroom feel that suits both heating and bathroom work. Change
`--color-primary`, `--color-accent`, and `--color-cool` to re-skin. Fonts are two
families (Sora for display, Inter for body).

### The contact form

`script.js` validates and shows a success message, but does **not** send anything.
Wire it to Formspree, Netlify Forms, or your own endpoint before going live.

## Local preview

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## Notes

- Respects `prefers-reduced-motion` — all animation, including the pulsing breakdown dot,
  is disabled for users who ask for it.
- Keyboard accessible: skip link, focus rings, Escape closes the mobile nav.
- No external JS/CSS dependencies; the only network request is Google Fonts.
