# Lira — Réécriture FR (refonte-study)

Règles appliquées : 1 section = 1 point, 2-3 phrases max, suppression miroir / archéologie / hedge / wrapper, format adapté au contenu.

---

## Section 1 — Contexte et enjeux

**Image :** `contexte.jpg` + `lira-demo.mp4`

> ⚠️ Problème image : `contexte.jpg` montre le **Carnet de vocabulaire** (liste de mots avec statuts Nouveau/En cours/Maîtrisé, phrases en contexte). C'est un écran produit, pas une illustration du positionnement vs concurrents. La vidéo compense probablement, mais l'image seule ne raconte pas "Lira vs Duolingo/Anki/LingQ". À surveiller sur mobile où la vidéo peut ne pas lancer.

**Avant :**

> Les apps d'apprentissage des langues ont chacune leur angle mort.
>
> Duolingo installe une habitude, mais le contenu reste artificiel et beaucoup d'utilisateurs stagnent autour du niveau intermédiaire. Anki est extrêmement puissant, mais la création des cartes demande souvent plus d'effort que leur révision. LingQ se rapproche d'une expérience de lecture réelle, mais l'interface peut freiner la prise en main.
>
> Lira part d'un besoin simple : lire du contenu réel, sauvegarder les mots directement dans leur contexte, puis les revoir avec un système de répétition efficace. Le tout sans configuration lourde, ni mécanique de gamification.
>
> Le produit est en ligne depuis mars 2026.

**Après :**

> Les apps d'apprentissage ont chacune leur angle mort. Duolingo crée une habitude sur du contenu artificiel. Anki est puissant, mais la création de cartes rebute. LingQ est proche du réel, l'interface moins.
>
> Lira répond à un besoin simple : lire du vrai contenu, sauvegarder les mots en contexte pour les revoir. En ligne depuis mars 2026.

**Coupé :**
- §1 standalone → fusionné dans la liste du §2
- "Le tout sans configuration lourde, ni mécanique de gamification" → wrapper
- Reformulation sèche de §3, fait factuel (date) gardé

---

## Section 2 — Recherche et positionnement

**Image :** `persona-01.jpg`, `persona-02.jpg`, `persona-03.jpg`

> ✅ Image OK : les 3 personas sont sur les visuels. Le §5 (description des profils) est donc un miroir direct → coupé à raison.

**Avant :**

> La recherche s'est faite en amont du lancement, principalement en desk research : Reddit (r/languagelearning, r/Anki, r/duolingo, r/busuu...), forums LingQ, avis App Store et commentaires YouTube.
>
> Ces sources ont un biais évident : elles reflètent souvent des frustrations. Elles restent utiles pour comprendre où les produits actuels échouent.
>
> Un point revient constamment : beaucoup d'apprenants atteignent un plateau autour du niveau intermédiaire. À ce stade, la lecture devient un levier naturel de progression. Le besoin n'est pas de motiver, mais de rendre cette transition plus fluide.
>
> Autre friction récurrente : la création manuelle de cartes Anki, souvent citée comme une raison d'abandon.
>
> À partir de là, j'ai défini trois profils : un utilisateur avancé qui cherche un outil rapide et sans friction, un expatrié qui veut lire du contenu local sans casser son rythme, et un utilisateur régulier d'apps comme Duolingo qui ne ressent plus de progression réelle.

**Après :**

> Desk research avant lancement : Reddit (r/languagelearning, r/Anki, r/duolingo, r/busuu...), forums LingQ, avis App Store, commentaires YouTube.
>
> Deux points reviennent : le plateau au niveau intermédiaire sans passage naturel vers la lecture, et la création manuelle de cartes Anki, souvent la raison d'arrêt.

**Coupé :**
- §2 hedge (biais des sources — autodéfense inutile)
- §3 condensé + fusionné avec §4
- §5 miroir (profils visibles sur les personas)
- "À ce stade, la lecture devient un levier naturel de progression" → wrapper

---

## Section 3 — Logique de design

**Image :** `flow.jpg`

