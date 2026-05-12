## Version FR (locale FR)

### Intro projet
MBA My Business Academy est un projet de construction d’un écosystème digital complet pour un organisme de formation certifié Qualiopi, avec un double objectif: convertir sur le site vitrine public et structurer la décision sur un espace documentaire fondateur privé.

J’ai piloté la phase stratégique en tant que product designer en lead, en cadrant les enjeux avant la production visuelle, avec une approche centrée utilisateurs et une passation claire vers le développement.

### 1. Contexte business et contraintes
Le point de départ était simple: installer une présence en ligne crédible pour des publics B2C (reconversion, salariés en évolution) et B2B (employeurs, responsables RH), dans un contexte réglementaire exigeant.

La contrainte principale n’était pas de “faire un site joli”, mais de tenir ensemble quatre objectifs:
- acquisition organique via le SEO,
- réassurance immédiate sur la certification Qualiopi,
- lisibilité des parcours,
- capacité interne à maintenir le contenu dans le temps.

Autre contrainte forte: le niveau de maturité du projet. Certaines preuves de performance n’étaient pas encore disponibles à grande échelle. Il fallait donc une narration honnête, solide et orientée décision, sans inventer d’impact.

Côté structuration produit, j’ai séparé deux briques:
- un site vitrine orienté conversion,
- un site documentaire fondateur orienté gouvernance, qualité et pilotage de contenu.

Cette séparation évite de mélanger besoins marketing et besoins internes dans un même espace mal gouverné.

### 2. Cadrage et recueil des besoins
J’ai organisé le cadrage autour d’une chaîne claire: sources brutes -> documentation structurée -> contenu publiable -> applications.

Le recueil des besoins a été mené en partant des décisions produit à prendre, et non des demandes d’interface isolées.

Trois besoins prioritaires se sont imposés:
1. Rendre l’offre compréhensible rapidement avec des entrées par intention.
2. Réduire la friction de prise de contact avec des appels à l’action explicites.
3. Installer la confiance tôt dans le parcours avec des preuves claires.

J’ai aussi cadré les besoins internes:
- publier vite sans perdre en qualité,
- garder une cohérence éditoriale,
- limiter la dette documentaire.

Une alternative a été écartée: démarrer directement en maquettes haute fidélité. C’était rapide en apparence, mais risqué sans validation préalable de l’architecture d’information et des priorités de contenu.

### 3. Recherche exploratoire et analyse concurrentielle
J’ai mené une recherche exploratoire sur plus de six acteurs du secteur, avec un angle croisé UX, conversion, SEO, accessibilité RGAA et stratégie tarifaire.

L’objectif n’était pas de reproduire des interfaces, mais d’identifier les schémas qui réduisent l’incertitude produit.

Principaux enseignements:
- Les parcours efficaces commencent par une intention utilisateur claire.
- Le financement est un frein majeur, souvent traité trop tard.
- Plusieurs acteurs présentent des faiblesses structurelles (liens cassés, dépendance excessive au JavaScript, opacité tarifaire, accessibilité faible), ce qui ouvre une opportunité de différenciation.

J’ai utilisé des flux de travail augmentés par IA (Codex / Claude) pour accélérer les audits, consolider les comparatifs et produire des rapports de décision. L’IA a servi d’accélérateur, pas de décideur.

Alternative écartée: un benchmark purement visuel. Trop séduisant, mais peu utile dans un contexte de formation certifiante où la clarté, la conformité et la confiance priment.

### 4. Synthèse des besoins utilisateurs et personas
J’ai construit des proto-personas opérationnels:
- Personne en reconversion: cherche une formation finançable et un débouché concret.
- Salarié en évolution: cherche une formation compatible avec ses contraintes de temps.
- Porteur de projet: attend un accompagnement utile et applicable.
- Employeur / RH: veut des preuves de sérieux, de conformité et de fiabilité.

Besoin transversal: “Décider vite sans zone d’ombre”.

