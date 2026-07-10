# THE PAINTED GARDEN
## Original Luxury Wedding Invitation — Full Design & Build Blueprint
*Supersedes design-plan.md. References studied only for category understanding — nothing below copies them.*

---

# PART 1 — BRIEF vs. WHAT THE 9 REFERENCES ACTUALLY DO

| Dimension | What all 9 references do | What the brief demands | Verdict |
|---|---|---|---|
| Palette | Maroon/gold, terracotta, sage — mostly dark & saturated | Ivory, champagne, blush, sage, soft gold | **Replace.** Their palette is exactly the "heavy maroon/gold repetitive layout" to avoid |
| Opening | Identical pattern in all 9: static envelope + wax seal + "tap to open" | Cinematic multi-scene sequence, never the same twice | **Redesign.** Envelope-tap is now a category cliché |
| Backgrounds | Single flat texture + emoji flowers (🌸🦋) floating — literal clipart | Layered watercolor depth: foreground/midground/background, fog, light rays | **Replace.** The emoji particles are the clearest "random clipart" violation |
| Motion | One fade-up per section, falling emoji petals | Per-section unique transitions, parallax depth, 60fps ambient life | **Rebuild** on GSAP/Lenis instead of CSS-only |
| Typography | Great Vibes script + generic serif everywhere | Editorial luxury pairing, large spacing, hierarchy | **Upgrade** |
| Scratch card | Literal grey/gold "scratch to reveal" rectangle (5 of 9 sites) | Artistic reveal (mist clears, watercolor blooms) | **Reinvent** |
| Content depth | Names → events → family → venue map. Two sites add story/avatars | + Countdown, story, gallery, RSVP, travel/weather/dress code, footer signature | **Extend** — references are thin |
| Emotion | "A nice digital card" | "Entering a royal garden world" | The core gap |

**What the references get right (keep the *principles*, not the executions):** a ritual moment before content is shown; sacred invocation before names; per-event themed cards; music toggle; mobile-first single column; couple monogram used as a system.

**Their five weaknesses = our five opportunities:** clipart particles → painted particle engine; identical envelope → cinematic garden opening; flat scroll → depth + time journey; thin content → full guest experience; template feel → one bespoke illustrated world.

---

# PART 2 — THE ORIGINAL CONCEPT

## "The Painted Garden — From First Light to Fireflies"

One organizing idea no reference has: **the entire site is a single hand-painted royal garden, and scrolling moves you through one full day in it.** Guests don't browse sections — they walk through a garden as the light changes:

| Chapter | Time of day | Section | Ambient palette shift |
|---|---|---|---|
| I | Dawn mist | Opening + Invocation | Pearl, warm ivory, pale sage |
| II | Morning light | Names, quote, date, countdown | Cream, champagne, blush |
| III | Midday garden | Couple story + gallery | Sage, muted olive, soft terracotta |
| IV | Golden hour | Event schedule | Warm sand, soft gold, dusty rose |
| V | Twilight | Family + RSVP | Muted mauve, deep sage, firefly gold |
| VI | Night garden | Venue + farewell | Deep pine (never black), moonlight pearl, stars |

Butterflies by day gradually become fireflies by night. The sun's light rays angle lower as you scroll. This gives every section a *naturally different* transition and color world while remaining one coherent, handcrafted place — luxury through restraint, not ornament.

**Emotional hook:** the invitation itself is discovered *inside* the garden (Scene 2), so guests feel they were let into a private estate, not shown a webpage.

## Art direction

**Palette tokens**
```
--ivory:      #F7F2E9   (base paper)
--pearl:      #EFE9DD
--champagne:  #E4D3B0
--soft-gold:  #C7A96B   (accents, foil, never glossy yellow)
--blush:      #E8C9C0
--dusty-rose: #C99A92
--sage:       #A8B39A
--olive:      #7E8464
--terracotta: #C4795A   (small accents only)
--pine:       #2E3B33   (night sections; darkest value on site)
--ink:        #4A4238   (body text — warm, never pure black)
```

