# Retour Atelier Solo : Triple Triad Deck Builder

## Retour général

Bravo ! C'est du super travail ! On voit bien que tu as complètement comprit les notions de ces dernières semaines. Je vasi te faire quelques retours pour te permettre de prendre encore plus de niveau techniques et surtout quelques bonnes pratiques qui t'éviteront de prendre des mauvais réflexes. 💪

## Quelques retours

-   Eviter d’utiliser « start » comme script pour lancer le server avec Nodemon, Nodemon étant un outils qui permet de lancer le server avec ce que l’on appelle un watcher, qui permet d’update l’instance du serveur à chaque modification de fichier. On aura tendance à utiliser « dev » pour Nodemon et « start » pour Node. Ce que tu as fait fonctionne très bien, c’est plutôt une question de bonne pratique qu’il vaut mieux s’imposer tout de suite pour éviter les mauvaises habitudes.
-   Penser a supprimer les commentaires qui ne sont pas la pour expliquer le code (debug, historique du code —> c’est git qui permet de voir les changements historique du code).
-   Pensez également à supprimer les logs qui ne sont pas utiles en dehors du développement. Les logs qui doivent être laissés sont seulement ceux qui permettent de signaler une erreur de fonctionnement comme par exemple dans un « catch ». En entreprise, on peut éventuellement mettre en place un système de debug log. Mais l’affichage de ces logs sera conditionné à une variable d’environnement car on ne veut afficher tous les logs de debug sur la production par exemple.
-   Pour aller plus loin, il pourrait être intéressant de ne pas rafraîchir les pages a chaque actions sur le deck mais plutôt de faire des requêtes au serveur avec « fetch » de façon a mettre à jour la session. Pour cela il faudrait que les routes "/deck/add/:id" et "/deck/remove/:id" retourne du json plutôt que de faire un redirect comme c’est le cas pour le moment. À la réponse du serveur, tu n’aurais qu’à modifier l’affichage en conséquence. Par exemple, si une carte a bien été ajouté, alors tu remplaces le [+] par un [-] et tu fais en sorte que le clic sur ce dernier lance un appelle pour remove la carte du deck.

## Bon courage pour la suite et continue comme ça !

Si tu souhaites approfondir certains points ou évoquer des choses que je n’ai pas remarqué, n’hésite surtout pas, je suis la pour ça 😉
