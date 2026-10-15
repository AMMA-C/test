# Handoff : site Just you (bien-être, sport, nutrition)

## Vue d'ensemble
Just you est un site responsive (mobile first) en français, au **vouvoiement**. Il aide chaque personne à choisir un objectif parmi trois, puis lui propose un parcours adapté : plan sport, plan nutrition et suivi.
- **Public** : grand public, en priorité des femmes de 25 à 45 ans, avec un ton inclusif.
- **Modèle** : freemium. Le plan de la semaine est gratuit par email ; l'abonnement **Just you+** donne accès aux programmes de 8 semaines, aux vidéos guidées et au suivi détaillé.
- **Ton** : bienveillant, sans culpabilisation, sans promesse chiffrée, sans régime extrême (jamais moins de 1 200 kcal par jour).

## À propos des fichiers
Les fichiers de ce dossier sont des **références de design en HTML**. Ce sont des prototypes qui montrent l'apparence et le comportement attendus, pas du code de production à copier tel quel. La tâche consiste à **recréer ces écrans dans l'environnement du dépôt cible** (React, Vue, Next, Astro…) avec ses conventions et ses bibliothèques. S'il n'existe pas encore d'environnement, nous recommandons Next.js ou Astro avec des composants React, du CSS Modules ou Tailwind configuré sur les tokens ci-dessous, et des pages statiques pour la vitesse de chargement.

Les fichiers `.dc.html` s'ouvrent directement dans un navigateur. Ils dépendent de `support.js` (le runtime du prototype, à ne pas reprendre), de `organic.css` (les tokens), de `icons.js` (Lucide) et de `image-slot.js` (les emplacements photo).

## Fidélité
**Haute fidélité.** Les couleurs, la typographie, les rayons, les espacements, les textes et les interactions sont définitifs. Seules les photos sont des emplacements annotés, à remplacer. Les témoignages sont fictifs et doivent être remplacés par de vrais retours.

## Mise en page globale
- Conteneur : `max-width: 1220px`, centré, marges latérales `clamp(16px, 4vw, 40px)`.
- Point de rupture principal : **1000px**. En dessous, la navigation passe en menu burger.
- Les grilles utilisent `repeat(auto-fit, minmax(min(100%, Xpx), 1fr))` : 300px pour les cartes d'objectif, 260 à 280px pour les cartes de contenu.
- Rythme vertical des sections : 48 à 56px de padding.
- Typographie fluide : H1 `clamp(40px, 6.4vw, 76px)` sur l'accueil et `clamp(36px, 5.4vw, 64px)` sur les pages ; H2 `clamp(28px, 4vw, 46px)`.

### En-tête (sticky)
- Hauteur 72px. Fond crème à 92 % d'opacité avec `backdrop-filter: blur(14px)`.
- Logo : pastille terracotta de 30px avec un point crème central, puis « Just you » en Caprasimo 24px.
- Navigation desktop : Parcours, Recettes, Séances, Conseils, À propos. Ce sont des pilules en Figtree 600 15px ; la page active reçoit le fond `--surface2` et `aria-current="page"`.
- À droite :
  - boutons icônes de 44×44px : recherche, bascule clair/sombre ;
  - bouton secondaire « Mon plan », en pilule bordée ;
  - bouton principal « Faire le quiz ».
- Mobile : recherche, thème et burger. Le menu plein écran affiche les liens en Caprasimo 24px, puis les boutons « Faire le quiz (1 min) » et « Mon plan ».

### Pied de page
- Fond `--surface2`, coins supérieurs droits. Quatre colonnes :
  - marque, slogan et bouton « Recevoir mon plan » ;
  - Parcours ;
  - Contenus ;
  - Just you.
- Barre légale : © 2026, mentions légales, politique de confidentialité, CGU Just you+.
- Lien « Gérer les cookies », qui rouvre le bandeau en mode personnalisation.

## Écrans

### 1. Accueil
1. **Hero** en deux colonnes (une seule sur mobile).
   - Badge sauge « Sport · Nutrition · Bien-être ».
   - H1 « Votre corps, votre rythme, votre plan. »
   - Sous-titre « Des séances courtes, une cuisine simple et un suivi bienveillant pour vous remettre en mouvement et mieux manger, même quand l'agenda déborde. »
   - CTA « Choisir mon objectif » (principal) et « J'hésite : faire le quiz (1 min) » (secondaire).
   - Trois points de réassurance avec icônes : séances de 20 à 45 min, maison ou salle, gratuit pour commencer.
   - À droite : photo en arche (`border-radius: 200px 200px 32px 32px`, ratio 4/4,4), un cercle sauge clair en décor, et une carte flottante « Séance du jour faite · Mobilité du matin · 20 min ».
