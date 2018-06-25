# The National Bank
# ============

## Project : prjWin_NationalBank_Rm
Été-2017


The objective : To understand the class relationships and the concepts of object oriented programming

[Diagramme de classes UML](https://lipn.univ-paris13.fr/~gerard/docs/corrections/uml-corr02.pdf)

## Getting started

A bank has several agencies spread over the Quebec territory. A bank is characterized by the name of its director, 
its global capital, its own name and the address of its head office.

### Summary of classes:

We have these classes and their propierties.

![Summary of classes](/img/organization.jpg "Summary of classes")

We must complete the following class diagram using the required symbols to specify 
 *abstraction, encapsulation, inheritance, and polymorphism.*

### Summary of classes:


![Class Diagram](/img/classes.jpg "Class Diagram")

We did the analysis and we get the next diagrams.

### abstract class clsAccount:

![Class Diagram Account](/img/account.jpg "abstract class clsAccount")

### abstract class clsHuman:

![Class Diagram Human](/img/human.jpg "abstract class clsHuman")

### Class Diagram Developed:

![Class Diagram Developed](/img/Class_Diagram_StrategyPattern.jpg "Class Diagram Developed")

We implemented with C# and Visual Studio the abstract classes account (clsAccount) and human (clsHuman) and all their offspring.

### Concepts.

#### Encapsulation is -

 * Hiding Complexity,
 * Binding Data and Function together,
 * Making Complicated Method's Private,
 * Making Instance Variable's Private,
 * Hiding Unnecessary Data and Functions from End User.
 
Encapsulation implements Abstraction.

 #### Abstraction is -
 
 * Showing Whats Necessary,
 * Data needs to abstract from End User,
 
[What is the difference between Abstraction and Encapsulation ?](https://www.youtube.com/watch?v=1Q4I63-hKcY)
 
#### Inheritance is -

When we can reuse (inherits), the behavior of a super class (parent class) in a child class (class that inherits the members of the base class).

[Inheritance in C# and .NET](https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/inheritance)

Not all membersfrom the parent class are nherited in the the child class.

 * Static constructors, *which initialize the static data of a class*.
 * Instance constructors, *which you call to create a new instance of the class. Each class must define its own constructors*.
 * Finalizers, *which are called by the runtime's garbage collector to destroy instances of a class*.
 
 
*All members from the super class are inherited to the lower classes, but if they are visible or not depends on their accessibility.*

Private *members are visible only in derived classes that are nested in their base class.*
Protected *members are visible only in derived classes.*
Internal *members are visible only in derived classes that are located in the same assembly as the base class.*
Public *members are visible in derived classes and are part of the derived class' public interface.*
 











Dans la racine de ce projet se trouve un fichier config.js contenant les paremètres globaux de notre application, comme les paramètres de notre connexion à la base de données, le port de notre application, les messages d'erreurs du back-end, etc.

### Prérequis

Database : Mysql
Langage de programmation : nodeJS (l'installation du framework Express est requis).

### Installation

npm install

## Code source
**/routes/**

* **/routes/database.js**
Dans ce module se trouve toutes les fonctions liées à la manipulation de la base de données.
Liste de fonctions:
- detruireCollection(typeInstallation, callback): cette fonction supprime les données selon le type d'installation.
- insertCollection(donnéesJson, callback): cette fonction ajoute des données à notre base de données.
- trouver(critères, champs, callback): cette fonction retourne les données dans un objet Json
- trouverUnique(champs, critères, callback): cette fonction retourne la liste d'installations sans doublons dans un tableau de type chaîne.
- updateCollection(id, jsonData, callback): cette fonction met à jour les données selon l'id.
- removeCollection(id, callback): cette fonction supprime les données selon l'id.

* **/routes/index.js**
Ce module contient toutes les routes de l'application.
Liste de fonctions:
- recherche(critères, champs, callback): cette fonction appelle la fonction database/trouver() et trie l'information par nom d'installation.
- listeUnique(critères, champs, callback): cette fonction appelle la fonction database/trouverUnique() et trie l'information par nom d'installation.
- ins_mauvaise_condition(): cette fonction retourne les installations en mauvaises conditions.
- genererCSV(data): cette fonction reçoit les données en format Json objet et retourne une chaîne contenant les données en format CSV
- msgErreur(reponse): cette fonction reçoit une variable de type réponse provenant des différents services.
Liste de services: tous les détails se retrouvent dans la route /doc
- GET /installations : URL exemple: http://localhost:3000/installations?arrondissement=LaSalle
- GET /nom_installation : URL exemple: http://localhost:3000/nom_installation?nom=Parc%20Haymard
- GET /all-installations/
- GET /installations-mauvaise-condition
- GET /installations-mauvaise-condition/xml
- GET /installations-mauvaise-condition/csv
- PATH /update-glissade/:id  : ce service reçoit l'id et les données Json (voir le schéma : schemas/update-glissade)
- DELETE /supprimer-glissade/:id  : ce service reçoit l'id de l'installation.
- PATH /update-piscine/:id  : ce service reçoit l'id et les données Json (voir le schéma : schemas/update-piscine)
- DELETE /supprimer-piscine/:id  : ce service reçoit l'id de l'installation.

* **/routes/taches.js**
Ce module appelle les modules routes/get-csv.js et routes/get-xml.js pour exécuter la tâche cron.

**/views/**

* **/views/index.pug**
Cette vue contient l'interface utilisateur (page d'accueil) de notre application. 

* **/views/xml_installation.pug**
Cette vue affiche les données de toutes les installations en mauvaises conditions en format XML. 

## Mise en production

La commande suivante doit être lancée à partir de la ligne de commande (Terminal ou DOS) dans le dossier de l'application, sur le serveur web:

git pull

Ouvrez notre fureteur et saisissez l'adresse suivante :
http://gestionemam.csdm.qc.ca:3000/admin


## Technologies utilisées :
Front-end:
* Pug
* Bootstrap 3.3.2
* Datatables (https://datatables.net) 
* JQuery
* HTML5

Back-end:
* Node.js 8.6
* express.js 4
* xmldom
* node-cron
* raml2html
* jsonschema

Base de données:
* Mysql


## Versions et gestionnaire de source 

Ce projet utilise Gitlab.com comme gestionnaire de source dans le dépôt suivant:
https://gitlab.com/AndyDelRisco/ConservatoireEMRTM.git. 

Historique de versions : https://gitlab.com/AndyDelRisco/ConservatoireEMRTM/commits/master

## Auteur

* **Ricardo Mendoza** - *Analyste programmeur Jr* 

## Licence

Ce projet utilise les licences suivantes:
- Copyright Andy Del Risco & Ricardo Mendoza:  Licensed under the Apache License, Version 2.0 http://www.apache.org/licenses/LICENSE-2.0
- Booststrap & DataTables, the MIT License (MIT)

