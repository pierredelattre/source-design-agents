# Design Systems — Synthesised Principles

Derived from:
- `Atomic Design` — Brad Frost (2016)
- `Design Systems` — Alla Kholmatova (2017)
- `Expressive Design Systems` — Yesenia Perez-Cruz (2019)
- `Hackez le Design System` — Idean France (2019)
- `Design Systems Handbook` — InVision (2017)

Use this file as a conceptual reference. Cite principles and patterns from here; do not paste raw source text into prompts.

---

## 1. What a design system actually is

A design system is broader than a pattern library or style guide:
- **Pattern library**: collection of reusable UI building blocks.
- **Style guide**: documentation of brand language, component rationale, and usage rules.
- **Design system**: encompasses both, plus the underlying design principles, shared language, and team practices that make them coherent over time.

Components alone do not create consistency. The shared language and culture around patterns matter as much as the artefacts themselves (Kholmatova).

---

## 2. Component architecture (Atomic Design)

The atomic metaphor provides a mental model for component hierarchy:

| Level | Description | Examples |
|-------|-------------|---------|
| Atoms | Smallest indivisible UI elements | Button, input, label, icon |
| Molecules | Groups of atoms working together | Search field (input + button) |
| Organisms | Complex UI sections | Header, card grid, navigation |
| Templates | Page-level skeletons | Article layout, dashboard shell |
| Pages | Templates filled with real content | Live product screen |

Key principle: design systems, not pages, are the right unit of work. A 30,000-page site is often just 3 content types and 2 layouts.

---

## 3. Functional vs. perceptual patterns (Kholmatova)

- **Functional patterns** (modules): tangible, behavioural building blocks — buttons, forms, menus, headers.
- **Perceptual patterns** (styles): descriptive, aesthetic elements — iconography style, colour palette, typography — that create emotional connection and brand coherence.

Both must be systematised. Most teams start with functional patterns; perceptual patterns are equally important and often neglected.

---

## 4. Expressiveness and brand (Perez-Cruz)

An expressive design system has three qualities:
1. **Purpose-built**: aligned to the brand's voice, visual style, and intended behaviour.
2. **Supports a range of expression**: enables meaningful experimentation and divergence while retaining systemic coherence.
3. **Inspires use**: designers feel motivated to solve problems *with* the system, not *around* it.

The goal is cohesion across touchpoints, not uniformity. Variation is a feature, not a bug — as long as it is intentional and governed.

---

## 5. Design principles

Design principles are the bridge between brand values and design decisions. A good principle:
- Is specific enough to guide a concrete choice
- Is genuinely debatable (not a platitude)
- Can be used to resolve conflict between two valid options

Principles should precede pattern creation, not follow it.

---

## 6. Governance models (Idean, Perez-Cruz)

Two archetypes:
- **Strict (centralised)**: one team owns and controls all DS contributions. High consistency, lower speed of adoption, risk of bottleneck.
- **Loose (federated)**: product teams contribute; DS team curates. Higher adoption, higher risk of drift.

Most successful organisations use a federated model with clear contribution guidelines and a DS team acting as curators, not gatekeepers.

Key governance artefacts:
- Contribution model (who can add/change what)
- Versioning and deprecation policy
- KPIs for DS health (adoption rate, component coverage, accessibility score)
- Communication channels (changelog, newsletter, office hours)

---

## 7. Shared language

A DS without a shared vocabulary drifts. Teams invent local names for the same pattern, leading to fragmentation.

Practices:
- Name components consistently across design and code
- Document naming rationale, not just the names
- Conduct interface inventories to surface naming conflicts before they calcify
- Treat the shared language as a living artefact that evolves with the product

---

## 8. Building and scaling (InVision Handbook)

Step-by-step arc:
1. **Audit existing UI** — interface inventory to find patterns already in use
2. **Define visual language** — colours, type, spacing, iconography
3. **Build component library** — starting with highest-frequency, highest-leverage components
4. **Document and publish** — style guide with rationale and usage examples
5. **Integrate into workflow** — design and engineering tooling (Figma libraries, code packages)
6. **Scale** — governance, contribution model, expansion to new platforms/products

A DS is never "done". It evolves gradually with the product.

---

## 9. Accessibility as a DS responsibility

Accessibility should be baked into the DS, not bolted on:
- Components must meet WCAG contrast requirements by default
- Interactive states (focus, hover, active, disabled) must be designed and documented
- Semantic structure decisions (heading hierarchy, landmark roles) belong in the DS
- The DS is the highest-leverage place to fix accessibility at scale

---

## 10. When a DS stifles creativity

Common failure modes (Perez-Cruz, Idean):
- **Over-rigidity**: system becomes a constraint machine; designers work around it
- **Under-documentation**: patterns exist but no one knows how to use or extend them
- **No variation model**: no principled way to deviate, so deviation is either forbidden or chaotic
- **Neglected maintenance**: system grows stale; teams stop trusting it

Antidotes: purpose statements, contribution models, regular audits, and treating the DS team as enablers rather than police.
