# Marquote: a quotes Bot

## Descriptif
Marquote est un bot Discord permettant de sortir à volonté des citations d'un enseignant de l'IUT de Bayonne et du Pays Basque, **Christophe Marquesuzaà**.
Le bot est également doté d'une fonction lui permettant de réagir à des mots clés sélectionnés parmi les citations, pour répondre par une citation liée et créer des situations humoristiques.

## Installation

- Installation des dépendances : `cd marquote-master && npm install`
- Changer le fichier `.env-sample` en `.env`
- Modifier les valeurs du fichier `.env` selon indications dans la partie **Paramétrage**
- Lancer le bot avec la commande `node index.js`

## Paramétrage

Le paramétrage se fait via le fichier `.env`. Les options sont les suivantes :
- ***TOKEN*** (à renseigner **obligatoirement**) : Le token du bot à récuperer depuis l'application Discord Developper
- ***PREFIX*** (valeur par défaut = **!**) : Le préfixe à écrire avant chaque commande du bot
- ***ADMIN_ID*** (valeur par défaut = **377171004167946242**) : L'identifiant de l'utilisateur administrateur de l'instance du bot. Par défaut il s'agit de son créateur originel
- ***QUOTES_CHANNEL_ID*** (valeur par défaut = **380444002538749964**) : L'identifiant du salon de citations dans lequel le bot ira piocher pour alimenter sa base de données de citations

## Commandes

> Toutes les commandes sont au format suivant : "_prefixe_commande" **SAUF** la commande ping qui s'écrit seule. 

La liste des commandes est la suivante :

Commande | Description | Exemple | Résultat attendu
------------ |  ------------- | ------------- | ------------
***ping*** | Permet de vérifier le bon fonctionnement du bot | ping | "pong"
***help*** | Permet d'afficher la liste des commandes utilisables | !help | Liste des commandes
***f*** | Permet au bot d'alimenter sa base de données à partir de l'identifiant d'un salon. Les citations sont récupérées dans le salon identifié. Les citations récupérées sont celles commencant et se finissant par des guillemets ou des chevrons | !fill | "Citations de Marquesuzaà mises à jour !"
***s*** | Le bot enverra un message dans le salon ou la commande est exécutée, avec le message indiqué ensuite. Le message contenant la commande sera supprimé, comme si le bot parlait seul | !speak Hello. | "Hello."
***m*** | Permet d'obtenir une citation d'un enseignant de l'IUT de Bayonne et du Pays basque. Il s'agit de la fonction principale du bot | !m | "Si ma tante en avait, ce serait mon oncle"
***c*** | Permet d'obtenir une auto complétion d'une citation enregistrée | !c Bitch | "... ! **dabe**"

## Analyse de mots clés

Comme expliqué dans le partie **Descriptif**, le bot est capable, à chaque message envoyé, d'analyser le message pour y chercher des mots clés d'une citation et réagir avec la citation correspondante.
Le fonctionnement est le suivant :
* Lors de l'enregistrement des citations, le bot détermine pour chacune des mots clés. La citation et les mots clés correspondants sont stockés dans le fichier `keywords.json`.
* A chaque nouveau message, le bot va parcourir le fichier `keywords.json` et tester la présence de chaque mot clé pour chaque citation dans le message.
* Si le bot trouve plus d'un tiers des mots clés d'une citation dans le messages envoyé, *it's a match!*
* Il y a alors 20% de chances que le bot dise juste après le message, sans aucun enclenchement de commande, la citation liée aux mots clés trouvés.