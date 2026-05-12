# Septième Séance — Réécriture FR (refonte-study)

Règles appliquées : 1 section = 1 point, 2-3 phrases max, suppression miroir / archéologie / hedge / wrapper, format adapté au contenu.

---

## Section 1 — Contexte et enjeu

**Image :** `contexte.jpg`

> ✅ Image probablement contextuelle (problème + usage). Le texte peut garder le cadrage produit, la contrainte de vitesse d'accès et la fermeture du service liée à l'API.

**Avant :**

> Les services cinéma existants proposent beaucoup d'informations, mais rarement sous une forme exploitable immédiatement. L'utilisateur doit naviguer entre plusieurs écrans avant de voir les séances autour de lui, parfois même sans prise en compte fiable de sa position.
>
> Le problème n'était pas un manque de contenu, mais un manque de hiérarchie et de vitesse d'accès à l'information. L'objectif produit était donc clair : permettre à un utilisateur de comprendre ce qui se joue autour de lui en quelques secondes et choisir une séance sans friction.
>
> Le service a été conçu et lancé comme un produit complet, de la recherche à la mise en ligne. Il s'est arrêté suite à une restriction d'accès à l'API de données, mais reste un cas représentatif d'un cycle produit complet, avec contraintes techniques réelles.

**Après :**

> Les services cinéma donnent beaucoup d'informations, mais rarement dans un format exploitable immédiatement. L'objectif était de réduire le temps entre l'entrée et le choix d'une séance.
>
> Le produit a été conçu et lancé de bout en bout. Il s'est arrêté après une restriction d'accès à l'API, mais reste un cas concret de cycle produit complet sous contrainte technique.

**Coupé :**
- Détails redondants sur la navigation multi-écrans (si déjà visibles dans les écrans suivants)
- Formulations allongées autour de la "friction"

---

## Section 2 — Géolocalisation ou recherche manuelle

**Image :** `geoloc.jpg`

> ✅ L'image couvre le double point d'entrée. Le texte doit surtout garder la logique produit (accès rapide à une première réponse utile).

**Avant :**

> Deux points d'entrée ont été conçus : géolocalisation ou recherche manuelle. L'enjeu n'était pas d'ajouter des options, mais de réduire le temps d'accès à une première réponse pertinente.
>
> La géolocalisation permet d'afficher immédiatement les cinémas proches avec un rayon ajustable. La recherche manuelle couvre les cas où l'utilisateur pense en termes de lieu précis, de film ou de salle.
>
> Les deux modes convergent vers le même objectif : afficher des résultats exploitables en un minimum d'interactions.

**Après :**

> Deux entrées : géolocalisation ou recherche manuelle. Le but était d'obtenir une première réponse utile en quelques interactions.
>
> La géolocalisation affiche les cinémas proches avec rayon ajustable. La recherche manuelle couvre les cas orientés lieu, film ou salle.

**Coupé :**
- "L'enjeu n'était pas d'ajouter des options" (wrapper)
- Phrase de conclusion redondante avec les deux phrases principales

---

## Section 3 — Filtres de recherche

**Images :** `filter-films.jpg`, `filter-perimetre.jpg`, `filter-langue.jpg`

> ✅ Les images montrent déjà les types de filtres. Le texte doit garder la logique d'usage, pas répéter chaque contrôle interface.

**Avant :**

> Pour accompagner la recherche, des filtres ont été ajoutés afin de permettre un tri plus précis selon les situations.
>
> Certains filtres affinent les résultats : genre, année, durée et option films récents vs films cultes encore projetés. Les utilisateurs peuvent aussi filtrer par abonnements acceptés (UGC, Pathé...).
>
> L'utilisateur peut définir la distance autour du point géolocalisé ou autour de la ville/cinéma choisi manuellement. Il peut aussi choisir la date souhaitée pour voir les projections correspondantes.
>
> La gestion des langues et sous-titres fait aussi partie des options. L'idée est de laisser chacun adapter l'affichage selon ses contraintes.

**Après :**

> Les filtres servent à transformer une liste large en sélection exploitable rapidement.
>
> Ils couvrent le contenu (genre, année, durée, récents/cultes), le contexte (distance, date, abonnements) et les contraintes de séance (langues, sous-titres).

**Coupé :**
- Répétitions de formulation "l'utilisateur peut"
- Détail interface trop exhaustif déjà visible en capture

