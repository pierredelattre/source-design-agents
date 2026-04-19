# UX/UI Reference — Synthesised Concepts

Derived from:
- `UI/UX Design Guide` — Joel Parker Henderson (EPUB, 2024)

Use this file as a lookup reference for UX/UI concepts, methods, and checklists. Cite principles from here; do not paste raw EPUB content into prompts.

---

## 1. Core distinctions

| Term | Definition |
|------|-----------|
| UI (User Interface) | The visual and interactive layer users touch — layout, components, typography, colour, motion |
| UX (User Experience) | The full experience of using a product — usability, flow, emotional response, value delivery |
| CX (Customer Experience) | The end-to-end relationship between a customer and an organisation, across all touchpoints |
| UCD (User-Centered Design) | A design process that centres real users' needs, goals, and contexts at every stage |

---

## 2. Research methods

| Method | When to use |
|--------|-------------|
| Personas | Synthesise user research into representative archetypes to guide decisions |
| Journeys / Journey maps | Visualise the full user flow across touchpoints; find pain points and moments of delight |
| Focus group | Explore attitudes and mental models with a small group; qualitative, not quantitative |
| Voice of the Customer (VoC) | Capture direct user feedback at scale; useful for prioritisation |
| Diary study | Longitudinal, in-context data; reveals behaviour over time rather than in a test session |
| Critical Incident Technique (CIT) | Ask users to recall specific moments of success or failure; surfaces real edge cases |
| Task analysis / HTA | Decompose a user goal into steps; find where the design creates friction |

---

## 3. Information architecture

Key IA concepts:
- **IA** defines the structure, organisation, and labelling of content — before any visual design.
- A good IA reflects users' mental models, not the organisation's internal structure.
- Tools: card sorting, tree testing, site maps, decision trees, mind maps.
- The site map is a deliverable; the IA is the reasoning behind it.

---

## 4. Ideation methods

| Method | Best for |
|--------|---------|
| Brainstorming | Volume of raw ideas; defer judgement |
| SCAMPER | Challenging assumptions on an existing design (Substitute, Combine, Adapt, Modify, Put to other uses, Eliminate, Reverse) |
| Thinking Hats (de Bono) | Structured multi-perspective review of a proposed solution |
| Design charrette | Intense, cross-functional collaborative session; fast convergence |
| Storyboard | Visualise a user flow in context before building; surfaces narrative gaps |
| Futurespective | Imagine a future state (success or failure) and reason backwards |

---

## 5. Usability

Core principles (Jakob Nielsen's 10 Heuristics):
1. Visibility of system status
2. Match between system and the real world
3. User control and freedom
4. Consistency and standards
5. Error prevention
6. Recognition rather than recall
7. Flexibility and efficiency of use
8. Aesthetic and minimalist design
9. Help users recognise, diagnose, and recover from errors
10. Help and documentation

**Cognitive load**: reduce unnecessary complexity; chunk information; use progressive disclosure.
**Usability friction**: identify and eliminate steps that slow users without adding value.

---

## 6. Accessibility

Key standards and concepts:
- **WCAG** (Web Content Accessibility Guidelines): the normative standard. Levels A, AA, AAA. Minimum target: AA.
- **ARIA attributes**: semantic roles and states for screen readers. Use native HTML first; ARIA as a fallback.
- **Screen readers**: design and test with VoiceOver (macOS/iOS) and NVDA/JAWS (Windows).
- **Colour blindness**: never rely on colour alone to convey information; test with colour-blindness simulators.
- **Keyboard navigation**: all interactive elements must be reachable and operable via keyboard alone.
- **Alternative text**: all meaningful images need descriptive alt text; decorative images use `alt=""`.

Accessibility is not a feature — it is a baseline quality criterion. The DS is the right place to enforce it at scale.

---

## 7. Design system and pattern library concepts (EPUB definitions)

- **Design system**: the broadest concept — principles, rules, guidelines, and the pattern library together.
- **Style guide**: documentation of brand language, component rationale, and usage rules.
- **Pattern library**: collection of reusable UI building blocks.
- Reference implementations: Apple HIG, Google Material Design, UK Government Design Principles.

---

## 8. Prototyping

| Type | When to use |
|------|-------------|
| Low-fidelity / wireframe | Validate structure and flow before investing in visual design |
| High-fidelity / mockup | Test visual design and micro-interactions; stakeholder sign-off |
| WYSIWYG prototype | Test with real or near-real content; reduces abstraction gap |

---

## 9. UX writing and microcopy

- Microcopy: labels, tooltips, error messages, empty states, button text. High impact per word.
- Copywriting principles: clarity over cleverness, action-oriented labels, error messages that suggest a fix.
- Localization: design for text expansion (some languages are 30-40% longer than English), bidirectional text (Arabic, Hebrew), and locale-specific conventions.

---

## 10. Testing methods

| Method | What it measures |
|--------|----------------|
| Split (A/B) testing | Which of two variants performs better on a metric |
| Acceptance testing | Whether a feature meets agreed criteria |
| Accessibility testing | WCAG compliance, screen reader behaviour |
| Localization testing | Correct rendering, cultural appropriateness across locales |
| Heatmap | Where users look and click; reveals attention and friction patterns |
| Benchmark testing | Performance against a baseline over time |

---

## 11. AI in UX/UI (emerging)

- AI form fill, AI content generators, AI image generation are reshaping interaction patterns.
- Design for AI outputs: handle variable-length content, error states, and confidence indicators.
- AI internationalization: machine translation is improving but still requires human review for tone and cultural nuance.
