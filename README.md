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
| `sg_entreprise_mystere.webp`, `sg_bingo_sujets.webp`, `sg_dernier_badge.webp` | Vignettes 960×600 des cartes Serious games (Le dernier badge : capture de l'accueil du jeu, ajoutée le 30/10/2026) |
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

Sans vidéo de démo, la colonne de droite reçoit un `tool-video-placeholder` (« Démo vidéo à venir »), comme pour Suggestions LinkedIn Learning au 10/10/2026.

## Quand on ajoute un serious game

Trois endroits de `index.html` : la carte `<a class="game-card">` dans `<div class="games-grid">` (vignette `sg_<nom>.webp` en 960×600), le compteur « N jeux · Accès libre » de la section, et l'encadré « Écosystème PracTice » (chiffre « Serious games » et ligne « Serious games · … »). La grille passe sur 3 colonnes au-delà de 1100 px, 2 en dessous, 1 sous 900 px.

Jeux au 30/10/2026 : L'Entreprise Mystère, Bingo Sujets IMT-BS, Le dernier badge (escape game du Career Center, prototype réalisé avec ChatGPT Astra, https://practice-imtbs.github.io/escape-game-dernier-badge/, sources dans `_Projets/CareerCenter/PropositionMarine/EscapeGame/`).

## Mise à jour

Éditer `index.html` en local, prévisualiser par simple ouverture du fichier,
puis commiter / pousser (GitHub Pages) et/ou redéployer sur l'hébergement
institutionnel.

## Crédits

Service PracTice — Julien Morice — Institut Mines-Télécom Business School.
