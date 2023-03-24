# Retour Atelier Solo : Triple Triad Deck Builder

## Retour général

Joli travail ! Il est clair que tu as bien assimilé la plupart des concepts que tu as appris ces dernières semaines. Je vais te faire quelques retours pour te permettre de prendre encore plus de niveau techniques et surtout quelques bonnes pratiques qui t'éviteront de prendre des mauvais réflexes. 💪

## Quelques retours

-   Attention aux vulnérabilités des modules utilisés. Lorsque je fais un « npm install » dans le repo, j’ai une alerte pour une vulnérabilité. C’est a dire que que l’un des modules utilisés possède du code qui expose ton programme à une vulnérabilité (bug, faille, …). Tu peux facilement régler le problème. D’abord en utilisant la commande « npm audit » qui te permet d’afficher la liste des vulnérabilités et leurs origines. Puis en utilisant « npm audit fix » qui dans la plupart des cas réglera le problème en mettant à jours les modules concernés.
-   Par soucis de sécurité, on mettra toutes les clés secretes dans un fichier .env afin de les utiliser sous forme de variable d’environnement. Cela évite d’avoir une clé secrete visible dans un repo git par exemple.
-   Pour la recherche par élément, comme tu as pu le voir sur la correction, on utilise l’élément envoyé via le formulaire directement dans la requête à la base de données. Cela évite de faire 2 fois le travail, la requête te permet de récupérer directement la bonne liste filtré.
-   Pour l’affichage des résultats de la recherche, on peut directement utiliser la vue pour la liste des cartes, en lui donnant une liste de cartes correspondant aux résultats de la recherche.v

## Bon courage pour la suite et continue comme ça !

Si tu souhaites approfondir certains points ou évoquer des choses que je n’ai pas remarqué, n’hésite surtout pas, je suis la pour ça 😉
