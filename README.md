# URL de la partie théorique : https://docs.google.com/forms/d/e/1FAIpQLSdSqHkaevIBLqGXX4et34PeZoNX2EE2M2hQy-qZxbDHWcsbqg/viewform?usp=sf_link
# Durée : 2,5 jours ou 20h (8h x 2 + 4h)
# Données
Vous devez ajouter dans votre base de données locale le SQL contenu dans _log_portiques.sql_
## Structure
Votre base de données ne va contenir qu'une seule table appelée <pre>log_portiques</pre>. Cette table contient toutes les logs enregistrés au niveau des bornes de pointages disponible chez Vivetic.
Dans cette table, vous avez 12 champs qui sont:
- Name : le nom du collaborateur;
- id : identifiant unique du log, c'est une clé primaire;
- time : date et heure de chaque log;
- pin : numéro matricule du collaborateur;
- card_no : numéro de la carte RFID utilisée par le collaborateur pour pointer;
- device-id : identifiant de la portique;
- device_sn : numéro de série de la portique;
- device_name : nom de la portique;
- verified : utilisateur vérifié;
- state : entier;
- event_point_id : id de l'événement;
- event_point_name : nom de l'événement (entrée / sortie).
## Informations supplémentaires
En principe, un collaborateur (représenté par pin) possède une et une seule carte RFID (représentée par card_no). Mais il arrive qu'un collaborateur oublie la carte et doit donc utiliser une autre carte. Il est donc possible qu'un collaborateur puisse pointer avec des cartes différentes.
# Objets du test pratique
On vous demande de créer une application permettant de satisfaire deux fonctionnalités :
## Fonctionnalités
1. Afficher la liste des collaborateur (nom et matricule) ainsi que la ou les cartes qu'ils ont utilisé
C'est un affichage simple dans un tableau avec les en-têtes suivantes:
<pre>Nom - Matricule - Cartes</pre>
On ne doit avoir qu'un collaborateur par ligne, donc pas de doublon.
Si un collaborateur a utilisé plus d'une carte RFID, les afficher séparées par une virgule sans espace (,). Exemple:
<pre>
+--------------+-----------+-----------------------+
|Nom           | Matricule | Cartes                |
+--------------+-----------+-----------------------+
|RANDRIAMIHAJA | 1725      | 2572687440,2431438576 |
+--------------+-----------+-----------------------+
</pre>
2. Afficher la liste des logs, filtrés par date (donc on doit avoir la possibilité de sélectionner la date) et d'afficher les collaborateurs qui ont un ou des logs pour la date sélectionnée. Une ligne = un collaborateur. On ne doit pas avoir de doublon. Les informations à afficher sont (en tenant en compte que chaque collaborateur peut passer plus d'une fois sur les bornes de pointage) :
- Le nom du collaborateur
- Son matricule
- La ou les cartes utilisées ce jour-là
- L'heure de première entrée
- L'heure de dernière sortie
- Le nombre de pauses
- Le volume des pauses (en heure)

Soyez imaginatif pour la présentation de ces informations.
Faites attention sur le fait qu'il y a des collaborateurs qui entrent le soir pour sortir le matin. Ce qui veut dire que l'heure de première entrée peut ne pas se trouver sur la même date que l'heure de la dernière sortie.
## Technologie
Vous êtes totalement libre de choisir le stack technologique que vous voulez utiliser mais la seule recommandée est l'utilisation de MySQL pour le serveur de base de données.
## Livrable
Vous devez rendre pour ce test les documents / fichiers suivants:
- la documentation de votre application avec captures d'écran;
- les codes sources dans un fichier ZIP;
- les instructions d'installation.

Ces documents doivent être envoyés à l'adresse email suivante : thierry.randriantiana@vivetic-group.com