---

## Section 4 — Liste des projections autour

**Image :** `projections.jpg`

> ✅ L'image porte la structure de liste. Le texte doit rester centré sur la promesse: lisibilité + décision rapide.

**Avant :**

> Une fois la zone définie, les séances apparaissent immédiatement. Les cinémas sont triés par proximité, avec un accès direct aux séances du jour.
>
> La présentation est volontairement compacte et mobile-first : chaque élément doit être scannable en quelques secondes. L'objectif n'est pas d'exposer toute la donnée, mais de permettre une décision rapide.
>
> Chaque écran est pensé comme une réduction de l'incertitude : où, quand, et quoi regarder.

**Après :**

> Dès que la zone est définie, les séances s'affichent et les cinémas sont triés par proximité.
>
> La liste est compacte et mobile-first pour permettre une lecture rapide et une décision immédiate.
>
> La compacité sert un objectif simple: moins de scan, donc une décision plus rapide.

**Coupé :**
- "pas d'exposer toute la donnée" (wrapper explicatif)
- "réduction de l'incertitude" (bonne idée, mais formulation conceptuelle)

---

## Section 5 — Décisions produit et arbitrages

**Images :** `filter-empty.jpg`, `filter-seances.jpg`, `filter-results.jpg`

> ✅ Les états d'interface illustrent les arbitrages. Le texte garde les choix structurants (focus intention, lisibilité, suppressions assumées).

**Avant :**

> Le premier écran est une barre de recherche, sans distraction. Les utilisateurs arrivent avec une intention claire : savoir ce qui passe maintenant ou ce soir.
>
> Les résultats sont organisés pour maximiser la lisibilité : affiches en grille, informations essentielles visibles immédiatement, filtres séparés entre contenu et localisation.
>
> Plusieurs arbitrages ont structuré le produit :
>
> - L'intégration Letterboxd a été abandonnée. Pertinente dans certains contextes (catalogue large), elle n'améliorait pas la décision dans les cas majoritaires.
> - L'affichage des prix a été écarté. Bien que techniquement possible, la donnée était trop incomplète à grande échelle (2 300 cinémas, multiples séances). Une information partielle aurait dégradé la confiance.
>
> Ces choix illustrent une logique produit simple : privilégier la fiabilité et la rapidité de décision plutôt que la richesse fonctionnelle.
>
> Stack : React, Tailwind, Figma, Heroicons.

**Après :**

> Le produit est centré sur une intention immédiate : trouver quoi voir maintenant ou ce soir.
>
> Deux arbitrages ont guidé la version : abandon de l'intégration Letterboxd et retrait des prix, car la donnée restait trop incomplète à l'échelle et nuisait à la confiance.

**Coupé :**
- Détail de layout déjà visible en captures
- "Ces choix illustrent..." (wrapper)
- Stack technique (à garder ailleurs si nécessaire)

---

## Section 6 — Futures améliorations

**Images :** `notes.jpg`, `alertes.jpg`, `letterboxd.jpg`

> ✅ Les images couvrent les pistes d'évolution. Le texte garde l'insight test utilisateur et les priorités produit.

**Avant :**

> Les tests ont montré un comportement inattendu : plusieurs utilisateurs recherchaient directement un cinéma, plutôt que d'utiliser la géolocalisation. Leur besoin était différent : voir un programme complet sur plusieurs jours.
>
> Cela a conduit à deux évolutions prioritaires : recherche par cinéma avec autocomplétion, et pages cinéma multi-jours.
>
> Les prochaines itérations visaient à enrichir l'expérience sans compromettre la simplicité : mise en avant de la prochaine séance, alertes personnalisées, métadonnées utiles (formats, avant-premières), et amélioration des filtres (compteurs, reset, feedback temps réel).
>
> Chaque amélioration est évaluée selon un critère : réduit-elle le temps nécessaire pour prendre une décision ?

**Après :**

> Les tests ont révélé un besoin complémentaire : rechercher directement un cinéma pour voir son programme sur plusieurs jours.
>
> Priorités retenues : recherche cinéma avec autocomplétion et pages cinéma multi-jours, puis enrichissements ciblés (prochaine séance, alertes, métadonnées utiles, filtres améliorés) sans alourdir le parcours.

**Coupé :**
- "comportement inattendu" (dramatise inutilement)
- Question finale rhétorique (le critère reste implicite dans le texte)
