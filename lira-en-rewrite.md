# Lira — Rewrite EN (refonte-study)

Rules applied: 1 section = 1 point, 2-3 sentences max, no mirror / archaeology / hedge / wrapper, format matched to content type. Translated from lira-fr-rewrite.md and humanized.

---

## Section 1 — Context and challenge

**Image:** `contexte.jpg` + `lira-demo.mp4`

> ⚠️ Image note: `contexte.jpg` shows the **vocabulary notebook** (word list with Nouveau/En cours/Maîtrisé statuses and context sentences). It is a product screen, not an illustration of Lira vs competitors. The video likely compensates, but the image alone does not tell the positioning story. Worth checking on mobile where autoplay may not trigger.

**Before:**

> Language-learning apps each have their own blind spot.
>
> Duolingo builds habits, but its content remains artificial and many users plateau at an intermediate level. Anki is extremely powerful, but creating cards often takes more effort than reviewing them. LingQ moves closer to real reading, but the interface can be hard to navigate.
>
> Lira is built around a simple need: read real content, save words in context, and review them with an efficient repetition system. No heavy setup, no gamification.
>
> The product has been live since March 2026.

**After:**

> Language-learning apps all have their blind spot. Duolingo builds habits on artificial content. Anki is powerful, but making cards puts people off. LingQ gets close to real reading. The interface less so.
>
> Lira is built around one need: read real content, save words in context, review them. Live since March 2026.

**Cut:**
- §1 standalone → folded into the list
- "No heavy setup, no gamification" → wrapper
- §3 tightened, factual date kept

---

## Section 2 — Research and positioning

**Image:** `persona-01.jpg`, `persona-02.jpg`, `persona-03.jpg`

> ✅ Image OK: the 3 personas are shown visually. The original §5 (profile descriptions) is a direct mirror → cut.

**Before:**

> Research was conducted before launch, mainly through desk research: Reddit (r/languagelearning, r/Anki, r/duolingo, r/busuu...), LingQ forums, App Store reviews, and YouTube comments.
>
> These sources are biased toward frustration, but they are useful to understand where existing products fail.
>
> One pattern appears consistently: many learners plateau at an intermediate level. At that stage, reading becomes a natural next step. The challenge is not motivation, but making that transition easier.
>
> Another recurring friction is manual Anki card creation, often cited as a reason for dropping the tool.
>
> From this, three profiles emerged: an advanced user looking for speed and no friction, an expat wanting to read local content without breaking flow, and a regular user of apps like Duolingo who no longer feels progress.

**After:**

> Desk research before launch: Reddit (r/languagelearning, r/Anki, r/duolingo, r/busuu...), LingQ forums, App Store reviews, YouTube comments.
>
> Two patterns kept coming up: the plateau at intermediate level with no natural move toward reading, and manual Anki card creation, usually the reason people quit.

**Cut:**
- §2 hedge (source bias disclaimer)
- §3 condensed and merged with §4
- §5 mirror (profiles shown on the persona visuals)
- "At that stage, reading becomes a natural next step" → wrapper

---

## Section 3 — Design logic

**Image:** `flow.jpg`

> ✅ Image OK: the flow explicitly shows Reading → Tap word → Translation Window → [Audio / Translations tab / Definitions tab] → Save / Close. The two-tap behavior is readable. Panel positioning (bottom mobile / side desktop) is not in the flow diagram → worth keeping in text.

**Before:**

> Reading remains the primary activity. Everything else has to fit around it without interrupting it.
>
> The translation panel opens without replacing the page. The text stays visible. A word can be checked in a single gesture.
>
> Saving words required the most iteration. One tap opens the panel, another saves the word. Feedback is immediate: loading state, then confirmation and inline marking.
>
> Early versions used a full-screen overlay. It was dropped because it broke the reading flow and made users lose their place.
>
> The final version anchors at the bottom on mobile and on the side on desktop, without shifting the reading column.

**After:**

> Reading is the primary activity. Everything else has to work around it.
>
> The panel opens without replacing the page. One tap opens it, a second tap saves the word with its original sentence. Bottom on mobile, side on desktop: the reading column stays put.

**Cut:**
- §3 archaeology (full-screen overlay attempt)
- §5 mirror (visible in the flow and in screenshots)
- §2 condensed and merged into rewritten §2

---

## Section 4 — The reader

**Image:** `reader-large.jpg`, `reader-definitions.jpg`, `reader-mobile.jpg`

