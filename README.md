## Challenge SSTIC 2021

Ce dépôt contient les instructions minimales pour déployer le partie remote du challenge SSTIC 2021

### Étape 1

Télécharger l'archive disponible sur la [page du challenge](https://www.sstic.org/2021/challenge/)

### Étape 2

Lors de l'étape 2, il vous faudra lancer le binaire trouvé lors de l'étape 1 sur une machine windows. Sur cette machine
windows, déposé également l'archive ``step-2/DRM.zip`` sur le bureau de l'utilisateur.

L'étape 2 consiste à exploiter ce binaire pour extraire cette archive de la machine windows.

### Étapes 3 à 5

Les étapes 3 à 5 peuvent être déployer sur une machine linux en utilisant docker et docker-compose.

```bash
$ cd step-345
$ docker-compose up
```

## Référence

[page du challenge 2021](https://www.sstic.org/2021/challenge/)

dépôts de l'[étape 2](https://github.com/challengeSSTIC2021/Step2_challenge) et de [AppJailLauncher](https://github.com/challengeSSTIC2021/appjaillauncher-rs)

dépôt de l'[étape 3](https://github.com/challengeSSTIC2021/wb)

dépôts de l'[étape 4 et 5](https://github.com/challengeSSTIC2021/service) et de [qemu](https://github.com/challengeSSTIC2021/qemu)
