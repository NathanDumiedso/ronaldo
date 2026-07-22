# CR7 Tribute

Site vitrine statique en hommage à Cristiano Ronaldo. Site fan non officiel,
sans lien avec le joueur, ses clubs ou ses représentants.

## Pages

| Fichier             | Page                       |
| -------------------- | -------------------------- |
| `index.html`          | Accueil                    |
| `a-propos.html`       | À propos / biographie      |
| `services.html`       | Palmarès (titres, records) |
| `photos.html`         | Galerie photo              |
| `evenements.html`     | Événements à venir         |
| `contact.html`        | Contact                    |

## Stack

HTML / CSS / JavaScript vanilla — pas de framework, pas d'étape de build.
Polices via Google Fonts (Anton + Inter).

## Lancer le site en local

```bash
python3 -m http.server 8000
```

Puis ouvrir `http://localhost:8000`.

## Structure

```
├── index.html, a-propos.html, services.html, photos.html, evenements.html, contact.html
├── css/style.css      # styles partagés (variables, layout, responsive)
├── js/script.js       # menu mobile, surlignage nav active, formulaire de contact
├── images/            # photos de Cristiano Ronaldo (voir Crédits)
└── screenshots/       # captures utilisées pour vérifier le rendu
```

## Crédits photos

Les photos dans `images/` proviennent de [Wikimedia Commons](https://commons.wikimedia.org/)
et sont utilisées sous licence Creative Commons, avec attribution aux photographes
d'origine. Ce sont des images d'exemple : à remplacer librement par d'autres visuels.

## À faire avant une mise en ligne réelle

- Remplacer les événements de `evenements.html` (actuellement des exemples de mise
  en page) par un vrai calendrier.
- Brancher le formulaire de `contact.html` à un service d'envoi (ex. Formspree)
  ou à un backend : il ne fait actuellement qu'afficher un message de confirmation
  côté client, sans envoyer de message.

## Auteurs

Créé par Donatien et Myriam Dumas.
