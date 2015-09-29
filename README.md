#Analyse projet Green IT
##Contexte du projet
Dans le cadre de ce projet, nous devont calculer et restituer la consommation énergétique d'un raspberry pi.
Suite à différentes recherches, nous avons choisi un projet simple, bas niveau, qui nous permettrais facilement de comprendre le fonctionnement du matériel pour ensuite passer à des logiciels plus conséquent comme PowerAPI ou PowerTop.

Le projet est simple, il consiste en l'allumage d'une diode et le calcul de la consommation de cette dernière en connaissant sa consommation de base. Ainsi le système va compter le nombre de clignotements de la diode s'étant produit sur une durée.
Par exemple : si notre diode s'est allumée 10 fois sur une heure, nous avons consommé 10 * 1 Watt/heure.

##Power API
PowerAPI est une librairie offrant une API permettant de mesurer la consommation énergétique d'un processus système. Le but étant de pouvoir répondr aux questions du type : quelle est la consommation énergétique de mon application/processus ? L'intérêt de PowerAPI repose à la fois sur son architecture et sa manière de mesurer la consommation énergétique : Le calcul se base sur la consommation énergétique des composants matériels utilisés par le processus (CPU, mémoire, disqueけ) et utilise pour cela des formules énergétiques, sans effort matériel, sans avoir besoin de wattmètre ou d'autres outils matériels de mesure/calibration pour calculer la consommation énergétique.

Son architecture est modulaire, où chaque module représente une unité de calcul propre (capteur CPU, formule CPU), permettant à l'utilisateur d'adapter la librairie à sa requête. L'utilisateur compose alors la librairie en ajoutant les modules dont il a besoin, évitant ainsi les surcoûts inutiles

##PowerTop
PowerTOP est un utilitaire pour Linux développé en 2007 par Intel. Il permet de diminuer la consommation électrique des PC portables sous Linux grâce à une analyse détaillée de cette consommation. PowerTOP affiche le pourcentage du temps passé dans les différents modes de consommation des processeurs ainsi qu’une liste des programmes qui réveillent le plus souvent le processeur.

Grâce à cette analyse, l’utilisateur peut alors modifier certains paramétrages pour augmenter l’autonomie de sa batterie. PowerTOP propose lui-même des améliorations pour diminuer les demandes inutiles aux processeurs.

##Matériel requis
Pour réaliser ce projet nous avons des besoins matériel de base :
- RaspBerry Pi (modèle B)
- Une plaque d'essai
- Une cellule photovoltaique
- Un condensateur 1 microF 50 V
- 3 Wires jumper male/femelle

Le port d'alimentation 3,3 V n°1 du GPIO (en haut à gauche) relié à la cellule photo-électrique.
- L'autre patte de la cellule photo-électrique est reliée à la borne positive du condensateur.
- La borne négative du condensateur est reliée au port n° 6 qui est la masse.
- La borne positive du condensateur est reliée au port n°12 du GPIO qui correspond au canal 1.