2. **Les 3 cartes d'objectif**. H2 « Par quoi voulez-vous commencer ? ». Chaque carte :
   - est un bouton entier sur le fond clair de son accent, avec un rayon de 32px ;
   - contient une photo 16/11 (rayon 22px), une icône ronde de 46px, le nom en Caprasimo 23 à 27px, la description, les tags et « Découvrir le parcours → » ;
   - au survol : `translateY(-4px)` et une ombre forte, en 0,25s.
   - Sous les cartes, une bande en pointillés : « Vous hésitez ? Cinq questions… » avec le bouton « Faire le quiz ».
3. **Comment ça marche** : trois colonnes, chacune avec un grand chiffre de 64px en Caprasimo (terracotta, sauge, ocre) : « Choisissez votre objectif », « Suivez votre plan », « Ajustez chaque semaine ».
4. **Bandeau calculateur** sur fond sauge clair, avec le bouton sauge foncé « Ouvrir le calculateur ».
5. **Témoignages** : trois cartes `figure`/`blockquote` avec avatar rond. Mention « Témoignages fictifs, à remplacer ».
6. **Conseils de la semaine** : trois cartes d'articles.
7. **CTA newsletter** sur fond `--color-accent-2-800`, rayon 40px : champ email et bouton terracotta clair « Recevoir mon plan ». Le bouton ouvre la modale d'inscription, où se donne le consentement.

### 2. Page objectif (même modèle pour les 3)
- **Onglets** des trois parcours en haut de page (`aria-pressed`).
- **Hero** sur le fond clair de l'accent, rayon 40px : surtitre « Parcours 01 », H1, chapô, CTA « Recevoir ce plan par email » et « Voir Mon plan ». Photo avec le coin supérieur droit à 160px.
- **Mention santé** (pages Perdre du poids, nutrition, recettes et calculateur) : « Ces contenus sont informatifs et ne remplacent pas l'avis d'un professionnel de santé. En cas de grossesse, de pathologie ou de doute, demandez conseil à votre médecin. »
- **À qui s'adresse ce parcours** : quatre puces à coches, et à côté quatre cartes « piliers » (icône, titre, texte).
- **Plan sport** :
  - sélecteur de durée 20, 30 ou 45 min, et sélecteur de lieu « À la maison » ou « En salle » ;
  - une grille de 7 jours ; chaque carte affiche le jour, une icône de type, le titre, le détail (qui change selon le lieu) et la durée ;
  - le format dépend de la durée : 20 min = 2 tours, 30 min = 3 tours, 45 min = 4 tours + retour au calme ;
  - les séances de mobilité sont plafonnées à 20 min ;
  - les jours de repos ont une bordure en pointillés.
- **Plan nutrition** :
  - principes clés et note ;
  - exemple de journée (4 repas) ;
  - 4 idées de repas, liées aux fiches recettes ;
  - liste de courses par rayon, à cocher (texte barré une fois coché) ;
  - batch cooking du week-end en étapes numérotées avec leur durée.
- **Suivi** :
  - objectifs 1 et 2 : 3 KPI, puis un histogramme sur 8 semaines (barres à l'accent moyen, la dernière à l'accent foncé) ;
  - objectif 3 : humeur sous forme de visages et énergie sous forme de jauges verticales sur 7 jours, sans poids ;
  - un conseil de lecture des données.

Accents par parcours (foncé = texte et boutons, moyen = graphiques, clair = fonds) :

| Parcours | Foncé | Moyen | Clair | Sombre : texte / fond |
|---|---|---|---|---|
| Perdre du poids (corail) | #9A3B2C | #E07A62 | #FDEEE9 | #F8B4A3 / #3A2621 |
| Construire du muscle (ocre) | #765510 | #C99A3A | #FBF1DC | #E9C77C / #352C1B |
| Bouger et se sentir bien (sauge) | #56633F | #8FA073 | #F0FAE1 | #CCDBB2 / #262C1F |