Implications directes:
- information scannable,
- hiérarchie claire,
- appels à l’action précis,
- réassurance répartie dans tout le parcours.

J’ai écarté l’approche “catalogue complet dès l’entrée”, car elle augmente la charge cognitive et ralentit la décision.

### 5. Principes UX et priorisation
Principes retenus:
- clarté avant densité,
- réassurance continue,
- mobile en priorité,
- accessibilité par défaut,
- gouvernance éditoriale explicite.

Priorisation du parcours principal:
1. page d’accueil,
2. pages catégories,
3. fiches formation,
4. contact et demande d’information contextualisée.

Ce choix a été préféré à une exécution en parallèle de toutes les pages, trop coûteuse en cohérence et en qualité de passation.

### 6. Architecture de l’information et parcours utilisateurs
L’architecture repose sur une hiérarchie robuste:
- accueil -> catalogue -> catégories -> fiches formation,
- pages transverses: financement, organisme, contact, obligations légales.

Parcours quotidiens clés:
- reconversion: recherche -> fiche -> financement -> prise de contact,
- employeur: preuve de conformité -> offre ciblée -> demande de proposition.

Personnalisation progressive, sans sur-complexité:
- préremplissage contextuel des formulaires,
- appels à l’action adaptés à l’intention,
- formulations orientées situation.

Réassurance structurée:
- signaux de confiance visibles aux moments de décision,
- certification explicite,
- promesse réaliste sur les résultats.

Alternative écartée: une page d’accueil très dense “tout-en-un”, qui dilue le message et allonge le temps d’accès à l’information utile.

### 7. Feuille de route design (maquettes à venir), limites, risques, prochaines étapes
Le socle stratégique est posé: cadrage, recherche, architecture, principes UX, gouvernance.

Les maquettes UI sont volontairement annoncées “à venir” pour respecter l’ordre de travail: stratégie validée d’abord, expression visuelle ensuite.

Limites actuelles:
- pas encore de mesure en production de la conversion,
- pas encore de test sur prototype haute fidélité,
- UI Kit à produire complètement dans la phase suivante.

Risques:
- dérive institutionnelle si la direction visuelle devient trop rigide,
- dette éditoriale si les règles de gouvernance ne sont pas appliquées,
- perte de clarté si le périmètre s’élargit avant stabilisation du parcours principal.

Prochaines étapes:
1. traduire les principes en maquettes,
2. construire l’UI Kit (fondations, composants, variantes),
3. préparer la passation front,
4. lancer une première version instrumentée,
5. itérer sur la base de signaux réels.

### 8. Cadre d’impact business
Indicateurs prévus:
- taux de conversion visite -> demande,
- temps d’accès à l’information clé,
- taux de clic sur les appels à l’action principaux,
- qualité des leads (demandes complètes et exploitables),
- progression dans l’entonnoir (accueil -> catégorie -> fiche -> formulaire),
- conformité éditoriale (structure, SEO, accessibilité RGAA).

---

## EN Version (locale EN)

### Project intro
MBA My Business Academy is a full digital ecosystem project for a Qualiopi-certified training organization, with a dual objective: conversion on the public website and decision support on a private founder documentation platform.

I led the strategic phase as lead product designer, framing key decisions before visual production, with a user-centered approach and a clear handoff path to development.

### 1. Business context and constraints
The starting point was straightforward: build a credible online presence for both B2C audiences (career switchers, employees upskilling) and B2B audiences (employers, HR), under strong regulatory and trust constraints.

The core challenge was not visual polish. It was aligning four goals at once:
- organic acquisition through SEO,
- early Qualiopi reassurance,
- clear user journeys,
- long-term content maintainability.

Another key constraint was project maturity. Some performance proof points were not yet available at scale, so the narrative had to stay rigorous and honest, without invented impact.

I split the product into two layers:
- a conversion-oriented public website,
- a governance-oriented founder documentation site.

This avoided a common failure mode: mixing marketing needs and internal operational needs in one poorly governed product.

### 2. Framing and needs collection
I structured framing with a clear chain: raw sources -> structured documentation -> publishable content -> applications.

