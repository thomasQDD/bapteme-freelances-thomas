# Explications Fetch

Hello ! J'espère que tu vas bien.

Ravi que tu t’intéresse à Fetch. Pour faire simple, la méthode `fetch()` te permet de faire des requête HTTP (que se soit vers une route de ton serveur ou vers un autre). Elle te permet ensuite de pouvoir récupérer cette réponse et de la traiter. Tu vas voir que tu vas t’en servir régulièrement pour faire des requêtes à des API par exemple.

Je vais te montrer comment l’utiliser dans ton rendu de parcours pour pouvoir ajouter des cartes dans ton deck directement depuis la liste de carte sans avoir à rafraîchir la page.

-   Je créé un fichier `deck.js` qui sera utilisé par view `cardList.ejs` :

    ```javascript
    // file: /public/js/deck.js
    const addCardLinks = document.querySelectorAll(".link--addCard");

    // Pour chaque lien, on lui met un eventListener qui appelera la fonction addCard dès que l'on clique dessus
    for (let index = 0; index < addCardLinks.length; index++) {
    	const link = addCardLinks[index];

    	link.addEventListener("click", (event) => {
    		// On bloque notre evenement pour que le fait d'avoir cliquer sur le lien ne nous redirege pas à l'adresse du lien
    		event.preventDefault();
    		addCard(link);
    	});
    }

    const addCard = async (link) => {
    	// On fait notre requête au serveur pour ajouter notre carte
    	// Pour cela, on utilise le href de notre lien, comme ça pas besoin de s'embéter à savoir l'id de notre carte, il est déjà dans le lien
    	const jsonResponse = await fetch(link.href).then((response) => {
    		// Ici on traite la réponse de façon à ne récupérer que le json renvoyé
    		// Faire un console.log(reponse) pour voir que sans cela fetch nous renverai une réponse brut qui contient d'autres information qui ne nous sont pas utile ici
    		return response.json();
    	});

    	// Si le status retourné est "ok" alors on fait l'action souhaité
    	if (jsonResponse.status === "ok") {
    		// On change le href du lien pour qu'il pointe maintenant vers la route qui remove la carte du deck
    		link.setAttribute("href", link.href.replace("add", "remove"));
    		// On remplace le "[ + ]" par "[ - ]"
    		link.textContent = "[ - ]";
    		alert(jsonResponse.message);
    	}
    };
    ```

-   Je modifie la methode addCard de façon à ne plus rediriger vers la page deck mais à renvoyer un JSON :

    ```javascript
    // file: /app/controllers/cardController.js
    addCard: async (req, res) => {
    	const cardId = Number(req.params.id);
    	try {
    		const card = await dataMapper.getOneCard(cardId);
    		console.log("card", card);

    		// // Initialiser le tableau si inexistant ==> ajouté dans un Middleware
    		// if(!req.session.cards) {
    		//   req.session.cards = [];
    		// }
    		console.log("req.session.cards", req.session.cards);
    		if (card) {
    			// Rechercher si la carte est déjà dans le deck, si non l'ajouter, si oui ne rien faire
    			const findCardInDeck = req.session.cards.find(
    				(card) => card.id === cardId
    			);
    			// console.log("add ?",findCardInDeck);
    			if (!findCardInDeck && req.session.cards.length < 5) {
    				req.session.cards.push(card);
    			}
    			res.status(200).json({ status: "ok", message: "Card added" });
    			console.log("req.session.cards", req.session.cards);
    		}
    	} catch (error) {
    		console.error(error);
    		res.status(500).json({
    			status: "error",
    			message:
    				"Error during process, try again or come back later, sorry..",
    		});
    	}
    },
    ```

-   J'importe mon fichier `deck.js` dans la view `cardList.ejs`

    ```html
    <!-- file: /app/views/main/cardList.ejs -->

    [...]

    <script type="text/javascript" src="/js/deck.js"></script>
    <%- include('partials/footer') %>
    ```

Et voilà, normalement, si je n'ai pas fais d'erreur en retrenscrivant le code, tu devrais pouvoir tester fetch dans ton code.
Pour t'entrainer, je te propose de modifier ta methode `removeCard` de façon à renvoyer également un JSON avec, puis de modifier le code de `deck.js` de façon le faire fonctionner pour enlever une carte du deck. Tu peux également gérer les actions à effectuer en cas d'erreur (affichage d'un message par exemple).

Si je n'ai pas été clair surtout n'hésite pas 😉

## Bon courage 💪