> ✅ Image OK : le flow montre explicitement Reading → Tap word → Translation Window → [Audio / Traductions / Définitions] → Save / Close. La logique des 2 clics est lisible. Le positionnement du panneau (bas mobile / côté desktop) n'est pas dans le flow → mérite de rester dans le texte.

**Avant :**

> La lecture reste l'activité principale. Tout le reste doit s'y intégrer sans l'interrompre.
>
> Le panneau de traduction s'ouvre sans remplacer la page. Le texte reste visible. Un mot se consulte en un geste.
>
> La sauvegarde a demandé le plus d'ajustements. Un premier clic ouvre le panneau, un second enregistre le mot. Le retour visuel est immédiat : état chargé, puis confirmation et marquage dans le texte.
>
> Les premières versions utilisaient un overlay plein écran. Ce choix a été abandonné : il coupait la lecture et faisait perdre le repère dans le texte.
>
> La version finale s'ancre en bas sur mobile et sur le côté sur desktop, sans déplacer la colonne de lecture.

**Après :**

> La lecture reste l'activité principale. Tout le reste doit s'y intégrer sans l'interrompre.
>
> Le panneau s'ouvre sans remplacer la page. Un clic ouvre le panneau, un deuxième enregistre le mot avec sa phrase d'origine. En bas sur mobile, sur le côté sur desktop : la colonne de lecture ne bouge pas.

**Coupé :**
- §3 archéologie (overlay abandonné)
- §5 miroir (visible dans le flow et sur les screenshots)
- §2 condensé + fusionné dans le §2 réécrit

---

## Section 4 — Le reader

**Image :** `reader-large.jpg`, `reader-definitions.jpg`, `reader-mobile.jpg`

