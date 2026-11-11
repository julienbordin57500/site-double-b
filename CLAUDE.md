# Site du Double B — fiche pour Claude

Site vitrine du restaurant Le Double B (Folschviller) : https://www.doubleb-folschviller.fr
Répondre en français, simplement : le gérant n'est pas développeur.

## Ce que contient ce dépôt
- `accueil.html` : toute la page (HTML, CSS et scripts dans un seul fichier, environ 230 Ko).
  Elle est **collée dans WordPress**, dans un widget HTML Elementor (modèle « Elementor Canvas »).
  Ne jamais la lire en entier : chercher la section voulue par son `id` (`#semaine`, `#bientot`, etc.).
- `semaine.json` : les plats du jour de la semaine. C'est le **seul fichier que le site lit en direct** ici.
- `img/` : les photos, déjà envoyées dans la médiathèque WordPress.

## Ce qui se publie tout seul, et ce qui ne se publie pas
- **`semaine.json`** : pousser sur `main` suffit. La page le relit à chaque visite (script juste après la
  section `#semaine`) ; le site change en quelques minutes, sans passer par WordPress.
- **`accueil.html` et `img/`** : pousser ici ne change **pas** le site. Il faut ensuite recoller la page
  dans le widget HTML d'Elementor et envoyer les nouvelles photos dans WordPress. Le gérant se connecte
  lui-même à WordPress ; Claude ne saisit jamais d'identifiant ni de mot de passe.

## Plats de la semaine (routine hebdomadaire)
Forme exacte de `semaine.json`, toujours 5 jours du lundi au vendredi :
```json
{
  "semaine": "Du 9 au 13 novembre 2026",
  "jours": [
    { "jour": "Lundi",    "plat": "…", "prix": "12,90 €" },
    { "jour": "Mercredi", "plat": "Jour férié (11 novembre) : le restaurant est fermé", "ferie": true }
  ]
}
```
- Prix par défaut : `11,50 €`. Un jour férié a `"ferie": true` et pas de prix.
- Mettre aussi les mêmes plats et prix dans les 5 tickets de `accueil.html` (bloc `id="jours"` de la
  section `#semaine`) : ce sont les plats de secours si le fichier ne se charge pas.
- Pousser sur `main` est autorisé pour cette routine. Vérifier ensuite que
  `https://raw.githubusercontent.com/julienbordin57500/site-double-b/main/semaine.json` est à jour.
- Le visuel Canva de la semaine se fait en même temps (skill `menus-semaine` sur le Mac du gérant).

## Règles
- Ce dépôt est **public** : jamais de mot de passe, de clé, d'adresse de connexion ni de donnée privée.
- Pour toute autre modification que `semaine.json` : demander avant de pousser.
- Ne rien supprimer sans accord.
- La direction artistique, les décisions déjà prises et la maquette de travail sont décrites dans la fiche
  `CLAUDE.md` du dossier `Site-Internet-Double-B` sur le Mac du gérant : la lire avant de toucher au design.