Tous les textes des trois pages (titres, chapôs, publics, piliers, semaines maison et salle, principes, journées, courses, batch cooking, KPI) se trouvent dans l'objet statique `G` de `Site Just you.dc.html`. **Ils sont définitifs : reprenez-les mot pour mot.**

### 3. Recettes
- H1 « Recettes simples et gourmandes ».
- Panneau de filtres en pilules :
  - Objectif ;
  - Temps (≤ 15, ≤ 30 min) ;
  - Protéines (≥ 20 g, ≥ 30 g) ;
  - Régime, en sélection multiple (végétarien, vegan, sans gluten, sans lactose) ;
  - interrupteur **Cuisine du monde**, qui ne garde que les plats méditerranéens et tunisiens.
- Compteur `aria-live`, état vide avec « Réinitialiser ».
- Cartes : photo 4/3, badge d'origine, temps, protéines, régimes.
- **Fiche recette** :
  - photo carrée avec le coin inférieur droit à 200px ;
  - tags, H1, description ;
  - 3 tuiles : temps, protéines par portion, kcal estimées ;
  - « Idéal pour » ;
  - ingrédients à cocher, avec sélecteur de portions de 1 à 8 qui recalcule les quantités (base 2 portions, arrondi au 0,5 ou à 5 g) ;
  - étapes numérotées et astuce batch cooking ;
  - mention « valeurs estimées ».
- Les 12 recettes sont dans l'objet `R`. Les plats tunisiens : chakchouka, méchouia, couscous de poisson, lablabi, brick au four, ojja.

### 4. Séances
- Filtres : durée, niveau, matériel (sans matériel, élastique, haltères, salle), zone (full body, haut, bas, abdos et gainage, mobilité).
- Cartes : visuel 16/10, badge de durée, niveau (couleur du parcours), zone, matériel, nombre d'exercices.
- **Fiche séance** :
  - vidéo 16/10 avec bouton lecture, mention « sous-titrée et transcription » ;
  - H1, description ;
  - 4 tuiles : durée, niveau, matériel, zone ;
  - bouton « Ajouter à Mon plan », qui passe à l'état « Ajoutée » ;
  - échauffement de 3 min ;
  - liste des exercices : illustration de 96px, numéro, nom, consigne, « 3 séries × 12 répétitions », repos, variante « Plus facile », case « Fait » ;
  - barre de progression ;
  - message de fin « Séance terminée, bravo. »
- Les 10 séances sont dans l'objet `W`.

### 5. Quiz (5 questions)
- Barre de progression (`role="progressbar"`), « Question n sur 5 ».
- Question en `legend` Caprasimo 28 à 42px. Les options sont des boutons radio en pilules de 64px de haut ; une fois choisies, elles ont le fond terracotta clair et une bordure terracotta.
- Le bouton « Question suivante » est désactivé tant que rien n'est choisi. À la cinquième question, il devient « Voir mon parcours ». Un bouton Retour est disponible.
- **Score** : chaque réponse ajoute des points pondérés aux trois objectifs (voir le tableau `Q`). Le meilleur score donne la recommandation, le deuxième est proposé comme alternative.
- **Résultat** :
  - carte sur l'accent de l'objectif : photo, icône, nom, explication ;
  - CTA « Découvrir mon parcours » et « Recevoir mon plan par email » ;
  - lien vers le deuxième parcours ;
  - « Recommencer le quiz ».

### 6. Calculateur
- Formule de **Mifflin-St Jeor** :
  - BMR = 10 × poids + 6,25 × taille − 5 × âge, puis −161 (profil femme) ou +5 (profil homme) ;
  - BMR × activité : 1,2 / 1,375 / 1,55 / 1,725.
- Ajustement selon l'objectif :
  - perte : × 0,85 ;
  - muscle : × 1,08 ;
  - bouger : × 1.
- **Plancher : 1 200 kcal.** Quand il s'applique, une alerte s'affiche. Le résultat est arrondi à la dizaine.
- Protéines en g par kg : perte 1,4 à 1,8, muscle 1,6 à 2,0, bouger 1,0 à 1,2. On affiche aussi la valeur par repas, sur 4 prises.
- Message obligatoire : « Il s'agit d'une estimation… », suivi de la mention santé.

