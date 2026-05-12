# Talkie - Reécriture FR (refonte-study)

Regles appliquees : 1 section = 1 point, 2-3 phrases max, suppression miroir / archeologie / hedge / wrapper, ton naturel, sans demi-cadratin.

---

## Section 1 - Contexte et enjeux

**Image :** `contexte.jpg`

> ✅ L'image couvre deja le contexte produit. Le texte doit garder le probleme de progression percue et l'intention de conception.

**Avant :**

> Les apps d’apprentissage des langues fonctionnent bien pour créer une habitude, mais la progression ressentie n’est pas toujours au rendez-vous. Les utilisateurs reviennent chaque jour, sans forcément avoir le sentiment d’apprendre efficacement.
>
> Les entretiens ont confirmé cette tension entre engagement et progression. Plutôt que d’optimiser la rétention, on a voulu explorer une autre direction : comment rendre la progression plus visible, et proposer des situations d’apprentissage plus proches du réel.

**Apres :**

> Les apps de langue installent une habitude, mais la progression percue reste souvent floue. Les utilisateurs reviennent, sans toujours sentir qu'ils avancent.
>
> Le projet est parti de ce point : rendre la progression visible et proposer des situations d'apprentissage plus proches de l'usage reel.

**Coupe :**
- Formulation "plutot que" qui oppose retention et apprentissage de maniere un peu theorique
- Tournure longue sur "tension engagement/progression"

---

## Section 2 - Recherche utilisateur

**Images :** `per.jpg`, `entr.jpg`, `fonctions.jpg`

> ✅ Les visuels portent les profils et les insights. Le texte doit garder les irritants concrets et la conclusion commune.

**Avant :**

> Trois entretiens semi-directifs de 30 minutes avec des utilisateurs actifs d’apps concurrentes.
>
> Le premier utilise Duolingo pour préparer un voyage. Il se sent bloqué : il ne peut pas sauter les notions déjà acquises et confond régulièrement des mots proches.
>
> Le second utilise MemRise dans un cadre professionnel. Il a arrêté car les exercices étaient trop simples, répétitifs, et ne lui donnaient pas de vision claire de sa progression.
>
> Le troisième cherche à apprendre du vocabulaire spécifique à son métier. Il ne trouve que du contenu généraliste, peu adapté à ses besoins.
>
> Point commun : tous étaient motivés au départ. Le problème n’était pas l’engagement, mais l’absence de progression perçue.

**Apres :**

> Trois entretiens de 30 minutes avec des utilisateurs actifs d'apps concurrentes.
>
> Les memes points reviennent : difficulte a passer les acquis, exercices repetitifs, contenu trop generaliste, et manque de visibilite sur la progression.
>
> Le constat est simple : la motivation etait la, mais la progression ne se voyait pas assez.

**Coupe :**
- Detail complet par profil deja lisible dans les supports de recherche
- Redondances descriptives sur chaque cas individuel

---

## Section 3 - Architecture et parcours

**Image :** `flows.jpg`

> ✅ L'image montre deja les parcours. Le texte doit rester sur la structure globale et l'intention de navigation.

**Avant :**

> L'expérience est structurée autour de cinq zones : Accueil, Apprendre, Quiz, Quêtes et Profil. Nous avons conçu des parcours fluides pour le duel, les quiz thématiques et l'apprentissage guidé, en garantissant une navigation claire.

**Apres :**

> L'experience s'organise en cinq zones : Accueil, Apprendre, Quiz, Quetes et Profil.
>
> Les parcours duel, quiz thematique et apprentissage guide suivent la meme logique de navigation pour garder une prise en main rapide.

**Coupe :**
- "en garantissant" (wrapper)

---

## Section 4 - Conception UI

**Images :** `apprentissage.jpg`, `quiz.jpg`, `duels.jpg`

> ✅ Les ecrans montrent deja la variete des formats. Le texte doit garder la logique de coherence entre ecrans.

**Avant :**

> L’interface a été conçue pour gérer plusieurs formats (cours, quiz, duels, quêtes) sans complexifier l’expérience.
>
> Plutôt que multiplier les patterns, on s’est appuyé sur des briques communes : cartes de contenu, blocs de progression, modules de quiz et header partagé.
>
> Chaque écran suit la même logique : une action principale claire, des informations hiérarchisées, et des feedbacks visibles pour aider l’utilisateur à comprendre ce qu’il vient de faire.
>
> L’objectif était de rendre l’expérience prévisible, pour réduire la charge mentale et laisser plus de place à l’apprentissage.

**Apres :**

> L'interface gere plusieurs formats sans alourdir l'experience.
>
> On a utilise des briques communes (cartes, progression, modules de quiz, header) pour garder des reperes stables d'un ecran a l'autre.
>
> Chaque ecran met en avant une action principale, des infos hierarchisees et un feedback clair, pour reduire la charge mentale.

**Coupe :**
- "plutot que multiplier" (formulation defensive)
- Phrase finale redondante avec le paragraphe precedent

---

## Section 5 - Design system

**Image :** `designsystem.jpg`

> ✅ L'image porte deja la bibliotheque visuelle. Le texte doit garder le besoin de gouvernance et la production concrete.

**Avant :**

> Le projet couvre cinq sections (Accueil, Apprendre, Quiz, Quêtes, Profil) développées en parallèle par deux designers. Sans référentiel commun, les sections auraient divergé. On a construit un design system complet : tokens, fondations, composants documentés par usage, templates et documentation publiée sur Zeroheight, synchronisée depuis Figma.

**Apres :**

> Le projet avancait en parallele sur cinq sections et deux designers, avec un risque clair de divergence.
>
> On a donc construit un design system complet : tokens, fondations, composants documentes par usage, templates, et documentation Zeroheight synchronisee depuis Figma.

**Coupe :**
- Reformulation explicative "sans referentiel..." devenue implicite dans la phrase d'ouverture

---

## Section 6 - Tests utilisateurs

**Image :** `tests.jpg`

> ✅ L'image couvre les retours test. Le texte doit garder le niveau de severite, les frictions et les iterations.

**Avant :**

> Tests réalisés avec 3 participants sur deux parcours.
>
> Les scénarios ont été complétés sans blocage majeur. La navigation était globalement comprise et fluide.
>
> Plusieurs points d’amélioration sont ressortis :
> - confusion sur l’écran initial du quiz (réponses visibles trop tôt)
> - impossibilité d’inviter plusieurs amis
> - absence de titre sur certaines pages
> - difficulté à quitter puis reprendre un cours
>
> Les itérations ont porté sur ces éléments : clarification des entrées de quiz, amélioration des écrans de fin, et ajout des états manquants.

**Apres :**

> Tests menes avec 3 participants sur deux parcours. Les scenarios ont ete completes sans blocage majeur.
>
> Les frictions principales concernaient l'entree quiz, l'invitation d'amis, certains titres manquants, et la reprise de cours.
>
> Les iterations ont cible ces points : clarifier l'entree quiz, ameliorer les fins de parcours, et ajouter les etats manquants.

**Coupe :**
- Liste a puces detaillee remplacee par une phrase plus directe
