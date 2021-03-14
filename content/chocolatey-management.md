---
title: 'Chocolatey management'
date: Thu, 06 Feb 2020 21:42:13 +0000
draft: false
tags: ['Dev machine']
---

Chocolatey est un **gestionnaire de paquets** pour Windows. C’est un programme qui vous permet d’installer et de désinstaller des applications à la vitesse de l’éclair en utilisant la commande `choco`. Son point fort : il est capable de mettre à jour l’ensemble des applications installées sur votre système avec une **seule commande** !

See [https://github.com/chocolatey/choco/wiki/CommandsInstall#options-and-switches](https://github.com/chocolatey/choco/wiki/CommandsInstall#options-and-switches)

Source de cet article :

From [https://lecrabeinfo.net/chocolatey-gestionnaire-paquets-windows.html](https://lecrabeinfo.net/chocolatey-gestionnaire-paquets-windows.html)

Pour mettre à jour des logiciels avec Chocolatey :

1.  Vérifiez si des mises à jour sont disponibles :  
    `choco outdated`
2.  Pour **mettre à jour un seul paquet** :  
    `choco upgrade f.lux -y`[](https://lecrabeinfo.net/app/uploads/2017/08/chocolatey-gestionnaire-paquets-windows-installer-logiciels-applications-ligne-commande-mise-a-jour-logiciel-59a2f65da2fad.png)
3.  Pour mettre à jour **tous les paquets** du système :  
    `choco upgrade all -y`

Pour lister tous les paquets installés avec Chocolatey :

```
choco list -l
```

### Liste des commandes de Chocolatey

Voici [toutes les commandes](https://chocolatey.org/docs/commands-reference) disponibles avec Chocolatey :

*   **list** ou **search** – liste les paquets distants ou locaux
*   **info** – affiche les informations du paquet. Similaire à : `choco search pkgname --exact --verbose`
*   **install** – installe des paquets
*   **pin** – supprime les mises à jour du paquet
*   **outdated** – affiche les paquets obsolètes. Similaire à `choco upgrade all --noop`
*   **upgrade** – met à jour des paquets
*   **uninstall** – désinstalle un paquet
*   etc...