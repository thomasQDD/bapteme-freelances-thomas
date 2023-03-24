# Retour Atelier Solo : Triple Triad Deck Builder

## Retour général

Hello ! J'ai vu que tu as eu quelques difficultés sur ce parcours. Ne t'inquiète pas, il n'y a rien d'insurmontable ! On va essayer de voir ensemble comment régler tout ça 😉 Je vais commencer par te faire quelques retours concernant ton rendu sur ce parcours.

## Quelques retours

-   Attention de ne pas te rajouter trop vite du travail, tu as essayé de faire plusieurs choses interessantes mais qui ne faisaient pas parti du sujet. Par exemple, tu as voulu remettre en forme la liste des cartes, or tu n’avais qu’a simplement utiliser la vue EJS fournie tel qu’elle l’était en ne changeant que les url des liens déjà présent pour les envoyer vers les bonnes routes. Tu as également modifié l’architecture du dossier views pour déplacer les vues partagées dans un dossier Partials et créé une vue notFound. En soit, ce n’est pas une mauvais e initiative, bien au contraire, mais c’est une charge de travail importante que tu te rajoute avant même d’avoir terminé les taches qui sont demandées dans ce sujet. Je te conseille pour la prochaine fois de faire ces suppléments seulement une fois que tu as terminé ton rendu. Comme ça tu sais que tu peux rendre quelque chose de complet avant de te lancer sur des Bonus.
-   Pour l’affichage des détails d’une carte, tu cherches à utiliser une boucle for alors que tu n’en as pas besoin. Tu possède à ce moment là un objet qui correspond à ta carte et que tu as stocké dans une variable « oneCard ». 2 choses a propos de ton code:

    -   tu peux utiliser directement oneCard pour accéder aux différents attributs de ton objet sans passer par une boucle for.
    -   quand tu utilises une boucle « for » avec le « of », c’est bien la variable avant le of qui va contenir chaque élément de ton tableau tour à tour comme dans l’exemple suivant:

        ```javascript
        const cards = [
        	{ name: "toto", level: 3 },
        	{ name: "tata", level: 5 },
        	{ name: "titi", level: 4 },
        ];

        for (const card of cards) {
        	console.log(card);
        }

        // Retours en console:
        // { name: "toto", level: 3 }
        // { name: "tata", level: 5 }
        // { name: "titi", level: 4 }
        ```

-   Pour la partie recherche, ici tu avais déjà une view qui était créé et tu n’avais pas besoin d’en faire une autre. Dans la consigne, la vue à créé si besoin était celle pour l’affichage des résultats de la recherche (même si d’ailleurs on pouvait utiliser celle de la page d’affichage de la liste des cartes).

## Pour conclure

Je te propose une fois que tu auras pris connaissance de ces retours, c’est de revenir vers moi afin de faire un point ensemble pour s’assurer qu’il n’y a pas de blocage technique que je n’aurais pas vu a travers ton rendu. Encore une fois, n’est pas d’inquiétude, il n’y pas de problème sans solutions, tu vas y arriver 💪
