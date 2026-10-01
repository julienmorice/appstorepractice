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

## Déploiement

Site 100 % statique, aucune dépendance de build.

- **GitHub Pages** : Settings → Pages → branche `main`, dossier `/ (root)`.
  URL : `https://practice-imtbs.github.io/appstorepractice/`
- **Hébergement institutionnel** : le dossier se dépose tel quel sur n'importe
  quel serveur statique. Site public : https://practice-imtbs.eu

## Déploiement sur practice-imtbs.eu (Hostinger)

```
scp -P 65002 -i ~/.ssh/id_ed25519_hostinger -o IdentitiesOnly=yes index.html learnybot.html learnybot-mascotte.svg u641251867@72.60.93.197:~/domains/practice-imtbs.eu/public_html/
```
(détails de connexion : `../AppStorePractice_site/CLAUDE.md`)

## Mise à jour

Éditer `index.html` en local, prévisualiser par simple ouverture du fichier,
puis commiter / pousser (GitHub Pages) et/ou redéployer sur l'hébergement
institutionnel.

## Crédits

Service PracTice — Julien Morice — Institut Mines-Télécom Business School.