> ✅ Image OK : `reader-large.jpg` montre le mot "alemán" cliqué, panneau ouvert avec phonétique (/ale'man/), 2 onglets (Traduction / Définition BETA), traduction + phrase contexte, bouton "Sauvegarder la traduction", liens Wiktionary/Reverso. Icône audio visible. Le texte reste lisible derrière le panneau.
>
> Ce que l'image ne montre pas : que l'audio est un moteur **local** (PiperTTS, pas une API externe) — information non-évidente, à garder dans le texte.

**Avant :**

> Le reader est le cœur du produit. L'objectif est simple : lire sans être interrompu.
>
> Un clic sur un mot ouvre un panneau avec deux onglets : traduction et définition. L'utilisateur voit la phonétique et peut lancer une prononciation audio via un moteur local (PiperTTS).
>
> Tout se fait sans quitter la page. Un second clic permet de sauvegarder le mot. Une carte est alors générée automatiquement, en utilisant la phrase d'origine comme contexte de mémorisation.
>
> L'idée est de transformer un moment de lecture en opportunité d'apprentissage, sans changer de mode.

**Après :**

> Un clic ouvre le panneau : traduction, définition, phonétique, audio via PiperTTS (local). Le mot se sauvegarde en un clic de plus, avec la phrase d'origine comme contexte.

**Coupé :**
- §1 wrapper/echo du titre
- "Tout se fait sans quitter la page" → miroir (visible sur image)
- §4 wrapper

---

## Section 5 — Bibliothèque et import

**Image :** `biblio.jpg`

> ✅ Image OK : montre 3 états en un — bibliothèque Gutenberg (livres Cervantes), zone d'import (EPUB/PDF/TXT/HTML/URL), éditeur de nettoyage du texte importé. Les formats d'import sont lisibles directement.
>
> ⚠️ Note : l'image montre aussi **HTML** comme format d'import, absent du texte actuel.
>
> Ce que l'image ne montre pas : les langues disponibles dans Gutenberg → à garder dans le texte.
>
> Ce que l'image montre déjà : la progression par texte et les mots sauvegardés sont visibles sur `contexte.jpg` (le carnet) → §3 coupé.

**Avant :**

> L'import accepte une URL, un texte, un EPUB ou un PDF. L'utilisateur lit ce qu'il veut, sans bibliothèque imposée.
>
> Pour ceux qui cherchent un point de départ, Lira intègre Project Gutenberg : plusieurs milliers de livres du domaine public, directement dans l'app. Romans, nouvelles, essais en espagnol, allemand, anglais, italien et d'autres langues.
>
> Les textes importés et les livres Gutenberg s'organisent dans la même bibliothèque personnelle. Chaque texte affiche la progression de lecture et le nombre de mots sauvegardés.

**Après :**

> Import : URL, EPUB, PDF, HTML ou texte brut. Project Gutenberg est intégré directement, avec des livres du domaine public en espagnol, allemand, anglais et italien.

**Coupé :**
- "L'utilisateur lit ce qu'il veut, sans bibliothèque imposée" → wrapper
- §3 miroir (progression visible sur le carnet dans `contexte.jpg`)
- HTML ajouté (absent du texte original, visible sur l'image)

---

## Section 6 — Révision et mots croisés

**Image :** `crossword.jpg`, `revision.jpg`, `stats.jpg`

> ✅ Image OK : `crossword.jpg` montre la grille générée à partir du vocabulaire personnel (destino, libro, parque, verdad...) avec les traductions françaises comme indices. Le principe "généré depuis le vocab personnel" est évident sur l'image.
>
> Ce que l'image ne montre pas : FSRS, la phrase d'origine disponible en cas de doute, le mini-quiz post-lecture → à garder dans le texte.

**Avant :**

> La révision repose sur FSRS avec un rappel contextuel. L'utilisateur doit retrouver un mot ou sa traduction, avec la possibilité de revoir la phrase d'origine en cas de doute.
>
> La mémorisation ne passe pas uniquement par le mot isolé, mais aussi par son contexte d'utilisation.
>
> Après quelques minutes de lecture et quelques mots sauvegardés, un mini-quiz optionnel apparaît. Court, rapide, lié à la session en cours.
>
> Les mots croisés sont générés à partir du vocabulaire personnel. Ils offrent une alternative aux flashcards pour varier les sessions de révision.

**Après :**

> Révision FSRS avec rappel contextuel. L'utilisateur retrouve un mot ou sa traduction, avec la phrase d'origine disponible en cas de doute. Après la lecture, un mini-quiz optionnel apparaît sur les mots de la session.
>
> Les mots croisés sont générés à partir du vocabulaire personnel.

**Coupé :**
- §2 miroir ("La mémorisation ne passe pas uniquement par le mot isolé" — echo du rappel contextuel)
- "Ils offrent une alternative aux flashcards pour varier les sessions de révision" → wrapper

---

## Section 7 — Design

**Image :** `landing.jpg`, `dark.jpg`, `profil.jpg`

> ✅ Image OK : `dark.jpg` montre le dark mode reader avec le mot "popular" cliqué — fond très sombre, texte clair, panneau identique au mode clair, vert du bouton conservé. La police Literata est visible dans le corps du texte.
>
> Ce que l'image ne montre pas : les noms des polices (Literata/Satoshi) et le "pourquoi" du fond teinté → à garder dans le texte.
>
> Ce que l'image montre déjà : le dark mode fonctionne, la palette (vert/brun/fond teinté) → §4 miroir, coupé.

**Avant :**

> La lecture a guidé les choix visuels.
>
> La police Literata est utilisée pour les textes longs, afin d'améliorer le confort de lecture. L'interface repose sur Satoshi pour garder une bonne lisibilité sur les éléments fonctionnels.
>
> Le fond est légèrement teinté pour éviter la fatigue liée au blanc pur. Les couleurs restent limitées : un vert pour les actions et un brun foncé pour le texte.
>
> Le mode sombre reprend les mêmes principes avec des contrastes ajustés pour conserver le confort sur de longues sessions.

**Après :**

> Literata pour les textes longs, Satoshi pour l'interface. Fond légèrement teinté pour éviter la fatigue du blanc pur. Palette limitée : vert pour les actions, brun foncé pour le texte.

**Coupé :**
- §1 wrapper ("La lecture a guidé les choix visuels")
- §4 miroir (dark mode visible sur l'image)
- Reformulation plus sèche des §2+§3 fusionnés
