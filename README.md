# SharedHealth

Plugin Paper (Minecraft Java 1.21.11) qui transforme la partie en mode **vie/faim partagees**.

## Compatibilite

- Paper 1.21.x (teste pour 1.21.11)
- Java 21

## Installation

1. Compiler le plugin (voir section Build) ou recuperer le `.jar` deja compile.
2. Copier le fichier `.jar` dans le dossier `plugins/` de ton serveur Paper.
3. Demarrer (ou redemarrer) le serveur.

## Utilisation (regles du mode)

Le plugin ne propose **aucune commande** : tout est automatique.

- Les PV sont partages entre tous les joueurs connectes.
- La faim (food bar) est partagee.
- Les effets Regeneration, Bonus de sante et Absorption sont synchronises.
- La regeneration est geree pour eviter les cumuls abusifs (pas de stack multi-joueurs).
- Si un joueur meurt, tout le groupe meurt.
- A la mort partagee :
  - inventaires vides (armure incluse),
  - coffres de l'End vides,
  - drops de mort vides,
  - objets au sol supprimes.
- Si un joueur etait hors ligne pendant une mort partagee, a sa reconnexion il est resynchronise au meme etat de progression (inventaire/coffre de l'End nettoyes).

## Build local

```bash
mvn -DskipTests clean package
```

Le jar est genere dans `target/`, par exemple :

- `sharedhealth-1.1.0.jar`

## Donnees persistees

Le plugin enregistre sa progression dans :

- `plugins/SharedHealth/shared-health.yml`
