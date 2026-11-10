# App Store PracTice — site vitrine

Page vitrine des services pédagogiques augmentés par l'IA du service **PracTice**
(Institut Mines-Télécom Business School). Catalogue des outils en ligne, en accès
libre, avec démos vidéo.

## Contenu

| Fichier | Rôle |
|---|---|
| `index.html` | Page unique, autonome (HTML + CSS + JS inline), bilingue FR/EN |
| `Logo IMT-BS RF RVB.png` | Logo officiel IMT-BS (version République Française) |
| `imageillustation.png` | Illustration de la section « À propos » |
| `learnybot.html` | Page LearnyBot : démo en direct (LearnyBot du service PracTice) + bouton « Écrire à PracTice » |
| `learnybot-mascotte.svg` | Mascotte LearnyBot (carte du catalogue et page dédiée) |
| `sg_entreprise_mystere.webp`, `sg_bingo_sujets.webp` | Vignettes 960×600 des cartes Serious games (`sg_dernier_badge.webp` n'est plus affichée depuis le 10/11/2026) |
| `suggestions-linkedin-learning.html` | Page Suggestions LinkedIn Learning : formulaire (nom du cours, précisions, langues, adresse de l'école) qui appelle le workflow n8n « LinkedIn Learning · Demande de suggestions ». Fonctionnement et identifiants : `_Projets/AnnuaireLinkedLearning/Workflow_Suggestions/README.md` |

## Déploiement

Site 100 % statique, aucune dépendance de build.

- **GitHub Pages** : Settings → Pages → branche `main`, dossier `/ (root)`.
  URL : `https://julienmorice.github.io/appstorepractice/` (dépôt `julienmorice/appstorepractice` ; l'ancienne adresse `practice-imtbs.github.io/appstorepractice/` ne répond plus, constaté le 10/10/2026)
- **Hébergement institutionnel** : le dossier se dépose tel quel sur n'importe
  quel serveur statique. Site public : https://practice-imtbs.eu

## Déploiement sur practice-imtbs.eu (Hostinger)

```
scp -P 65002 -i ~/.ssh/id_ed25519_hostinger -o IdentitiesOnly=yes index.html learnybot.html learnybot-mascotte.svg suggestions-linkedin-learning.html sg_*.webp u641251867@72.60.93.197:~/domains/practice-imtbs.eu/public_html/
```
(détails de connexion : `../AppStorePractice_site/CLAUDE.md`)

## Quand on ajoute un outil au catalogue

Trois endroits de `index.html` sont à tenir à jour ensemble :

1. la carte : une rangée `<div class="tool-row">` (carte + vidéo) ajoutée **à la suite** des autres dans `<div class="tools-grid">`, jamais à l'intérieur d'une rangée existante ;
2. le compteur de la section (« 6 outils · Accès libre ou sur demande ») ;
3. l'encadré « Écosystème PracTice » en haut de page : le chiffre « Outils disponibles » et une ligne par outil.

Sans vidéo de démo, la colonne de droite reçoit un `tool-video-placeholder` (« Démo vidéo à venir »). Depuis le 10/11/2026, tous les outils ont leur vidéo ; celle de Suggestions LinkedIn Learning (trailer v2, voix de Julien, en français seulement) est https://mediaserver.ip-paris.fr/permalink/v126d68470acf2yjwqw8/, sources dans `_Projets/AnnuaireLinkedLearning/Trailer_Suggestions_v2/`.

## Quand on ajoute un serious game

Trois endroits de `index.html` : la carte, le compteur « N jeux · Accès libre » de la section, et l'encadré « Écosystème PracTice » (chiffre « Serious games » et ligne « Serious games · … »).

Depuis le 10/11/2026, la section commence par un jeu **à la une** (`<div class="game-feature">` : vidéo Médiaserveur à gauche, présentation et lien à droite, empilés sous 1100 px), suivi de la grille `<div class="games-grid">` des autres jeux en cartes `<a class="game-card">` (vignette `sg_<nom>.webp` en 960×600), sur 2 colonnes, 1 sous 900 px. Pour changer de jeu à la une, déplacer l'ancien dans la grille sous forme de carte.

Jeux au 10/11/2026 : **Premier jour** à la une (jeu à la première personne du Career Center, réalisé avec Claude, https://practice-imtbs.github.io/premier-jour/, vidéo https://mediaserver.ip-paris.fr/permalink/v126d6845d7d2uey1kzr/, sources dans `_Projets/CareerCenter/PropositionMarine/PremierJour3D/`), puis L'Entreprise Mystère et Bingo Sujets IMT-BS. Le dernier badge (escape game, ChatGPT Astra, https://practice-imtbs.github.io/escape-game-dernier-badge/) a été retiré de la vitrine le 10/11/2026 ; le jeu reste en ligne.

## Mise à jour

Éditer `index.html` en local, prévisualiser par simple ouverture du fichier,
puis commiter / pousser (GitHub Pages) et/ou redéployer sur l'hébergement
institutionnel.

## Crédits

Service PracTice — Julien Morice — Institut Mines-Télécom Business School.
