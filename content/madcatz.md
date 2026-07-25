+++
title = "Dual Mod DB15 USB Madcatz TE2+"
date = 2025-11-07
+++

En voyant les prix des [adaptateurs de chez Brook](https://www.smallcab.net/brook-super-converter-ps3ps4-adapter-p-1903.html) pour connecter des sticks arcades ou des manettes PS3/PS4 sur Neo Geo, je me suis dis que j'allais plutôt modder mon stick Madcatz TE2+ pour lui rajouter un câble DB15.

Besoin de pas grand chose :

- fils électrique récup dans un vieux câble RJ45 qui trainait.
- câble rallonge DB15 choppé pour 3€ sur [Aliexpress](https://fr.aliexpress.com/item/1005006479569847.html).
- Un tournevis plat
- Un tournevis cruciforme

Aucune soudure nécessaire. J'ai mis des dominos pour certains boutons.

Le TE2+ est super pratique, on peut l'ouvrir avec une simple pression d'un bouton. Tous les boutons sont accessibles comme ça à l'exception des boutons start, select, derrière un cache en plastique en haut à droite.

Pour accéder à la PCB, il faut dévisser les deux vis qui maintiennent un cache en plastique noir. J'ai totalement retiré le cache pour ma part. J'aurais pu faire quelque chose de plus propre en essayant de cacher tous les câbles et en passant par la fente du cache, mais au cas où il faut changer plus tard, je n'ai pas pris le temps de le faire. (C'est une MVP).

Le gros avantage du stick Madcatz est que la masse est commune pour tous les boutons sur la PCB.

Si la masse n'est pas commune, il faut relier toutes les masses des boutons et du joystick ensemble, et s'assurer qu'il n'y a pas de court-circuit sur la PCB lorsque l'USB est branché.

Sur le câble rallonge DB15, il y a 15 fils.
Pas de documentation avec le câble donc pas de moyen de savoir quel couleur correspond à quel input.

Mettons le slot en mode button check et sortons le stylo et le papier pour noter quel couleur correspond à pin sur le DB15.
Pour mettre le slot en button check, il faut mettre le premier dipswitch sur la position 1. Avec une manette fonctionnelle branchée, on peut sélectionner le premier menu "Hardware Test". Puis appuyer sur Start jusqu'à arriver à l'écran Button Check.

0 -> pas d'input

1 -> présence d'input (pression sur un bouton ou direction sur le joystick).

On branche le câble rallonge à la Neo Geo ou au Supergun et maintenant plusieurs solutions :
On peut faire contact entre les fils pour déterminer quel fil correspond à quoi.
Lorsque tous les fils font contact, on a 1 à tous les input sur le menu.
On enlève un contact, on a un input qui disparait à l'écran, on note à quoi ça correspond.

Pour ma part, j'ai d'abord déterminé la masse. J'ai connecté le fil de masse à une cosse d'un bouton sanwa, et je teste tous les autres fils à un par un en notant au fur et à mesure la correspondance. Il suffit de connecter les fils, et voir si le 1 s'affiche ou pas.

Sur ma table de mapping, j'ai essayé de garder les directions ensemble et les boutons dans l'ordre. Ca sera plus simple pour la suite.

<img src="/assets/images/madcatz/mapping.png" alt="Mapping" height="400">

Maintenant, on connecte tout.

On retire la nappe qui connecte les boutons à la PCB.
Il y a deux rangés. Sur la rangé du haut, repère la couleur du bouton qu'on veut mapper, et j'ai inséré dans le connecteur le fil du câble DB15 correspondant.
On fait ça pour tous les boutons qu'on veut mapper puis on remet le connecteur sur la PCB (c'est aussi simple à enlever et remettre qu'une barrette de RAM).

Pareil pour le joystick.
Vu que la masse est commune, j'ai choisi de connecter le fil de masse du câble à la masse du joystick.

<img src="/assets/images/madcatz/jlfsanwa.png" alt="Wiring JLF Sanwa" height="400">

Ensuite pour Start et Select c'est pareil, ce sont les connecteurs respectivement gris et blanc, même technique, le fil sur le pin dans le connecteur sur la PCB.

Passage du cable :

Avec une perceuse j'ai fait un petit trou à l'avant du joystick (donc pas à l'arrière où il y a les boutons start select), vraiment à l'avant, juste à côté du bouton pour ouvrir le stick.
Puis, j'ai agrandi le trou juste pour laisser de la place au cable.

J'ai choisi cette solution avec un câble parce qu'il n'y a pas trop de place sur ce stick pour mettre un connecteur DB15 à même la carcasse. Le câble DB15 n'est donc pas détachable chez moi.

Est-ce que c'est beau ? Disons que c'est pas moche. Mais en tout cas, ça marche et c'est pratique.

Evolution : mettre un stop-câble pour fixer une limite de longueur du câble en dehors du stick.
Egalement, je pense imprimer des passes câble en 3D. Pour l'instant j'ai mis du gaffer à l'intérieur, afin que je puisse le tester rapidos et faire quelques parties avant de prendre le temps de modéliser une pièce en 3D.

Sur le madcatz il y a deux rangées de 4 boutons.

J'ai choisi le mapping :
```
A C / /
B D / /
```

Les jeux Neo Geo, c'est 4 boutons. Pas besoin de plus.


MAJ - 25/07/2026

Ordre des pins sur le DB15 mâle :
1 - GND
2 - Kick 2 (pour jeux 6 boutons) / Bouton 6
3 - Select
4 - D
5 - B
6 - Droite
7 - Bas
8 - +5V
9 - Non branché
10 - Kick 1 (Pour jeux 6 boutons) / Bouton 5
11 - Start
12 - C
13 - A
14 - Gauche  
15 - Haut

<img src="/assets/images/madcatz/pcb.jpg" alt="PCB Madcatz TE2+" width="400">
<img src="/assets/images/madcatz/pcb2.jpg" alt="PCB Madcatz TE2+ 2" width="400">
<img src="/assets/images/madcatz/cosse.jpg" alt="Cosse Madcatz TE2+" width="400">
<img src="/assets/images/madcatz/stick.jpg" alt="Full Madcatz TE2+ DB15" width="400">