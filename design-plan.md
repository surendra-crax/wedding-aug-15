# Wedding Invitation Website — Design Plan
*Reference study: 9 invitationmedia.in sites · Prepared for new client page*

---

## 1. What the 9 reference sites taught us

| Site | Standout idea worth borrowing |
|---|---|
| Rushikesh & Prajakta | Sage-green envelope + wax seal opening, falling petals, scratch-to-reveal card, photo-backed event cards |
| Deeksha & Chetan | **Full Warli-art theme** (terracotta + cream), custom couple logo (moon + sun), Devanagari hashtag, "Story Behind Our Logo" section — strongest branding of all 9 |
| Ananya & Vartika | Blush → deep maroon contrast, Mughal-garden illustrated hero, dark events section for drama |
| Harshjot & Karanpreet | Faith-specific theming (Khanda seal, Gurdwara illustration, Jaggo/Baraat cards), Google Maps embed + Get Directions |
| Jinal & Hitarth | Red velvet Radha-Krishna envelope, Sanskrit shloka, handmade-paper card texture, hashtag shown before envelope even opens |
| Swapnil & Ritu | **Best event cards**: each ceremony gets its own themed watercolor world (marigold Haldi, starlit navy Sangeet) + per-event hashtags + frosted-glass text panels; hanging temple bells; shloka with transliteration |
| Roopa & Anoop | Cinematic light-burst envelope opening, embossed ivory paper, pearl-embroidery seal, elegant fade-in storytelling |
| Bhushan & Pragyansa | **Personality**: "Meet the Couple" avatar cards with favourites chips, "Our First Photo" polaroid — guests love this |
| Saiyam & Jenny | Photoreal textured envelope with ribbon, full-bleed cinematic garden scene, editorial minimalism |

**Common skeleton all sites share:** sealed envelope → tap to open → invocation (Ganesha/shloka) → couple names + parents → scratch-to-reveal surprise → events schedule → family section → venue/map → footer with music toggle.

**Gaps we can exploit (nobody did these):** countdown timer, RSVP/blessing wall, photo gallery timeline of the couple's story, day-wise itinerary navigation, dress-code palette, save-to-calendar buttons.

---

## 2. Design concept: "The Royal Pothi" — a heritage keepsake that comes alive

One-line pitch to client: *"Not a webpage — a digital heirloom. It opens like a sealed royal invitation, reads like a miniature-painting storybook, and ends with the guest's own blessing on the wall."*

### Visual language
- **Palette:** Deep maroon `#5C1A1B` + ivory handmade paper `#F6EFE3` + antique gold `#C9A24B`, with one fresh accent (sage or peacock teal) for balance. Rich but airy — dark sections alternate with light so it never feels heavy.
- **Typography:** Great Vibes / Tangerine-style script for names, Cormorant Garamond small-caps for labels (DATE / TIME / VENUE), a Devanagari display face for shlokas and hashtag.
- **Texture:** handmade-paper grain everywhere, gold-foil edges, embossed motifs (borrow from Jinal-Hitarth + Roopa-Anoop).
- **Traditional motifs:** Pichwai/miniature-painting borders, marigold garlands, hanging temple bells, peacocks, banana-leaf toran, kalash — chosen to match the client's culture/region once details arrive (theme is swappable: Warli / Pichwai / Phulkari / Kanjeevaram-checks).

### Page journey (scroll story)
1. **Sealed envelope landing** — 3D envelope with couple-monogram wax seal, couple hashtag below, petals drifting; "Tap to open." Opening = flap lifts + gold light burst + shehnai note.
2. **Invocation** — Ganesha line-art draws itself (SVG stroke animation), shloka with English transliteration.
3. **Names reveal** — bride & groom names in large script with parents' names; gold shimmer sweep.
4. **Countdown** *(new)* — "18 days to forever" in gold numerals inside a mandala ring.
5. **Our Story / Meet the Couple** — polaroid timeline + favourites chips (from Bhushan-Pragyansa), illustrated avatars.
6. **Events schedule** — each ceremony is a full themed card in its own color world (Haldi = marigold yellow, Mehendi = green henna vines, Sangeet = starlit navy, Wedding = maroon-gold mandap) with per-event hashtag, frosted-glass detail panel, add-to-calendar button.
7. **Scratch-to-reveal surprise** — keep this crowd-pleaser (a fun couple photo or "shagun" message).
8. **Venue** — illustrated venue artwork that cross-fades to real map; Get Directions button.
9. **Family & blessings** — "Awaiting your gracious presence" card + **guest blessing wall / RSVP** *(new)*.
10. **Footer** — "With love, [couple]," music toggle (soft shehnai/flute loop), hashtag.

### Motion & interaction rules
- Every section fades/rises on scroll (IntersectionObserver), 400–600 ms, easing out — elegant, never bouncy.
- Ambient layer: slow-falling petals + occasional butterfly (all references do this; keep density low).
- Parallax on hero borders; gold shimmer on headings once per view.
- Background music off by default, floating toggle bottom-right.
- Mobile-first (most guests open on WhatsApp); desktop shows the same column beautifully centered on a textured backdrop — like Roopa-Anoop.

### Why this will impress
It keeps everything familiar that clients expect from these references (envelope, seal, shlokas, event cards) but adds five things none of the nine had: countdown, blessing wall/RSVP, add-to-calendar, story timeline, and a fully consistent custom couple-logo system carried from wax seal → hashtag → event cards → footer.

---

## 3. Build notes
- Single-page React (or plain HTML/CSS/JS) + Tailwind; SVG illustrations & stroke animations; Lottie for envelope/light burst; lazy-load heavy art; music via muted-until-tap audio.
- All art direction tokens (colors, motifs) kept as variables so the theme can be re-skinned per client religion/region in hours, not days.

## 4. Waiting on client details
Names & parents' names · religion/region (decides motif set: Warli/Pichwai/Sikh/South-Indian) · events + dates/times/venues · couple photos (or avatar preference) · hashtag (or we design one + a logo story like Deeksha-Chetan) · music choice · RSVP contact.
