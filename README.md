# DevFest_SOLUTEC_2023
Dépôt pour le projet de conception de jeu Unity type Snake pour la participation de Solutec au DevFest Nantes 2023.
---
---

# Réunion DevFest 2023 - *20/04/2023*

## Points évoqués
* [Décision du modèle](#1--décision-du-modèle)
* [Droits d'utilisation](#2--droits-dutilisation)
* [Identité graphique du jeu](#3--identité-graphique-du-jeu)
* [Éléments de Gameplay](#4--éléments-de-gameplay)
* [Gestion des scores et collecte de données](#5--gestion-des-scores-et-collecte-de-données)

***

## 1- Décision du modèle
Les deux idées disponibles étaient un **Temple Run-like** ou un **Snake-like**. La première option apparaît plus compliquée à mettre en place, et demandrait de passer beaucoup de temps sur Unity3D et de mettre en place beaucoup d'éléments. On se penche donc plus vers la seconde option, pour revisiter le Snake classique à la sauce **Tron-Solutec**.

***

## 2- Droits d'utilisation
Il faut vérifier les droits de commercialisation d'un produit développé sur Unity, pour se renseigner sur le besoin ou non d'obtenir une licence professionnelle.

En revanche, les **assets** communautaires achetés sur l'[Asset Store][1] sont directement utilisables à usage commercial, comme indiqué dans [cet article][2].

***

## 3- Identité graphique du jeu
La perspective principale du jeu serait une vue **top-down** classique pour un snake, avec une notion de profondeur pour intégrer de la 3D.

Le joueur contrôle donc une moto Tron, qu'il déplace à la façon d'un snake, sur une carte **hexagonale**

Les thème global du jeu s'inspire de l'univers graphique des films **Tron**, un thème avec des contrastes assez élevés entre teintes de couleurs vives néon et zones d'ombres. Il faut intégrer la **charte graphique Solutec** à ce thème pour le brander correctement.

Parmi les différents éléments de décors, comme les murs ou le fond du plateau, on pourra glisser des logos Solutec ou d'autres éléments permettant de rappeler l'entreprise. Des **assets** sont disponibles dans l'[Asset Store Unity][1]. On peut trouver des prefabs avec le mot-clé "[Tron][3]". Ces derniers sont modifiables et pourront être re-brand à la sauce **Solutec**.

Afin de renouveller la sensation de jeu et de dynamiser son rythme, on pourra s'inspirer des jeux de rythmes tels que **A Dance Of fire And Ice** qui utilisent des couleurs vives, des flashs de lumière, des jeux de mouvements de caméra, et une musique assez intense, pour garder l'attention du joueur et ajouter de la difficulté au jeu.

***

## 4- Éléments de gameplay
Le **but du jeu** est le même que pour snake, évoluer dans une  enceinte fermée en laissant une **trainée** statique derrière soi qui s'allonge au fil du temps. Toute **collision** avec cette trainée ou avec un élément du décor tel que les murs est fatale, et interrompt la partie.

Le jeu serait un jeu **solo**. Cela permet d'éviter le développement supplémentaire nécessaire pour le développement multijoueur, et tous les bugs que ça peut entraîner. Ne pas ajouter d'**ennemis** permet aussi de gagner du temps pour ne pas avoir à développer l'IA des adversaires.

Les **points** sont calculés en fonction de la durée de la partie du joueur (gain progressif de points juste en restant en vie).

Au fur et mesure de la partie, pour **limiter** la durée de cette dernière, le **rythme augmente**. La vitesse du joueur augmente, le nombre d'obstacles aussi, et les éléments perturbateurs (comme les flashs de lumière, les zooms saccadés, ou la musique) s'intensifient, pour augmenter la difficulté du jeu selon une pente assez raide pour que les parties soient rapides.


Des **collectibles** apparaissant progressivement et permettent au joueur de modifier le déroulement de sa partie. Ces **affixes** peuvent faciliter temporairement le déplacement du joueur (comme en réduisant sa vitesse, ou en paralysant le déplacement de la caméra) ; ou à l'inverse en ajoutant temporairement de la difficulté récompensée par un bonus sur le gain de points (ex: inversion des contrôles pour points x2).

### **Exemples d'affix**
| Effet | Contre-effet |
| ----- | ------------ |
| Vitesse réduite | Gain de points réduit |
| Vitesse accrue  | Gain de points doublé |
| Caméra fixée    | Gain de points réduit |
| Inversion de la rotation de caméra | +200 points |
| 5 secondes de flashs lumineux | +100 points par flash |
| etc |


### **Idées**
* Au bout d'un temps, la caméra peut se mettre à tourner continuellement pour perturber la perception des déplacements ;
* Des murs peuvent apparaître pour restreindre les déplacements ;
* Des projectiles ou des lasers peuvent apparaître pour essayer d'éliminer le joueur ;
* La trainée de lumière peut se mettre à disparaître : il advient alors au joueur de se souvenir de sa disposition pour ne pas se manger sa propre traînée ;
* Des tuiles peuvent tomber ou se désintégrer au fil du temps pour les rendre innaccessibles ;
* Faire apparaître un **disque mouvant** qui peut éliminer le joueur qui entre à son contact pour rappeler le film ;
* Rétrécissement de la carte ;
* On peut avoir un **pattern** comme le **"S"** du logo Solutec qui permet au joueur d'obtenir un bonus secret de points si celui-ci arrive à le reproduire dans ses mouvements ;

***


## 5- Gestion des scores et collecte de données
La collecte des données de l'utilisateur serait déguisée pour permettre au joueur d'obtenir son score et accéder au **classement global** à la fin du festival. Il reste à déterminer si cette inscription se fait **avant** ou **après** la participation. Dans le premier cas, on risque de repousser certains participants qui ne voudraient pas entrer leurs données, mais on garantit la collecte de données sur une participation. Dans le second cas, on s'expose à la possibilité que les joueurs refusent de s'enregistrer, par flemme ou par frustration, mais cette possibilité peut être réduite par le **gain de prix**.

Pour inciter les joueurs à participer, on peut utiliser l'effet de **"pensée de groupe"**. Si on propose des **"factions"** à rejoindre, les joueurs pourront alors ajouter les points qu'ils gagnent à chaque partie au score global de leur faction. Le **sentiment d'appartenance** créé pourra alors inciter les joueurs à fournir leurs coordonnées pour leur participation.

Le **gagnant** peut gagner un prix. On retenait l'idée des **cartes cadeaux** ou des **figurines pop Tron** pour ne pas demander un budget trop important.

[1]: https://assetstore.unity.com/ "Unity Asset Store"
[2]: https://support.unity.com/hc/en-us/articles/205623589-Can-I-use-assets-from-the-Asset-Store-in-my-commercial-game "Commercialisation des assets Unity"
[3]: https://assetstore.unity.com/?q=tron&orderBy=1&page=1 "Assets Tron dans le magasin"