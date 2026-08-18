# Young Boys Barbershop — marketing site

Static site for Young Boys Barbershop (Ithaca, NY). No build step, no
dependencies — one `index.html` plus images, deployed on Vercel.

- **Live:** https://youngboys-barbershop.vercel.app
- **Booking app (separate repo):** https://github.com/brevitysolutions/youngboys-platform
- **Built by** [Brevity Solutions](https://brevity.solutions)

## The go-live switch

Near the top of `index.html`:

    const BOOKING_URL = null;   // null = Square Appointments; set to the app URL to cut over

All four "Book" CTAs carry a `data-book` attribute and read this one constant.
While it is `null` they point at the shop's existing Square Appointments page.
Setting it to the booking app's URL switches all four at once.

**The Square links are deliberate until the app goes live — do not "fix" them.**

## What is dynamic

The services menu renders from the booking app's `/api/services`, so prices,
descriptions and photos Kevin edits in the admin dashboard appear here too
without a deploy. A hardcoded copy paints first, so the page is never empty.

Shop hours appear in two places and both must stay in step: the visible hours
block, and the hardcoded JSON-LD `openingHoursSpecification` — the latter is what
Google actually reads.

## Deploying

Push to `main`; Vercel deploys. No build step. Commits must be authored with a
GitHub-mapped email or Vercel blocks the deploy.

## Client

**Young Boys Barbershop** — 111 Dryden Rd, Suite D · Ithaca, NY 14850
Instagram: [@youngboys_barbershop_1](https://www.instagram.com/youngboys_barbershop_1/)
