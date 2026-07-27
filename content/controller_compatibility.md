+++
title = "Remapper des mauvais input d'un stick arcade sur Linux"
date = 2026-07-27
+++

J'ai décidé de migrer définitivement ma machine de jeu sur Linux (avec Endeavour, histoire d'avoir Arch Linux).

J'ai rencontré un problème : les inputs de mes sticks arcade ne sont pas tous reconnus et ceux qui sont reconnus sont mal mappés dans mes jeux. C'est super embettant : je n'ai que des sticks arcade puisque je joue majoritairement à des jeux de combats. Si mes sticks ne fonctionnent pas, aucun moyen de jouer correctement.

## Debug

Déjà, est-ce que mon stick existe ?

`dmesg | tail -50`

```
[ 9513.579292] input: ACRUX QanBa Arcade JoyStick 2028  V2.0 as /devices/pci0000:00/0000:00:14.0/usb1/1-1/1-1.4/1-1.4.4/1-1.4.4:1.0/0003:0F30:1102.0009/input/input35
[ 9513.579464] hid-generic 0003:0F30:1102.0009: input,hidraw4: USB HID v1.11 Gamepad [ACRUX QanBa Arcade JoyStick 2028  V2.0] on usb-0000:00:14.0-1.4.4/input0
```

Ok, mon stick existe. Il est bien détecté par le kernel.

On teste les inputs avec evtest.
Tous les inputs sont reconnus mais le mapping n'est pas correct.

Pour remapper j'ai utilisé jstest-git : [https://github.com/Grumbel/jstest-gtk](https://github.com/Grumbel/jstest-gtk)

Puis pour sauvegarder le profil créé : jscal-store de joyutils. Pour le doc, cf [https://man.archlinux.org/man/extra/joyutils/jscal-store.1.en](https://man.archlinux.org/man/extra/joyutils/jscal-store.1.en)