### 7. Mon plan (maquette)
- Choix du parcours.
- Liste des séances de la semaine (hors repos) à cocher, avec une progression « n séances sur N ».
- Humeur sur 5 niveaux (boutons à icônes) et énergie sur 5 segments, avec un message bienveillant si l'humeur est basse (≤ 2).
- Interrupteur « Semaine chargée » : toutes les séances passent à 20 min.
- Encart Just you+.

### 8. Conseils, À propos, Contact
- **Conseils** : filtres par catégorie (Sommeil, Motivation, Stress, Erreurs fréquentes, Nutrition). Six articles dans `A`.
- **À propos** : histoire, 4 valeurs, encadré « Ce que nous ne ferons jamais ».
- **Contact** :
  - formulaire prénom, email, message, avec validation (les 3 champs requis, email valide) et un message de succès ;
  - newsletter avec case de consentement **non pré-cochée** et obligatoire, mention de la base légale ; succès « Presque fini ! » en double opt-in.

### Composants transverses
- **Modale d'inscription en 2 étapes** :
  - étape 1 : choix du parcours, email, consentement obligatoire, erreurs inline (`role="alert"`) ;
  - étape 2 : « Plus qu'une étape », confirmation par email (double opt-in), lien vers Mon plan.
- **Recherche** : modale avec champ, suggestions et résultats groupés (Parcours, Recette, Séance, Conseil). La recherche est insensible aux accents.
- **Bandeau cookies RGPD** :
  - « Tout refuser » et « Tout accepter » ont **le même poids visuel** ;
  - « Personnaliser » propose les catégories nécessaires (verrouillées), mesure d'audience et personnalisation ;
  - le choix reste modifiable depuis le pied de page ;
  - en production, rien n'est déposé avant le consentement.
- **Mode sombre** : bouton dans l'en-tête. À persister (localStorage) et à initialiser avec `prefers-color-scheme`.

## Interactions et animations
- Survol des cartes : `translateY(-3 à -4px)` et passage à l'ombre forte, en 0,2 à 0,25s.
- Apparition au scroll : les sections `[data-reveal]` passent de `opacity: 0` et `translateY(18px)` à leur état normal en 0,6s ease, déclenchées par un IntersectionObserver avec `rootMargin: -8%`.
- Barres de progression : `width` en 0,3 à 0,35s.
- Tout est désactivé sous `prefers-reduced-motion`.
- Changement de page : retour en haut.

## État (prototype)
- `page`, `goal`, `dark`, `duration` ('20' | '30' | '45'), `lieu` ('maison' | 'salle').
- Filtres : `rf` (recettes) et `wf` (séances), plus le booléen `monde`.
- `recipeId`, `servings`, `ing` (cochés) ; `workoutId`, `exDone`, `added`.
- Quiz : `qi` (index) et `qa` (réponses).
- `calc` : sexe, âge, taille, poids, activité, objectif.
- Mon plan : `planDone`, `mood`, `energy`, `planLight`.
- Inscription : `signup` (étape, email, consentement, erreur) ; cookies : `cookie` (affiché, audience, personnalisation).

En production, il faudra :
- persister Mon plan, le thème, le consentement et les réponses au quiz ;
- un back-end email avec double opt-in (Brevo, Mailchimp…) ;
- un CMS pour les recettes, séances et articles, avec les champs définis par les objets `R`, `W` et `A` ;
- une gestion d'abonnement pour Just you+.

## Design tokens (système Organic, voir `organic.css`)

| Rôle | Clair | Sombre |
|---|---|---|
| Fond | #F5EAD8 | #1D1A17 |
| Carte (`--surface`) | #F9F4ED | #27231F |
| Surface sable (`--surface2`) | #EBDDC5 | #2F2A25 |
| Texte | #201E1D | #F3EBDF |
| Texte secondaire | #645C50 | #C0B6A5 |
| Bordure | rgba(32,30,29,.16) | rgba(243,235,223,.16) |
| Action principale | #8C491A, survol #643312, texte #F9F4ED | #F6A06B, survol #FFC6A5, texte #201E1D |
| Sauge (marque) | #56633F / #8FA073 / #F0FAE1 | #CCDBB2 / #262C1F |
| Bloc sombre (CTA newsletter, résultat calculateur) | #3D472B | — |

Les rampes complètes 100 à 900 (neutre, accent, accent-2) sont dans `organic.css`.

