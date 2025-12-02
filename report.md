# Optimisation de la pipeline

## Cache

> Remettez la partie que vous aviez enlevée pour conserver en cache les node_modules. Lancez 2 fois la pipeline et analysez le workflow : Combien de temps prend-il pour la création des node_modules et leur sauvegarde dans le cache la première fois ? Combien de temps est gagné la seconde fois en récupérant directement les infos du cache ?

1er: 1m16s
2eme: 1m03s

> La pipeline s'assure que les node_modules mis en cache ne soient pas obsolètes. 
> Comment ?

En comparant le hash.

## Exécution parallèle

> Séparez les différents runs de tests dans différents job (n'oubliez pas de mettre une dépendance sur le job de build). Combien de temps gagne-t-on en parallélisant les tests ? Il faudrait idéalement comparer également la consommation de ressources, mais ce n'est pas évident à mettre en place sur Github Actions, on va donc s'en passer pour l'instant.

Note : chaque job est exécuté dans un environnement séparé, il faut donc réinstaller toutes les fonctionnalités.


On en perd: 1m23s

## Test conditionnels

> Ajoutez, pour chaque job, une condition pour le lancer (un changement dans un dossier donné par exemple) et comparez les temps d'exécution du workflow (sans rien modifier et en modifiant des fichiers des dossiers en questions)