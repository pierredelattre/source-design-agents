# Septieme Seance - EN Rewrite (refonte-study)

Applied rules: 1 section = 1 point, 2-3 sentences max, mirror / archaeology / hedge / wrapper removed, format adapted to content.

---

## Section 1 - Context and challenge

**Image:** `contexte.jpg`

> ✅ Image likely covers context (problem + usage). The text can keep product framing, the speed-to-access constraint, and the service shutdown linked to API access.

**Before:**

> Existing cinema services provide a lot of information, but rarely in a format that is immediately usable. Users often have to move through several screens before seeing nearby showtimes, sometimes without reliable location handling.
>
> The issue was not lack of content, but lack of hierarchy and speed of access. The product goal was clear: let users understand what is playing nearby within seconds and choose a session without friction.
>
> The service was designed and launched as a full product, from research to release. It stopped after API access restrictions, but it remains a representative case of a full product cycle under real technical constraints.

**After:**

> Cinema services provide plenty of information, but rarely in a format you can use right away. The goal was to shorten the time between entry and choosing a showtime.
>
> The product was designed and launched end to end. It stopped after API access restrictions, but it remains a concrete example of a full product cycle under technical constraints.

**Cut:**
- Redundant detail on multi-screen navigation (if already visible in following screens)
- Overextended wording around "friction"

---

## Section 2 - Geolocation or manual search

**Image:** `geoloc.jpg`

> ✅ The image already shows the two entry points. The text should keep the product logic: fast access to a first useful answer.

**Before:**

> Two entry points were designed: geolocation or manual search. The challenge was not adding options, but reducing time to a first relevant answer.
>
> Geolocation immediately shows nearby cinemas with an adjustable radius. Manual search covers cases where users think in terms of a specific place, movie, or theater.
>
> Both modes converge toward the same objective: deliver usable results with minimal interaction.

**After:**

> Two entry points: geolocation or manual search. The goal was to get a first useful answer in just a few interactions.
>
> Geolocation shows nearby cinemas with an adjustable radius. Manual search covers place-driven, movie-driven, or cinema-driven queries.

**Cut:**
- "The challenge was not adding options" (wrapper)
- Closing sentence that repeats the two core lines

---

## Section 3 - Search filters

**Images:** `filter-films.jpg`, `filter-perimetre.jpg`, `filter-langue.jpg`

> ✅ The images already show filter types. The text should keep usage logic, not repeat every UI control.

**Before:**

> To support search, filters were added to allow more precise sorting based on context.
>
> Some filters refine results by genre, year, duration, and recent films vs cult films still playing. Users can also filter by accepted subscriptions (UGC, Pathe...).
>
> Users can set distance around the geolocated point or around a manually selected city/cinema. They can also choose a target date to view matching showtimes.
>
> Language and subtitle handling is also included. The idea is to let everyone adapt display to their constraints.

**After:**

> Filters turn a broad list into a selection users can act on quickly.
>
> They cover content (genre, year, duration, recent/cult), context (distance, date, subscriptions), and session constraints (languages, subtitles).

**Cut:**
- Repeated "users can" phrasing
- Over-detailed UI listing already visible in screenshots

---

## Section 4 - Nearby showtimes list

**Image:** `projections.jpg`

> ✅ The image carries the list structure. Text should stay focused on the promise: readability plus fast decisions.

**Before:**

> Once the area is defined, showtimes appear immediately. Cinemas are sorted by proximity, with direct access to same-day sessions.
>
> The layout is intentionally compact and mobile-first: each element should be scannable in seconds. The goal is not to expose all data, but to support fast decisions.
>
> Each screen is designed to reduce uncertainty: where, when, and what to watch.

**After:**

> As soon as the area is set, showtimes appear and cinemas are sorted by proximity.
>
> The list is compact and mobile-first to support fast scanning and immediate decisions.
>
> Compactness serves a simple goal: less scan time, faster decisions.

**Cut:**
- "not to expose all data" (explanatory wrapper)
- "reduce uncertainty" (good idea, but overly conceptual wording)

---

## Section 5 - Product decisions and trade-offs

**Images:** `filter-empty.jpg`, `filter-seances.jpg`, `filter-results.jpg`

> ✅ Interface states illustrate trade-offs. Text keeps structural choices (intent focus, readability, deliberate removals).

**Before:**

> The first screen is a search bar with no distractions. Users arrive with a clear intention: see what is playing now or tonight.
>
> Results are organized for readability: poster grid, key information visible immediately, filters split between content and location.
>
> Several trade-offs structured the product:
>
> - Letterboxd integration was dropped. Relevant in some contexts (large catalog), but it did not improve decisions in most cases.
> - Price display was removed. While technically possible, data was too incomplete at scale (2,300 cinemas, multiple sessions). Partial information would have reduced trust.
>
> These decisions reflect a simple product logic: prioritize reliability and decision speed over feature richness.
>
> Stack: React, Tailwind, Figma, Heroicons.

**After:**

> The product is centered on an immediate intent: find what to watch now or tonight.
>
> Two trade-offs shaped this version: dropping Letterboxd integration and removing prices, because data stayed too incomplete at scale and hurt trust.

**Cut:**
- Layout details already visible in screenshots
- "These decisions reflect..." (wrapper)
- Tech stack (keep elsewhere if needed)

---

## Section 6 - Future improvements

**Images:** `notes.jpg`, `alertes.jpg`, `letterboxd.jpg`

> ✅ The images cover improvement tracks. Text keeps the user-testing insight and product priorities.

**Before:**

> Testing revealed an unexpected behavior: several users searched directly by cinema instead of using geolocation. Their need was different: seeing a full multi-day program.
>
> This led to two priority evolutions: cinema search with autocomplete, and multi-day cinema pages.
>
> Next iterations aimed to enrich the experience without compromising simplicity: highlighting the next session, personalized alerts, useful metadata (formats, premieres), and filter improvements (counters, reset, real-time feedback).
>
> Each improvement is evaluated by one criterion: does it reduce the time needed to make a decision?

**After:**

> Testing revealed a complementary need: searching directly for a cinema to view its multi-day schedule.
>
> Priorities selected: cinema search with autocomplete and multi-day cinema pages, followed by targeted enrichments (next session, alerts, useful metadata, improved filters) without adding friction to the journey.

**Cut:**
- "unexpected behavior" (unnecessary dramatization)
- Final rhetorical question (criterion stays implicit in the text)