**Typographie**
- Titres : **Caprasimo** 400, interlignage 1,02 à 1,15, approche −0,02em pour les grands titres.
- Texte : **Figtree** 400, 600 et 700 ; 16 à 17px pour le courant, 18 à 20px pour les chapôs, 13 à 14px au minimum pour les mentions.
- Surtitres : 14px, 700, capitales, approche 0,06em.

**Rayons**
- Pilules (999px) pour les boutons, champs, filtres et tags.
- Cartes de contenu : 24 à 28px. Cartes d'objectif et panneaux : 32px. Grands blocs : 36 à 40px. Vignettes : 16 à 22px.
- Formes photo : arche, cercle, ou un coin asymétrique à 160–200px.

**Ombres**
- Douce : `0 1px 2px rgba(46,43,37,.14), 0 6px 20px rgba(46,43,37,.07)`.
- Forte : `0 12px 32px rgba(46,43,37,.22)`.
- En mode sombre : liseré `0 0 0 1px rgba(243,235,223,.08)` et ombre noire.

**Tailles minimales**
- Cibles tactiles : 44px.
- Boutons principaux : 52 à 54px de haut.
- Filtres : 40px.

**Focus** : `outline: 2px solid #C67139; outline-offset: 2px`.

**Photos** : filtre « washed » `saturate(.6) contrast(.85) brightness(1.1)`.

## Accessibilité (WCAG AA)
- Contraste du texte ≥ 4,5:1. Les accents moyens (#E07A62, #C99A3A, #8FA073) servent **uniquement** au décor et aux graphiques.
- Lien d'évitement vers `#contenu`. Repères `header`, `nav`, `main` et `footer`.
- Les filtres et sélecteurs utilisent des boutons avec `aria-pressed`. Les options du quiz ont `role="radio"` et `aria-checked`.
- Les compteurs et résultats sont en `aria-live="polite"`, les erreurs en `role="alert"`.
- Les modales ont `role="dialog"` et `aria-modal`. À ajouter en production : piège de focus, fermeture par Échap, retour du focus au déclencheur.
- Toutes les icônes sont `aria-hidden`. Les boutons icônes ont un `aria-label`.
- Le texte de chaque emplacement photo décrit l'image attendue ; il sert de base au texte alternatif.

## Contenus et règles éditoriales
- Vouvoiement partout.
- Aucun résultat chiffré promis, aucun avant/après, aucun corps retouché.
- Calories : jamais moins de 1 200 kcal par jour.
- Les données de suivi affichées sont des exemples, signalées « Données d'exemple ».
- Les témoignages sont fictifs et signalés comme tels.
- Propositions de marque : **Just you** (retenue), « Votre corps, votre rythme, votre plan. » ; **Élan**, « Un petit pas chaque jour, à votre façon. » ; **Sève**, « Bouger, manger, respirer. Simplement. »

## Ressources
- **Icônes** : Lucide (https://lucide.dev), trait 2,75. Noms utilisés : search, moon, sun, menu, x, footprints, dumbbell, flower-2, heart-pulse, person-standing, bike, wind, timer, egg, utensils, calendar-check, calendar-plus, calculator, sprout, smile, meh, frown, laugh, info, lightbulb, cookie, mail-check, check, arrow-right, arrow-left, arrow-down, play, gauge, package, flame, party-popper, rotate-ccw, scale, trending-up, moon, sun, move, brain, repeat, heart-handshake, stairs, book-open-check, users, shield-check, circle-help, house, heart, minus, plus.
- **Polices** : Caprasimo et Figtree (Google Fonts).
- **Photos** : aucune n'est fournie. Chaque emplacement porte la description de la photo attendue : personnes réelles et diverses en âge, morphologie et origine, dans des lieux du quotidien, en lumière naturelle.

## Fichiers
- `Site Just you.dc.html` : le prototype complet. Template et logique, avec toutes les données (objets `G`, `R`, `W`, `A`, `Q`) et les textes définitifs.
- `Guide de style Just you.dc.html` : marque, arborescence, guide de style et maquettes desktop et mobile (instances du prototype).
- `organic.css` : les tokens du système Organic.
- `icons.js` : le rendu des icônes Lucide (prototype uniquement).
- `image-slot.js` : les emplacements photo (prototype uniquement).
- `support.js` : le runtime du prototype, **à ne pas porter**.