**Typography**
- Names/quotes: *Ivy Presto Display* or *Canela* class serif italic — editorial, not bridal-cliché. Handwriting moments (signature, notes): a custom-feel calligraphic like *Bickham* or SVG-stroke lettering.
- Labels/small caps: *Cormorant* or *Freight Display* with 0.35em letter-spacing.
- Body: same serif at 17–18px, 1.8 line-height, max 34ch.
- No Great Vibes / Dancing Script / Playfair — all overused in the category.

**Illustration system (everything custom, one consistent hand)**
- Style: loose watercolor botanicals with visible pigment blooms + fine ink linework, on cold-press paper texture. Motifs: white roses, peonies, jasmine vines, eucalyptus, olive branches, baby's breath, one signature bougainvillea spill, stone balustrades, a wrought-iron garden gate, a marble fountain, hanging crystal drops.
- Produced as ~14 layered "plates" (AI-assisted watercolor generation → hand cleanup → export as transparent WebP/AVIF + a few as SVG for stroke animation). Same brush language across every plate so nothing feels stock.
- Traditional touch, subtly: a gold *bandhanvar* (marigold-jasmine toran) across the gate, a lotus in the fountain, mehndi-fine linework inside the monogram, shehnai note in the soundscape. Royal-Indian by suggestion, not by maroon.

**Layer stack (every viewport, 5 depths)**
1. Paper grain + watercolor wash (fixed)
2. Distant painted landscape (parallax 0.2×)
3. Section content on "paper" cards (1×)
4. Botanical foreground spills entering from edges, slightly blurred (1.3×)
5. Living layer: particles, butterflies, light rays (canvas, above all)

---

# PART 3 — EXPERIENCE SPEC, SECTION BY SECTION

## 0. Opening sequence (the signature moment, ~11s, skippable)
- **S1 (0–2.5s):** Ivory mist on paper texture. Distant birdsong fades in after first tap/keypress (audio policy). Pollen drifts. A single butterfly crosses.
- **S2 (2.5–5.5s):** Mist thins; camera (scroll-locked container transform) drifts forward through a watercolor garden gate wrapped in jasmine; a *bandhanvar* of tiny gold marigolds hangs across it. On the gate: the couple's wax-seal monogram in soft gold.
- **S3 (interactive):** "Touch the seal" — on press, the silk ribbon threaded through the gate **unties itself** (SVG path animation), the gates swing inward with soft light bloom, and 3 butterflies escape toward the viewer.
- **S4 (3s):** Inside, an invitation card rests on a marble balustrade; it lifts, unfolds once (3D CSS fold with soft shadow), petals slip off it.
- **S5:** Names write themselves in calligraphy (SVG stroke-dashoffset), then subtitle → parents → invocation line fade in, staggered 400ms. Scroll indicator (a slowly falling petal) appears.
- Reduced-motion / repeat visitors / "skip" → elegant 1s crossfade straight to hero.
- **Alternates kept in the system** (so future clients never get the same opening): lotus blooms open on the fountain; a vintage glasshouse door; a music box lid. One is chosen per project, not per visit — consistency is luxury.

## 1. Hero — "Morning light"
Monogram (fine-line florals + initials) · names in large italic serif · one-line quote · date · **countdown as a growing vine**: a painted vine ring where leaves fill in as days pass, numerals in small caps beneath. Light rays sweep slowly; two butterflies orbit lazily. Floral corners only on two corners (asymmetry = editorial, not template).

## 2. Invitation message + artistic reveal
Replaces the category's scratch card: a card veiled in **painted mist — guests wipe it away with pointer/finger** (canvas destination-out brush with watercolor-edge falloff). Beneath: date, venue name, couple initials, one hidden butterfly that flies off on completion. Fallback: auto-clears on scroll for reduced motion.

## 3. Couple story — "Midday"
Cinematic horizontal chapter scroll (GSAP pinned): 4–5 memory scenes — *first meeting, the yes, families meet* — each a polaroid-on-paper collage with a handwritten caption (SVG stroke), a small painted map with a stitched travel line between their two cities, and an optional voice-note button styled as a wax-sealed letter that opens. Photos sit in torn-edge watercolor frames, never rectangles.

