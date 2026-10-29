# Fosat Global Concept: Website Project Plan

> **SOURCE OF TRUTH:** This document. Static HTML site in `/public`, Tailwind CSS + Preline UI via CDN.
> The earlier Next.js proposal is **SUPERSEDED**. Do not use Next.js or any build framework.
> If existing files conflict with this plan, report it and ask before changing anything.

---

## 1. Business Content (source: `docs/fosat company details.md`)

| Field        | Value                                                                    |
| ------------ | ------------------------------------------------------------------------ |
| Company name | Fosat global concept                                                     |
| Tagline      | Home of high quality printing                                            |
| Address      | 2, alhaja senatu road morogbo agbara lagos                               |
| Telephone    | 08068621420 (WhatsApp format: 2348068621420)                             |
| Email        | [Fosatassociate@gmail.com](mailto:Fosatassociate@gmail.com)              |
| RC (CAC)     | 3274141                                                                  |
| Established  | 2008                                                                     |
| Services     | Large format printing, Direct image printing, Branding, General printing |

All copy must come from `docs/`. Do not invent facts, prices, testimonials, or history.

### Assets in `docs/`

- Logos: `logo-new-black.jpeg` (current), `logo-old.png` (legacy)
- Videos: `machine_printing_banner.mp4`, `machine_printing_labels.mp4`, `man_hand_folding_shirt.mp4`, `man_operating_machine.mp4`, `man_operating_machine_2.mp4` (verify actual folder contents, do not trust this count)
- Photo categories: book, calendar, flyer, picture frame, plaque and awards, printer machine, rollup banner, shirts, souvenir bags, wall banner, wedding and birthday (verify real folder names; they may have been renamed or copied with hyphens)

### Known gaps (use placeholders, never invent)

No pricing, business hours, WhatsApp number, social handles, about/brand story, testimonials, FAQ, delivery info, payment methods, or order process.

---

## 2. Design Reference

Reference site: **digitalrealityprintlimited.com** (service-led layout, strong CTAs, testimonials, contact footer).
Rejected: iprints.com.ng (20+ categories, too dense) and printivo.com (pure e-commerce).

**Borrow:** sticky top CTAs, service cards (image + title + link), testimonials section, contact footer with hours/address/socials. **Do differently:** WhatsApp as the primary CTA, use Fosat's own photos, use Fosat's own tagline.

## 3. CTA Priority

1. **WhatsApp** (primary)
2. **Request a Quote** (secondary)
3. **Call** (tertiary)

---

## 4. Decisions After Approval

Fill in what you know. Anything left as "pending" stays a placeholder on the site.

- WhatsApp number: [FILL IN or "pending"]
- Business hours: [FILL IN or "pending"]
- Social handles: [FILL IN or "pending"]
- Pricing shown on site: [yes / no / "Pricing on request"]
- Accent color: [hex, or "agent to pick from logo"; plan suggests orange]
- Contact form handling: [mailto / WhatsApp link / Formspree / undecided]
- Other changes requested: [list or "none"]

## 5. Build Status

Previous agent ran out of credit mid-build.
[What you remember, e.g. "index.html mostly done, other pages not started", or "unknown, audit from files"]

---

## 6. Technical Specification

### Stack

- HTML5, static, no build step
- Tailwind CSS via CDN, with a small local CSS file for brand overrides
- Preline UI via CDN (navbar, dropdowns, modals)
- Google Fonts: Inter (body), Montserrat (headings)
- Mobile-first, responsive, fast loading (lazy-load images and videos)

### Folder structure (`/public` is the app root)

```
public/
├── index.html
├── services.html
├── portfolio.html
├── contact.html
├── css/
│   └── tailwind.css
├── js/
│   └── preline.js
├── assets/
│   ├── images/
│   │   ├── logo-new-black.jpeg
│   │   ├── logo-old.png
│   │   ├── book/
│   │   ├── calendar/
│   │   ├── flyer/
│   │   ├── picture-frame/
│   │   ├── plaque-and-awards/
│   │   ├── printer-machine/
│   │   ├── rollup-banner/
│   │   ├── shirts/
│   │   ├── souvenir-bags/
│   │   ├── wall-banner/
│   │   └── wedding-and-birthday/
│   └── videos/
└── favicon.ico
```

### Page specifications

**index.html (Home), mobile-first sections:**

1. Preline navbar: logo, mobile hamburger, service links, WhatsApp CTA button
2. Hero: tagline, short value prop, primary CTA (WhatsApp), secondary CTA (Call)
3. Services grid: 4 cards with category images
4. Trust bar: "Established since 2008", RC 3274141
5. About Fosat: company background, establishment year, registration, and location
6. Portfolio preview: 6 category thumbnails linking to Work
7. CTA banner: "Need printing for your business?"
8. Footer: contact details and links to the four core pages

**services.html:** all four service categories with images, concise descriptions, and quote links

**portfolio.html (Work):** gallery grid by category and videos

**contact.html:** address, telephone, email, WhatsApp, and quote form

### Visual direction

- Primary: charcoal/navy (from black logo)
- Accent: orange for CTA buttons and floating WhatsApp button (confirm against logo)
- Background: white / off-white
- Typography: Inter body, Montserrat headings

### Placeholder convention

Every missing item is marked exactly as `[PLACEHOLDER: description]` so it can be found with a search.

| Missing         | Marker                                                |
| --------------- | ----------------------------------------------------- |
| WhatsApp number | `[PLACEHOLDER: WhatsApp number]`                      |
| Business hours  | `[PLACEHOLDER: Opening hours]`                        |
| Social handles  | `[PLACEHOLDER: Instagram]`, `[PLACEHOLDER: Facebook]` |
| Pricing         | `[PLACEHOLDER: Pricing on request]`                   |
| Testimonials    | `[PLACEHOLDER: Customer testimonial]`                 |
| FAQ content     | `[PLACEHOLDER: FAQ content]`                          |
| Map embed       | `[PLACEHOLDER: Google Maps embed]`                    |

### Technical notes

- WhatsApp links use international format: `https://wa.me/2348068621420`
- A static site has no backend, so the contact form must use the method chosen in Section 4. Default if undecided: build the form to open a prefilled WhatsApp message.
- Tailwind is CDN-based unless Section 4 says otherwise. Do not introduce a build step without approval.
