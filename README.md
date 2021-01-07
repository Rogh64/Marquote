# Marquote: a quotes Bot
## Descriptif
Marquote est un bot Discord permettant de sortir à volonté des citations d'un enseignant de l'IUT de Bayonne et du Pays Basque, **Christophe Marquesuzaà**.

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
***help*** | Permet d'afficher la liste des commandes utilisables par un utilisateur "lambda" (toutes sauf la commande terminate) | !help | Liste des commandes
***fill*** | Permet au bot d'alimenter sa base de données à partir de l'identifiant d'un salon. Les citations sont récupérées dans le salon identifié. Les citations récupérées sont celles commencant et se finissant par des guillemets ou des chevrons. | !fill | "Citations de Marquesuzaà mises à jour !"
***m*** | Commande spécifique à un serveur, pour afficher des citations d'un enseignant de l'IUT de Bayonne et du Pays basque. | !marqua | "Si ma tante en avait, ce serait mon oncle"