## 4. Gallery
A loose **photo stack on a marble table**: drag/swipe the top photo aside (Framer Motion drag + spring), it slides to the bottom with paper-shuffle shadow. Subtle light reflection sweeps glass-framed photos on hover. 8–12 images, lazy, blurhash placeholders.

## 5. Events — "Golden hour"
Each ceremony = a **fold-out invitation** in the garden, not a repeated card. Closed state: a small folded paper with ribbon + event monogram. On tap/scroll-into-view it unfolds (two-panel 3D fold) revealing its own painted world:
- *Haldi* — turmeric-wash sun, marigold sprigs (soft ochre, never loud yellow)
- *Mehendi* — olive/ sage henna-fine vinework
- *Sangeet* — twilight bougainvillea + hanging crystal drops, bokeh
- *Pheras/Ceremony* — dusty rose + gold, the garden's flower arch
Each: date, time, venue, dress-code color chips (small painted swatches), "Add to calendar" (ICS). Cards share layout grammar but zero repeated artwork.

## 6. Family — "Twilight"
Two facing paper cards (bride/groom side) with parents' and grandparents' names, tiny painted family motif (e.g., their home city's flower), soft inner shadow, no photos required. First fireflies appear here.

## 7. RSVP
Frosted-glass card floating over the darkening garden (backdrop-blur, 1px champagne border). Inputs underline-only with floating labels; button is magnetic with gold shimmer sweep. On submit: card exhales, **painted petals + fireflies burst gently** (canvas, not confetti rectangles), success message in calligraphy: "We'll keep a seat beneath the flowers for you." Backend: Google Form endpoint or simple API route + spreadsheet.

## 8. Venue & guest guide — "Night garden"
Illustrated nocturne of the venue (custom plate, moonlit) that **cross-fades into the live map** on toggle. Below, a guest guide in small elegant tabs: directions button, travel options, parking, 2–3 stay suggestions, wedding-week weather (live API, painted weather icons), dress code palette as fabric swatches, nearby landmarks.

## 9. Footer — farewell
Deep pine sky, painted stars + drifting fireflies, the monogram, an **animated signature** of both first names writing across, blessing line ("With love and their families' blessings"), music control, tiny "crafted with love" mark. Last butterfly of the site rests, folds its wings.

## Site-wide systems
- **Audio:** one ambient bed (soft strings + piano + distant birds; a single shehnai phrase at the opening; temple-bell shimmer at events). Starts after first interaction, ducked to −18 LUFS, always-visible toggle (animated equalizer petal).
- **Cursor (desktop only):** small gold-dot cursor with 300ms trailing sparkle; a butterfly occasionally drifts to it after 20s idle. Native cursor on touch/reduced-motion.
- **Micro-interactions:** paper-lift hover (2° tilt + shadow deepen), gold shimmer sweep on headings once per viewport entry, magnetic primary buttons (≤8px pull), ripple on press.
- **Per-section transitions (all different, all slow):** mist clears (opening→hero) · vines grow along edges (hero→reveal) · ink-wash wipe (story) · light-ray sweep (gallery) · paper unfold (events) · fog descends + fireflies rise (family/RSVP) · star-fade (venue→footer).

---

# PART 4 — HOW TO BUILD IT

## Stack
- **Next.js 14 (App Router) + TypeScript**, static export (`output: 'export'`) — it's a single page, host on Vercel/Netlify/CDN.
- **TailwindCSS** with the palette/typography tokens above as theme.
- **GSAP + ScrollTrigger** — chapter pinning, scroll-scrubbed light/color journey, horizontal story.
- **Lenis** — smooth scroll (synced to ScrollTrigger).
- **Framer Motion** — component-level micro-interactions, drag gallery, AnimatePresence for opening scenes.
- **Canvas 2D particle engine (custom, ~200 lines)** — pollen, petals, fireflies, mist erase, celebration burst. One shared rAF loop, pooled sprites, capped at 60 particles mobile / 120 desktop. **No Three.js** — nothing here needs WebGL; that's how we hold 95+ Lighthouse.
- **Lottie only if needed** for the ribbon untie; prefer raw SVG stroke animation everywhere (lighter).

## Architecture
```
app/
  layout.tsx                # fonts (next/font, display:swap), metadata, OG image
  page.tsx                  # section composition
components/
  opening/  OpeningSequence.tsx, GardenGate.tsx, RibbonUntie.tsx, SkipButton.tsx
  chapters/ Hero.tsx, MistReveal.tsx, Story.tsx, Gallery.tsx,
            Events.tsx (+EventFold.tsx), Family.tsx, Rsvp.tsx,
            Venue.tsx, Footer.tsx
  living/   ParticleCanvas.tsx, Butterflies.tsx, LightRays.tsx, DayNightController.tsx
  ui/       MagneticButton.tsx, PaperCard.tsx, SectionTransition.tsx,
            AudioToggle.tsx, Cursor.tsx, Monogram.tsx
lib/       gsap.ts, lenis.ts, particles/, ics.ts, weather.ts, rsvp.ts
content/   site.config.ts   # ALL couple data, events, palette chapter map — re-skinnable per client
public/art/                 # plates: gate, fountain, corners, event worlds… (AVIF/WebP + SVG)
```
`DayNightController` is the heart: one ScrollTrigger scrubs CSS custom properties (`--sky`, `--light-angle`, `--particle-mode`) across the whole page — every chapter's mood derives from it. That's one system, not six hacks.

## Asset pipeline (the real differentiator)
1. Generate watercolor plates with consistent style prompts (same paper, same pigment set) → curate → hand-clean edges → remove backgrounds.
2. Export AVIF+WebP at 2 sizes; hero plates ≤180KB, others ≤80KB; total illustration budget ≤1.6MB initial route.
3. Line elements (gate, ribbon, monogram, signature, vine countdown) drawn/traced as SVG for stroke animation.
4. Paper grain: one 512px tiling texture, multiply blend.

## Performance & accessibility (brief targets: Lighthouse ≥95, 60fps)
- Animate only `transform`/`opacity`; particles on canvas; `will-change` sparingly; everything below hero lazy via dynamic import + IntersectionObserver.
- Fonts subset, `next/font`, 2 families max. Preload only hero plate + grain.
- `prefers-reduced-motion`: kill particles/parallax/cursor, keep gentle fades — full content parity. Semantic landmarks, focus-visible styles, keyboard path through RSVP and events, contrast ≥4.5:1 for text (ink on ivory passes), alt text on all art.
- Test matrix: iPhone Safari (majority of guests via WhatsApp), Android Chrome, low-end throttled.

## Build order (7 milestones)
1. **Foundation** — tokens, fonts, config schema, paper background, deploy pipeline.
2. **Living engine** — particle canvas, DayNightController, Lenis+GSAP wiring. *(If this feels magical empty, everything after is easy.)*
3. **Opening sequence** — gate, ribbon, unfold, calligraphy. Skippable from day one.
4. **Hero + mist reveal + events folds** — the three "wow" content moments.
5. **Story, gallery, family** — content chapters.
6. **RSVP + venue guide** — forms, ICS, weather, map.
7. **Polish pass** — cursor, audio mix, transitions tuning, Lighthouse/reduced-motion/device QA.

## Needed from client (blocking items marked •)
• Names, parents, events with dates/times/venues · • 8–12 photos · • date for countdown · hashtag/monogram preference · story beats (3–5) · RSVP destination (sheet/email/WhatsApp) · music preference · dress codes · stay/travel notes · optional voice note.

---

## Why this wins the client
Every reference site is a maroon envelope you tap. This is a private garden that remembers the whole day — dawn for the blessing, golden hour for the celebrations, fireflies for the goodbye. Familiar traditions are all present (toran, lotus, shehnai, wax seal, invocation) but rendered in one original hand-painted world with editorial restraint. It reads as a luxury studio commission, and the `site.config.ts` + plate system means the *engine* is reusable while every client's *garden* is painted fresh.
