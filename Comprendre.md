# Comprendre

TCP/IP (Transmission Control Protocol/Internet Protocol)
ce sont des protocoles qui définissent comment les ordinateurs communiquent entre eux sur Internet.
besoin d'avoir l'adresse IP de l'ordi qui envoie le message + celle de celui qui le reçoit

-

le port number (différent selon le type de service(transfert fichier, envoie d'une page html etc) )

DNS: serveur de mappage qui lie les url des sites aux adresses IP
ex: google.com correspond à 172.217.7.206

réponse avec le status code + le type de contenu (html page)

**_ Quels sont les rôles respectifs du HTML, du CSS et du JavaScript sur une page web ? _**

Front-end

HTML: le squelette de la page web avec son contenu textuel et les images qui vont être présentes
CSS: mise en page, l'esthétique du site
Javascript: logique du site, fonctions algo qui vont permettre une meilleure optimisation du site
--> on peut rendre le tout interactif.
On pourrait imager avec les notions suivantes :
Dans une phrase le HTML est le nom, le CSS est l’adjectif et le JS est le verbe.

Back-end (côté serveur)
pour stocker des données
langages utilisés: nodeJs,PHP,RubyOnRails
pour les données: MySQL, SQLServor

**_ Qu’est-ce que le DOM ? _**

Le Document Object Model permet à des scripts d’examiner et de modifier le contenu du navigateur web.
Interface pour pages web. C’est une API permettant aux programmes de lire et de manipuler le contenu de la page, sa structure et ses styles.

Il fournit une représentation structurée du document sous forme d'un arbre et définit la façon dont la structure peut être manipulée par les programmes, en termes de style et de contenu. Le DOM représente le document comme un ensemble de noeuds et d'objets possédant des propriétés et des méthodes. Les noeuds peuvent être associés à des gestionnaires d'évènements.

Les objets document et window sont ceux dont les interfaces sont les plus souvent utilisées dans la programmation DOM. En termes simples, l'objet window représente quelque chose comme le navigateur, et l'objet document est la racine du document lui-même.

**_ Qu’est-ce qu’une API ? _**

Application Program Interface fait dialoguer des applications (l'une consommatrice d'un service et l'autre productrice de ce service).
Exemple: Uber utilise l'API de Google Maps pour définir le trajet le plus court et l'API de paiement en ligne d'Apple pour facturer ses courses.

--> permet de simplifier l'utilisation d'appli en ayant recours à des API déjà existante (API payante évidemment)

Pour utiliser une API, le dev va devoir effectuer des requêtes en utilisant la documentation spécifique de l'API (qui définit son cadre d'usage)

API Rest c'est une API qui respecte les standards du web, basée sur le http

> garantit une meilleure intégration à l'architecture du web

REST (REpresentational State Transfer) API:

- multiples endpoints (GET/POST)
- JSON données utilisées
- tout type de langage/framework utilisé
- interface uniforme
- stateless: le serveur ne sauvegarde aucune des requêtes ou réponses précédentes
- cacheable (ou sauvegardable) un cache est un moyen de sauvegarder des données pour pouvoir répondre plus facilement aux prochaines requêtes qui seront identiques
  --> permet de ne pas avoir à faire constamment des requêtes aux serveurs
- layered system (système de couches): un composant utilisant REST n'a pas accès aux composants au-delà du composant avec lequel il interagit

**_ Quelles sont les 4 grandes fonctionnalités les plus communément fournies par une API ? _**

**_ Quel protocole réseau utilise un site/une application web pour communiquer avec une API ? _**

Protocole HTTP (API Rest) prend en charge le chiffrement TLS (Transport Layer Security). Le standard TLS permet de garder une connexion Internet privée et de vérifier que les données échangées entre deux systèmes (un serveur et un serveur, ou un serveur et un client) sont chiffrées et non modifiables.

> garantit une meilleure intégration à l'architecture du web
> Les API REST utilisent également le format de fichier JSON (JavaScript Object Notation), qui facilite le transfert des données via les navigateurs web. Grâce à l'utilisation du protocole HTTP et du format JSON, les API REST n'ont pas besoin de stocker des données ni de recréer des paquets, ce qui les rend ainsi plus rapides que les API SOAP.

Protocole SOAP: utilise des protocoles intégrés connus sous le nom de WS Security (Web Services Security). Ces protocoles définissent un ensemble de règles qui permettent d'ajouter un mécanisme de confidentialité et d'authentification.
Les API SOAP sont généralement reconnues pour leurs mesures de sécurité plus complètes, mais elles nécessitent un plus haut niveau de gestion. C'est pour cela qu'elles sont particulièrement bien indiquées pour les entreprises qui traitent des données sensibles.

**_ Qu’est-ce qu’une requête ? Nommer 4 types de requêtes. _**

Une requête est une demande qu'on va effectuer auprès de l'API pour obtenir une information, l'API va servir d'intermédiaire pour récupérer les informations dans les bases de données.

A) structure des requêtes:

Verbe HTTP + URI + Version HTTP + Headers + Body (facultatif)

1.  Dans l'API REST il y a 4 types de requêtes en fonction des verbes HTTP:

        - GET

    permet de récupérer les données d’une ou plusieurs entités dans une ressource

        - POST
        Permet de rajouter des entités à une ressource. Les données sont envoyées dans le corps de la requête.

(par défaut, une requête POST intègre le format Content-Type:application/x-www-form-urlencoded. Ce format est déconseillé avec les APIs REST car il ne correspond pas aux formats de réponse utilisés (JSON, XML))

    - PUT
    Permet de modifier les données d’une entité dans une ressource.

L’url doit indiquer l’identifiant de l’entité. Si l’identifiant est inexistant, l’entité devrait être créée.

    - DELETE
    Permet de supprimer une entité dans une ressource.

    - PATCH (optionnel)
    Permet de modifier en partie les données d’une entité dans une ressource.

Ce verbe ne fait pas partie des opérations de base pour la persistance des données mais pourrait être considéré comme une extension au verbe PUT lui permettant de simplifier les mises à jour partielles.

2. L'URI (le chemin de la ressource) est un moyen d'identifier les ressources et on va préciser l'ID d'un utilisateur si on veut obtenir des info spécifiques à son sujet.

3. Un header permet de faire passer des info supplémentaires sur le message (langage utilisé, date, logiciel que la personne utilise, clé d'authentification)

4. Le body n'est utilisé qu'avec la requête de type PUT (mise à jour) ou POST (création). Les données envoyées sous format JSON.

B) Le format des réponses

Version HTTP + Code de réponse HTTP + Headers + Body

Le code de réponse HTTP aide le développeur et/ou le client à comprendre le statut de la réponse.

100+ ➡ Information

200+ ➡ Succès

300+ ➡ Redirection

400+ ➡ Erreur client

500+ ➡ Erreur serveur

Exemples:
200: OK
301: Moved Permanently
403: Forbidden
404: Not Found
500: Internal Server Error

dans le body contient l'information qu'on a demandé lorsqu'on a fait la requête (sauf si celle-ci n'a pas été trouvée)

DBMS (DataBase Management Systems): 4 types

- Navigational DBMS
- Relational DBMS (plus commun: mySQL,Microsoft SQL Servor )
- SQL DBMS
- Object Oriented DBMS (données stockées sous forme d'objets)

**_ SQL _**

utilise des schémas (moins flexible en terme de données mais c'est plus prévisible)
utilise les relations (avantage pour la mise à jour car juste besoin de mettre à jour le user)

types de relations:

- entre l'utilisateur et les données de contact (id, mail etc
- entre l'utilisateur et le produit (l'utilisateur )
- entre l'utilisateur et les rôles qui peut avoir (admin, editor etc ) = création d'un statut entre les deux UserRoles

- vertical scaling possible

**_ No SQL _**

Il n'y a pas de schéma particulier (on peut avoir des colonnes de données vides )
--> plus flexible
Il n'y a pas de relations ou très peu entre les différentes bases de données = ça va plus vite, on fait des requêtes et récupère les données directement depuis les collections
Mais les données sont en double, et s'il faut mettre à jour les données on doit le faire sur chaque doublon.

- vertical ou horizontal scaling (rajouter des serveurs et merger plus de données )
