# Local Boards

Brochure site for localboards.com.au. Perth side business selling ad spots on
shared community A-frame boards placed free in local venues.

## Stack

Static site. One `index.html` with all CSS inline in a `<style>` block, plus
`img/`. No build step, no framework, no dependencies. Keep it that way unless
there is a clear reason not to.

Deploy target: GitHub Pages (or Cloudflare Pages) on the apex domain
localboards.com.au.

## The business, in short

- A 600x900mm double-sided A-frame board is placed free in a host venue
  (cafes, salons, barbers, waiting rooms) for 12 months, renewing annually.
- The board carries 6 printed ad tiles sold to local businesses at
  AUD $600 a year per spot. The advertisers pay for the board; the venue
  pays nothing.
- Host options: a specials board with a write-on chalk panel, or a static
  printed "we are open" board plus a free ad spot on another board.
- The host approves which advertisers appear and can veto competitors.
- Secondary line: supplying plain custom single-brand A-frames.

## Board layout (proportions of the board face)

- Top 11%: printed header strip with the host venue's branding
- Next 55%: matt blackboard vinyl for liquid chalk, used by the venue
- Next 29%: 6 ad tiles in 2 rows of 3, wide rectangles
- Bottom 5%: white banner with localboards.com.au, "Get a free board, or put
  your ad here", and a QR code

## Design decisions (don't undo these by accident)

- Palette is taken from the board artwork itself: tile navy #1B4C8C,
  teal #10797A, gold #B8912A, orange #E8811F, green #5FA637, plus the dark
  red #A81C22 from the localboards wordmark. Black rules, white/near-white page.
- Type is Archivo Black for headings, Barlow for body, from Google Fonts.
- Wordmark is "local" in black and "boards" in red, matching the printed banner.
- Hard 3px black rules and flat blocks. No rounded cards, no drop shadows,
  no serif display faces. An earlier version used those and looked
  generically AI-generated.
- The "who it suits" grid deliberately echoes the six ad tiles on the board.
  Gold, orange and green tiles use black text; white on them fails contrast.
- Light only, no dark mode. The page mirrors the printed board, and the old
  dark palette made text in the ink bands and the black tile invisible.
- On mobile the hero copy comes before the photo: QR visitors are standing
  next to the board already and need the pitch, not a picture of it.

## Known placeholders, fix before real traffic

- Contact is `hello@localboards.com.au` as mailto links only. No form, no
  backend, no phone number.
- All photos are AI-generated mock-ups, not real installed boards. Venue and
  advertiser names on them are invented (Bella Via, Fade & Blade, Subiaco
  Salon, Swan River Plumbing etc). Replace with a real board as soon as one
  is installed.
- Some generated images have garbled small text. Existing images are cropped
  to hide it. Check any new image at full size before using it.
- Pricing says $600 with no GST wording. Decide and add.
- The site makes commitments that need to be real: we replace damaged boards,
  we relocate and reprint if a venue closes, one business per trade per board,
  minor ad changes at the next reprint.

## Images

- `img/hero.jpg` barber shop board, hero background
- `img/board.jpg` cafe board, "What is on it" section
- `img/chalk.jpg` hand writing on the chalk panel, Option A card
- `img/street.jpg` salon streetscape, band above the venues section. Portrait
  image shown as a wide strip; `object-position` is set so the ad tiles (garbled
  small text) stay out of frame at every width. Recheck if the image changes.

On hero, board and street, the ad tiles that matched real Perth businesses
(Swan River Plumbing, Coastal Realty, Kings Park Physio) now read "Your Business
Here". Subi Smiles Dental, Fit Hub Subiaco and Subiaco Salon are still close to
real businesses. The 0499 804 031 on every tile is the owner's own number.
Uncompressed Gemini originals live in `originals/` (gitignored).

Keep images as separate files with relative paths. Do not inline them as
base64. Compress to roughly 100-150KB each.

## Likely next jobs

- Split into separate landing pages for venues and for advertisers. The pitch
  to a cafe owner is very different to the pitch to a plumber.
- A real contact form (Formspree or a Cloudflare Worker).
- A page or section listing which venues have boards and which trades are
  still free on each.