> ✅ Image OK: `reader-large.jpg` shows the word "alemán" tapped, panel open with phonetics (/ale'man/), 2 tabs (Translation / Definition BETA), translation + context sentence, "Save translation" button, Wiktionary and Reverso links. Audio icon visible. Text remains readable behind the panel.
>
> What the image does not show: that audio runs via a **local** engine (PiperTTS, not an external API) — non-obvious, worth keeping in text.

**Before:**

> The reader is the core of the product. The goal is simple: read without interruption.
>
> Clicking a word opens a panel with two tabs: translation and definition. The user sees phonetics and can trigger audio using a local TTS engine (PiperTTS).
>
> Everything happens in place. A second click saves the word, and a card is generated automatically using the original sentence as context.
>
> The idea is to turn reading into learning without switching modes.

**After:**

> Tapping a word opens the panel: translation, definition, phonetics, audio via PiperTTS (local). A second tap saves the word with its original sentence as context.

**Cut:**
- §1 wrapper/title echo
- "Everything happens in place" → mirror (visible in image)
- §4 wrapper

---

## Section 5 — Library and import

**Image:** `biblio.jpg`

> ✅ Image OK: shows 3 states in one frame — Gutenberg library (Cervantes books), import area (EPUB/PDF/TXT/HTML/URL), and import text editor. Import formats are readable directly in the image.
>
> ⚠️ Note: the image also shows **HTML** as an import format, which was missing from the original text. Added.
>
> What the image does not show: available Gutenberg languages → kept in text.
>
> What the image already shows: reading progress and saved-word counts are visible in `contexte.jpg` (the vocabulary notebook) → §3 cut.

**Before:**

> Import accepts a URL, plain text, EPUB, or PDF. Users read what they want, with no imposed catalog.
>
> For people who want a starting point, Lira integrates Project Gutenberg: some public-domain books directly available in the app, including novels, short stories, and essays in Spanish, German, English, Italian, and more.
>
> Imported texts and Gutenberg books live in the same personal library. Each text shows reading progress and saved-word count.

**After:**

> Import: URL, EPUB, PDF, HTML or plain text. Project Gutenberg is built in, with public-domain books in Spanish, German, English and Italian.

**Cut:**
- "Users read what they want, with no imposed catalog" → wrapper
- §3 mirror (progress visible in the vocabulary notebook)
- HTML added (missing from original, visible in image)

---

## Section 6 — Review and crosswords

**Image:** `crossword.jpg`, `revision.jpg`, `stats.jpg`

> ✅ Image OK: `crossword.jpg` shows a crossword built from personal vocabulary (destino, libro, parque, verdad...) with French translations as clues. The "generated from personal vocab" principle is clear from the image.
>
> What the image does not show: FSRS, the original sentence as a hint, the post-reading mini-quiz → kept in text.

**Before:**

> Review relies on FSRS with contextual recall. The user has to retrieve a word or its translation, with the option to reveal the original sentence if needed.
>
> Memorization happens through both the word itself and its usage context.
>
> After a few minutes of reading and a few saved words, a short optional quiz appears, based on the current session.
>
> Crosswords are generated from personal vocabulary. They offer an alternative to flashcards for users who want a different review format.

**After:**

> FSRS-based review with contextual recall. Users look up a word or its translation, with the original sentence available when in doubt. After a reading session, a short optional quiz appears based on words from that session.
>
> Crosswords pull from personal vocabulary.

**Cut:**
- §2 mirror ("Memorization happens through both the word itself and its context" — echo of contextual recall)
- "They offer an alternative to flashcards for users who want a different review format" → wrapper

---

## Section 7 — Design

**Image:** `landing.jpg`, `dark.jpg`, `profil.jpg`

> ✅ Image OK: `dark.jpg` shows dark mode with the word "popular" tapped — very dark background, light text, identical panel behavior to light mode, green button preserved. Literata is visible in the reading body text.
>
> What the image does not show: font names (Literata/Satoshi) and the reason for the tinted background → kept in text.
>
> What the image already shows: dark mode works, the palette (green/brown/tinted background) → §4 mirror, cut.

**Before:**

> Visual choices are driven by reading comfort.
>
> Literata is used for long-form text to improve readability, while the interface relies on Satoshi for functional clarity.
>
> The background uses a slightly warm tone to reduce fatigue compared to pure white. Colors are limited: a green for actions and a dark brown for text.
>
> Dark mode follows the same logic, with adjusted contrast to support long reading sessions.

**After:**

> Literata for long-form text, Satoshi for the interface. Background slightly tinted to cut eye strain from pure white. Limited palette: green for actions, dark brown for text.

**Cut:**
- §1 wrapper ("Visual choices are driven by reading comfort")
- §4 mirror (dark mode visible in image)
- §2+§3 merged and tightened
