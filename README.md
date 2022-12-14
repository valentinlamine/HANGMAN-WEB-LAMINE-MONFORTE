# Répartition du travail

## Répartition du travail prévu

Partie Backend :

- Valentin : Adapter le fichier pendu.go en package pendu utilisable en web
- Valentin : Mise en place du cœur du serveur (fichier main.go)
- Valentin : Intégration du pendu au serveur web
- Valentin : mise en place de la récupération de formulaire et envoie de donnée
- Valentin : mise en place du système de statistiques
- Valentin : mise en place du système de difficulté

Partie Frontend :

* Pierre : Mise en place du contenu de la page (HTML)
* Pierre : Mise en place du style et de la mise en page des page web (CSS)
* Pierre : Création des deux pages Index.html et Hangman.html
* Pierre : Création d'une version adaptative du site pour mobile

## Répartition du travail réel

Partie Backend :

- Valentin : Adapter le fichier pendu.go en package pendu utilisable en web
- Valentin : Mise en place du cœur du serveur (fichier main.go)
- Valentin : Intégration du pendu au serveur web
- Valentin : mise en place de la récupération de formulaire et envoie de donnée
- Valentin : mise en place du système de statistiques
- Valentin : mise en place du système de difficulté

Partie Frontend :

* Valentin : Mise en place du contenu de la page (HTML)
* Valentin : Mise en place du style et de la mise en page des page web (CSS)
* Valentin : Création des deux pages Index.html et Hangman.html
* Valentin : Création d'une version adaptative du site pour mobile
* Valentin : Rédaction et mise en forme du README.md

# Organisation des dossiers

Le HANGMAN WEB est classé dans différents dossiers :

* Dans le dossier templates nous trouvons les deux templates utilisé dans le projet :

  * [index.html](templates/index.html) qui permet de créer le nom d'utilisateur et de choisir la difficulté
  * [hangman.html](templates/hangman.html) qui est le template ou le pendu se déroule
* Dans le dossier css nous trouvons le fichier [style.css ](css/style.css)qui contient le CSS de nos deux templates web. Il n'y a qu'un css pour deux pages car les deux pages ayant beaucoup de point en commun, cela permet de gagner de la place.
* Le dossier images contient toutes les images du site :

  * Le fichier potence.ico utilisé pour l'icône du site Web
  * Le dossier positions dans lequel se trouve toutes les positions du pendu en fonction du nombre d'essai restants. **Les positions ont été dessiné à la main** **puis converti d'un fichier en .html vers un fichier en .svg**
* Le dossier Pendu contient le package pendu, c'est à dire :

  * Le fichier pendu.go qui est le package contenant toutes les fonctions pour créer et faire fonctionner le pendu
  * Les fichiers words.txt, words2.txt, words3.txt qui sont les dépendances du package pendu. Ces 3 fichiers sont ceux utilisé dans le choix de difficulté.

# Fonctionnement du code

## Le Fichier main.go

Le fichier main.go est le fichier central du projet, c'est lui que l'on exécute lors du lancement du serveur. Ce fichier est divisé en trois grandes fonctions :

* La fonction main() qui :
  * lance le serveur ainsi qu'initialise sa boucle principale
  * charge en mémoire les dossier css, images et positions
  * et appelle les deux fonctions qui gèrent les templates
* La fonction IndexHandler() qui :#### * gère le template [index.html](templates/index.html)
  * Permet d'enregistrer le nom d'utilisateur
  * Choisir la difficulté
* La fonction HangmanHandler() qui :
  * gère le template [hangman.html](templates/hangman.html)
  * gère le déroulement du jeu du pendu
  * gère l'initialisation du jeu du pendu ainsi que ces statistiques

## Le fichier pendu.go

Le fichier pendu.go est le package du pendu, il contient toutes les fonctions nécessaires à la création et au déroulement du jeu du pendu

## Les fichiers hangman.html & index.html

Ces fichiers sont les fichiers de templates utilisé par main.go, ils sont interprété par leur fonctions respectives (IndexHandler & HangmanHandler) avant d'être renvoyé par le serveur.
