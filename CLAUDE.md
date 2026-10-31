# veille-youtube

Veille YouTube de l'utilisateur. Claude repère les vidéos qui comptent, les fait regarder par Gemini et en extrait les méthodes. Réponses en français.

## Organisation

- `.claude/skills/watch/` : skill `/watch` ([bradautomates/claude-video](https://github.com/bradautomates/claude-video), MIT), moteur Gemini.
- `.claude/agents/veille.md` : agent qui trouve et trie les vidéos récentes d'après `sources.md` et écrit `veille/AAAA-MM-JJ.md`.
- `.claude/agents/analyse.md` : agent qui analyse une URL avec Gemini et écrit une fiche méthode dans `analyses/`.
- `sources.md` : chaînes, sujets et critères de la veille.

## Flux habituel

- « Fais la veille » : lancer l'agent `veille`, puis proposer à l'utilisateur d'analyser les vidéos notées 4 ou 5 avec l'agent `analyse`.
- « Analyse <URL> » : lancer l'agent `analyse`.
- Après chaque passe : committer et pousser `veille/` et `analyses/`, pour que rien ne se perde entre les sessions cloud.

## Prérequis

- Variable d'environnement `GEMINI_API_KEY`, définie dans les réglages de l'environnement cloud (ou sur la machine locale). **Jamais dans le dépôt ni dans le chat.**
- Domaines autorisés : `generativelanguage.googleapis.com` (Gemini) et `www.youtube.com` (flux RSS des chaînes).
- Sous Windows en local, utiliser `python` (ou `py -3`) au lieu de `python3`.
