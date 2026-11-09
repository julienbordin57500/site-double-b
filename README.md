# Site du Double B (Folschviller)

Fichiers de la nouvelle version du site https://www.doubleb-folschviller.fr :
- `accueil.html` : la page, collée dans un widget HTML Elementor (modèle « Elementor Canvas »).
- `img/` : les photos, envoyées dans la médiathèque WordPress.

## Plats de la semaine (mise à jour automatique)
- Les plats du jour sont dans `semaine.json`. La page les lit toute seule (script juste après la section `#semaine`).
- Chaque semaine : modifier seulement `semaine.json` et pousser sur `main`. Le site change en quelques minutes, sans passer par WordPress.
- Jour férié : mettre `"ferie": true` (pas de prix). Prix par défaut : 11,50 €.
