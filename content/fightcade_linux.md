+++
title = "Fightcade sur Linux"
date = 2026-07-27
+++

L'émulateur de Fightcade utilise Wine et Wine Mono. Il faut s'assurer de les avoir installés avant toute chose.

```
pacman -S wine wine-mono
```

La solution la plus simple est d'installer : [https://www.fightcade.com/download/linux](https://www.fightcade.com/download/linux)

La version de l'AUR n'est pas à jour (en date du 27 juillet 2026 - il faudrait proposer une update). La version sur les repo de Flatpak correspond à celle sur le site. Mais elle nécessite d'installer ses propres dépendances.

Commentaire intéressant : [https://aur.archlinux.org/packages/fightcade2-bin#comment-967076](https://aur.archlinux.org/packages/fightcade2-bin#comment-967076)


```
pacman -S winetricks
winetricks dxvk
```

D'après Wikipédia : [DXVK](https://en.wikipedia.org/wiki/DXVK) is an open-source translation layer which converts Direct3D 8/9/10/11 calls to Vulkan.
