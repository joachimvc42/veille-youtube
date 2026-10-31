# veille-youtube

Claude regarde YouTube pour toi : il repère les vidéos qui comptent (agent `veille`), les fait analyser par Gemini et en tire la méthode, étape par étape (agent `analyse`).

## Utilisation (dans une session Claude Code sur ce dépôt)

- « Fais la veille » : liste des vidéos récentes à regarder, notées de 1 à 5, dans `veille/`.
- « Analyse https://youtube.com/watch?v=… » : fiche méthode dans `analyses/`.
- « Ajoute la chaîne X à la veille » : met à jour `sources.md`.
- `/agents` : voir les deux agents.

## Mise en place (une fois)

1. Créer une clé gratuite sur https://aistudio.google.com/apikey.
2. L'ajouter comme variable d'environnement `GEMINI_API_KEY` dans les réglages de l'environnement cloud (menu de l'environnement dans la barre de titre, puis Edit).
3. Autoriser les domaines `generativelanguage.googleapis.com` et `www.youtube.com`.

Avec la clé gratuite, Google peut utiliser les contenus envoyés pour améliorer ses produits : n'y passer que des vidéos publiques.
