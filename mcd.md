# Retour MCD

Hello ! J'espère que tu vas bien. C'est bien, dans l'ensemble, tu sembles avoir bien compris comment faire un MCD. Voici une liste des choses à améliorer pour que ton MCD soit parfait 😉

-   Il n'est pas nécessaire de spécifier l'attribut `id` dans les classes.
-   Pense à souligner les identifiants absolues, comme par exemple `email` pour la classe `USER`
-   Il n'y a pas de representation `Many To Many` pour un MCD, soit tu décides de voir `Like` comme une Classe (mais je pense que ce n'est pas necessaire ici), soit tu le gardes comme un lien entre `USER` et `PRODUCT`, avec une carinalaté de `0, N` pour les 2. C'est plus tard, que l'on décidera de créer ou non un table `LIKE` avec une logique de Many To Many, en fonction des choix techniques validés (le type de BDD par exemple)
-   Pour `PRODUCT` tu n'es peut être pas obligé de mettre `mug_type`, je n'en vois pas l'utilité à ce stade. Il faut noter seulement ce qui est necessaire dans un MCD.

## Bon courage ! 💪
