# pythonE3FI

# USER GUIDE : 
Voici le lien du projet sur github : https://github.com/terencebarbotin/Python_Data_VIZ_Terence_Barbotin

* 1 : Télécharger le projet en format ZIP
* 2 : Décompresser le fichier ZIP
* 3 : Se rendre via un terminal (si on n'utilise pas VS Code) dans le dossier décompressé 
* 4 : Lancer le projet via : $ python3 main.py

Cela va lancer le projet. On va voir 244 lignes qui se print, c'est la récupération des données météo via API. 
Vous récupérerez ensuite un lien qui vous permettra de lancer le projet en local, sur chrome notamment. 
Vous pouvez accéder à cet URL, et le dashboard se lance. Le processus peut prendre quelques minutes selon votre connexion. 

Une fois cela fait, vous verrez un dashboard web avec un titre, un paragraphe, et 3 graphiques à la suite. 

L'ensemble des packages à installer peut être réalisé par la commande : $ python3 -m pip3 install -r requirements.txt

L'ensemble des datasets peut être récupéré par la commande : $ python3 get_data.py. Ils seront enregistrés dans un dossier 'downloads' au sein du répertoire du projet.

# RAPPORT D'ANALYSE : 

Ces analyses montrent une répartition des températures inégales, mais surtout une croissance des températures moyennes pour les pays issus de l'hémisphère Nord. On peut constater que plus de (44,7 + 17,6 + 15, 4 =) 77,7% des tempèratures moyennes minimales à la surface des zonnes habitées à l'année sont au dessus de 15°C.

# DEVELOPPER GUIDE : 

Ce projet comporte différents fichiers : 
* Un 'main.py' qui créé et lance le dashboard, et construit l'histogramme. 
* Un 'piechart.py' qui créé le graphique pie chart.
* Un 'carte_monde.py' qui créé la carte interactive du monde avec les températures en temps réel. Elle utilise une API météo spécifique à l'aide de 'countries.csv' (environ 240 données) et de countries.geojson
* Un 'fonctions.py' qui peut être utilisé lors de la création de fonctions annexes. 
* Un 'data.py', qui est allé récupérer via API World Weather Online (pas la même utilisée dans 'carte_monde.py', celle-ci retourne des données plus complètes) les températures moyennes minimales mensuelles des 12 derniers mois de toutes les villes contenues dans 'worldcities.csv', soit environ 41 000 données, et en a calculé la moyenne anuelle. Ces données ont ensuite été stockées localement dans le fichier 'avg_min_temp_world.csv' afin de ne pas avoir à effectuer les 41 000 requêtes à la création de chaque dashboard. 
* Un 'avg_min_temp_world.py' qui va retourner un tableau contenant toutes les valeurs de 'avg_min_temp_world.csv'.
* Un "GPS_non_formatees.py' qui m'a aidé à extraire les coordonnées GPS de 'worldcities.csv' dans un 'GPS.csv'.
* Un "GPS_formatees.py' qui m'a aidé à formaté les coordonnées GPS de 'GPS.csv' dans 'GPS2.csv'.

# NB : 

L'histogramme n'est pas correct visuellement, je m'en rends compte.
Vous pouvez remarquer qu'au début de 'main.py', je trie mon tableau de données afin que l'histogramme prenne en compte des valeurs croissantes et puisse adapter sa forme à celles-ci. Jusqu'ici, cela marchait très bien jusqu'à ce que je mette le dossier sur git et que je tente de le télécharger pour mettre en situation votre test. Depuis, les valeurs restent dans un ordre aléatoire et je n'ai aps réussi à en rechanger la forme dans le temps imparti, je m'en excuse. 






