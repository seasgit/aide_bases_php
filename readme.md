# PHP/MySQL en 21 heures

## Prérequis
Connaître HTML/CSS ou avoir suivi un cours d'initiation à l'intégration web.

## Objectif
S'initier à la programmation PHP/MySQL directement par la pratique.   
Relier chaque exercice aux chapitres de ce support de cours.  
Savoir utiliser toute la doc en ligne pour une recheche plus approdondie.  

##  Un mot sur les hébergeurs
Un site web doit être accessible aux internautes où qu'ils soient sur la planète.  
Des professionnels sont spécialisés dans la gestion de sites web et proposent des espaces de stockage avec des technologies adaptées au besoin du client. 

## Technologie abordée dans ce cours.
- serveur web HTTP **Apache** couplé avec le langage de script **PHP**.
- serveur **MySQL** _(System de Gestion de Base de Données)_

### Serveur HTTP Apache
Le serveur Apache est un logiciel dont le rôle est de gérer la communication entre le logiciel serveur et le logiciel client _(navigateur)_.   
> On parle de relation client serveur 

### Le Protocle HTTP   
Les échanges entre client et serveur web respectent un protocole de communication appelé HTTP _(Hypertext Transfert Protocol)_
- les urls commmencent par _http_ ou _https_.
- On parle de _"requête HTTP"_ et _"Reponse HTTP"_

### PHP

PHP est un langage de script qui permet côté serveur de construire du HTML avec du contenu dynamique.  
Pour construire des pages web, PHP peut communiquer avec des serveurs de base de données tels que **MySQL**..  
>> **A noter :** Le serveur Apache interprète le code PHP et renvoie au client du code HTML.


### MySQL

MySQL est un logiciel serveur de base de données qui permet d'organiser et traiter des données dans des tables relationnelles.  
Son langage _SQL_ permet d'éxécuter des opérations de selection, d'insertion, de modification et d'effacement de données.

## Installer un serveur en local.

Pour simuler l'exécution d'un site web hébergé, nous avons besoin d'installer un serveur local identique à celui proposé par l'hébergeur.
Il existe des solutions _"trois en un"_ à installer sur notre ordinateur.

**Mac/Windows :**

- Xamp : https://www.apachefriends.org/fr/index.html
- Mamp : https://www.mamp.info/en/
