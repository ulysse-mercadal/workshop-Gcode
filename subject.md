## Workshop Gcode
## ulysse mercadal | matthieu sacquet




## intro 



Qu'est-ce que le Gcode? 
Le G-code est un langage de programmation utilisé pour contrôler les machines à commande numérique (CNC), telles que les fraiseuses, des imprimantes 3D, tout ce qui transforme de la matière, et qui possède au moins trois moteurs pour les axes x y z. c’est le langage le plus utilisé dans cette industrie.
Quelle est sa syntaxe ? 
Le G-code est composé de commandes qui indiquent à la machine comment se déplacer, sur les axes x y z, un peu comme turtle en python… Mais avec quelques options supplémentaires permettant le perçage, la découpe ou l'usinage, et d'autres actions nécessaires à la fabrication de pièces. Ces fameuses commandes commencent par une lettre, souvent X (d'où le nom du langage), suivie d’un numéro, par exemple g00 pour bouger, g02 pour faire un arc de cercle, etc. De plus, les commandes sont à la ligne.
Pourquoi s’embêter a écrit du code alors que des slicers le font aussi très bien ? 
Les slicers (les logiciels qui transforment des objets 3d en suite de déplacement grâce à des algos de pathfinding), crée un g code efficace, mais pas optimal, ils traitent les pièces par strates, impossibles de faire en impression 3d une extrusion en diagonale, ce qui peut parfois être très utile. Et plus de permettre de faire des tests de calibration sur une machine. Pour nous, faire du code permet surtout de comprendre le fonctionnement de ces machines.




## outils utilisés




Pour éditer et visualiser le code ecrit: https://ncviewer.com/

liste des gcode basiques :
```gcode
G00  ;déplacement rapide
G01  ;déplacement simple en suivant un parametre de vitesse
G02  ;rotation dans le sens trigo
G03  ;rotation dans le sens anti-trigo
G04  ;attendre
G21  ;passer en mode métrique 
G91  ;passer en mode incrémentation (indispensable pour eviter les prises de tetes)
G51  ;scaling
```




## exercices




**1- déplacement en carré.**

Faites bouger la tête sur un carré de 10 cm x 10 cm


**2- premiers arrondis**

Ajoutez des arrondis de 3 cm de diam entre à tous les angles du carré crée


**3- cercle**

Créez un cercle simple.


**4- scaling**

Faites des cercles concentriques


**5- pièce technique**

Recréez un code pour découper dans une plaque de métal de 3 cm une pièce tenue selon ce schéma : 


**6- variables**

Déclarer deux variables locales : une égale a la position actuelle, une autre à la position x désirée, faire une boucle pour se déplacer de 1 cm sur l’axe des x jusqu’à arriver à la coordonnée d'arrivée.


**7- remplissage**

Admettons que nous contrôlons une imprimante 3d équipée d’une buse de 4 mm, le fil sorti de la tête d’impression fera le même diamètre, remplir un cercle de 3 cm de diamètre de matière. 
*Faites des hachures !*


**8- premier Gcode de calibration**

Dans le même cas que l'exercice dernier, continuer le code pour créer une montée droite depuis le centre du cercle de 5 cm, puis 10 cercles concentriques devant tenir sur cette même montée, afin de créer un cône inversé au bout d’un support simple.


**|——————————————————————————————————|**                                                      
**|/!\ à partir de maintenant, le code ne sera plus vérifiable sur ncviewer|**   
**|——————————————————————————————————|**


**9- rendre le Gcode utilisable**

Dans la suite du dernier exercice, gérez les paramètres de l’imprimante pour créer une initialisation de la machine, la température du bed doit être à 60, l’extruder a 190. La tête d’impression positionnée à coordonnées x 10 y 10. Tous les ventilateurs à 100 %.


**10- James bond**

Dans la suite du dernier exercice, après l'exécution du code, jouer un son, afficher un ratio à l'écran, puis supprimer le contenu du support de donnée, et éteindre la machine.


**11- alertes**

Dans le cas où le filament serait fini, faire 42 bips, se rétracter de 3 cm, et mettre la température de reprise à 200

**12- fini ?**

Faites en sorte de faire un quadrillage de 9 trous, en utilisant des conditions et des boucles (goto), et les variables suivantes :
```gcode
#100 = 0.100; depth of each hole
#101 = 1.000; X-axis increment 
#102 = 0.500; Y-axis increment
#103 = 0.000; X-axis pointer initialized to the origin
#104 = 0.000; Y-axis pointer initialized to the origin
#105 = 2.000; distance limit along the X-axis 
#106 = 1.234; distance limit along the Y-axis 
#107 = 0.050; safe plane
#108 = 5.0; drilling feed rate
```
*bonne chance !*
