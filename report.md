# Optimisation de la pipeline

## Cache

> Remettez la partie que vous aviez enlevée pour conserver en cache les node_modules. Lancez 2 fois la pipeline et analysez le workflow : Combien de temps prend-il pour la création des node_modules et leur sauvegarde dans le cache la première fois ? Combien de temps est gagné la seconde fois en récupérant directement les infos du cache ?

1er: 1m16s
2eme: 1m03s

> La pipeline s'assure que les node_modules mis en cache ne soient pas obsolètes. 
> Comment ?

En comparant le hash.

## Exécution parallèle