Needs collection focused on product decisions, not isolated interface requests.

Three priorities emerged:
1. Make the offer understandable quickly through intent-based entry points.
2. Reduce contact friction with explicit calls to action.
3. Build trust early in the journey with clear reassurance signals.

I also defined internal needs:
- publish quickly while preserving quality,
- keep editorial consistency,
- reduce documentation debt.

One option was rejected: jumping directly to high-fidelity mockups. It looked fast, but was too risky without validating information architecture and content priorities first.

### 3. Exploratory research and competitive analysis
I ran exploratory research across more than six competitors, with a combined lens on UX, conversion, SEO, accessibility, and pricing strategy.

The objective was not to copy interfaces, but to identify repeatable patterns that reduce product uncertainty.

Key findings:
- Strong journeys start from clear user intent.
- Funding information is a major decision blocker, often surfaced too late.
- Many competitors show structural weaknesses (broken pages, heavy JavaScript dependency, pricing opacity, weak accessibility), creating a clear differentiation opportunity.

I used AI-augmented workflows (Codex / Claude) to speed up audits, consolidate comparisons, and produce decision-ready reports. AI acted as an accelerator, not the decision maker.

Rejected option: purely visual inspiration benchmarking. Attractive, but weak in a certified training context where clarity, compliance, and trust matter most.

### 4. User needs synthesis and personas
I built operational proto-personas:
- Career switcher: needs funded training and a credible job outcome.
- Employee in progression: needs a format compatible with time constraints.
- Entrepreneur profile: needs practical, directly applicable support.
- Employer / HR: needs proof of reliability, compliance, and execution quality.

Cross-cutting need: “Help me decide fast, with no blind spots.”

Direct implications:
- scannable information,
- clear hierarchy,
- explicit calls to action,
- reassurance distributed across the journey.

I rejected the “full catalog first” approach at entry level because it increased cognitive load and slowed down decisions.

### 5. UX principles and prioritization
Selected principles:
- clarity before density,
- continuous reassurance,
- true mobile-first structure,
- accessibility by default,
- explicit editorial governance.

Priority flow:
1. homepage,
2. category pages,
3. training detail pages,
4. contextual contact and lead forms.

This was chosen over parallel production of all pages, which would have harmed consistency and handoff quality.

### 6. Information architecture and user journeys
The architecture relies on a clear hierarchy:
- home -> catalog -> categories -> training pages,
- transversal pages: funding, organization, contact, legal.

Core recurring journeys:
- career switcher: search -> training page -> funding -> contact,
- employer: compliance proof -> targeted offer -> proposal request.

Progressive personalization without over-engineering:
- contextual form prefill,
- intent-based calls to action,
- situation-specific wording.

Reassurance strategy:
- trust signals visible at decision points,
- explicit certification framing,
- realistic promise level.

Rejected option: an overloaded one-page homepage. It diluted priorities and increased time-to-information.

### 7. Design roadmap (mockups coming soon), limits, risks, next steps
The strategic foundation is complete: framing, research, architecture, UX principles, governance.

UI mockups are intentionally marked as “coming soon” to keep a healthy sequence: strategic validation first, visual execution second.

Current limits:
- no live conversion data yet,
- no high-fidelity usability testing yet,
- full UI Kit still to be produced in the next phase.

Risks:
- drifting toward an overly institutional visual tone,
- editorial debt if governance rules are not applied,
- reduced clarity if scope expands before the core journey is stabilized.

Next steps:
1. translate principles into visual mockups,
2. build the UI Kit (foundations, components, variants),
3. prepare front-end handoff,
4. launch an instrumented first release,
5. iterate from real usage signals.

### 8. Business impact framework
Planned KPIs:
- visitor-to-lead conversion rate,
- time to key information,
- primary call-to-action click rate,
- lead quality (complete and actionable submissions),
- funnel progression (home -> category -> detail page -> form),
- editorial compliance rate (structure, SEO, accessibility).
