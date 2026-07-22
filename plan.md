# Plan & journal — 2026-07-22

Résumé du travail effectué aujourd'hui sur le site CR7 Tribute, dossier vide
au départ.

## 1. Cadrage du projet

Questions posées à l'utilisateur pour cadrer le projet avant de coder :

- **Type de site** → site vitrine simple (pas de blog, pas d'e-commerce).
- **Stack technique** → HTML/CSS/JS statique, sans framework (choix justifié :
  quelques pages, pas besoin de build, hébergement trivial).
- **Sujet** → site hommage / fan non officiel à Cristiano Ronaldo.
- **Pages souhaitées** → Accueil, À propos, Services/Prestations, Contact,
  Photos, Événements à venir.
- **Style visuel** → sportif moderne (noir / rouge / or, inspiration
  Real Madrid / Portugal), typographie impactante.
- **Photos** → images réelles de Ronaldo à défaut de photos fournies par
  l'utilisateur.

## 2. Choix de contenu

- La page "Services / Prestations" demandée n'avait pas de sens telle quelle
  pour un site hommage : reformulée en page **Palmarès** (titres collectifs,
  distinctions individuelles), fichier conservé sous le nom `services.html`
  pour rester fidèle à la demande initiale.
- Les événements listés dans `evenements.html` sont des **exemples de mise
  en page**, explicitement signalés comme tels (badges "Exemple" /
  "À confirmer" + encart d'avertissement), pas de fausses informations
  présentées comme réelles.
- Le formulaire de contact est fonctionnel côté front (validation, message de
  confirmation) mais n'envoie rien réellement — pas de backend ni de service
  tiers branché.

## 3. Photos

Recherche de photos de Cristiano Ronaldo **sous licence libre** plutôt que des
images copyrightées récupérées au hasard sur le web, pour rester dans un usage
légal :

- Source : [Wikimedia Commons](https://commons.wikimedia.org/), licences
  CC BY / CC BY-SA.
- 6 photos téléchargées dans `images/` (action de jeu, portraits, statue à
  l'aéroport de Funchal).
- Crédit ajouté en pied de page de chaque page, avec lien vers Wikimedia
  Commons.

## 4. Réalisation

- `css/style.css` : variables de couleur (rouge/noir/or), typographie
  (Anton + Inter via Google Fonts), composants (hero, cartes, timeline,
  galerie, agenda d'événements, formulaire), responsive (breakpoints
  desktop / mobile avec menu burger).
- `js/script.js` : toggle du menu mobile, surlignage du lien de nav actif,
  gestion du submit du formulaire de contact (sans backend).
- 6 pages HTML avec header/footer partagés (dupliqués, pas de système de
  templating puisque le site est statique sans build).

## 5. Vérification

- Serveur local (`python3 -m http.server`) pour servir le site.
- Vérification via Playwright : rendu desktop (1280px) et mobile (375px),
  captures dans `screenshots/`, test du menu mobile, test de soumission du
  formulaire de contact (message de confirmation affiché correctement),
  vérification du surlignage de la page active dans la nav.
- Seule erreur console relevée : 404 sur `favicon.ico` (sans conséquence,
  pas de favicon défini).

## 6. Git / déploiement

- Dossier initialisé en dépôt git (`git init`), `.gitignore` minimal
  (`.DS_Store`).
- Premier commit avec l'ensemble du site, remote ajouté
  (`git@github.com:NathanDumiedso/ronaldo.git`), push sur `main`.
- Suite à une demande de l'utilisateur, ajout d'une mention discrète
  "Créé par Donatien et Myriam Dumas" dans le footer de chaque page (classe
  CSS `.footer-credit`, texte petit et grisé, sous la mention "site fan /
  hommage non officiel"). Nouveau commit + push.

## Suites possibles (non faites, à discuter si besoin)

- Remplacer les événements d'exemple par un vrai calendrier.
- Brancher le formulaire de contact à un service d'envoi réel.
- Ajouter un favicon.
- Choisir un hébergeur (Netlify / Vercel / GitHub Pages) pour mettre le site
  en ligne publiquement.
