## Challenge SSTIC 2021

Ce dépôt contient les instructions minimales pour déployer le partie remote du challenge SSTIC 2021

### Étape 1

Télécharger l'archive disponible sur la [page du challenge](https://www.sstic.org/2021/challenge/)

### Étape 2

Lors de l'étape 2, il vous faudra lancer le binaire trouvé lors de l'étape 1 sur une machine windows. Sur cette machine
windows, déposé également l'archive ``step-2/DRM.zip`` sur le bureau de l'utilisateur.

L'étape 2 consiste à exploiter ce binaire pour extraire cette archive de la machine windows.


Command line to add the RW rights to the file on the Desktop of the user, only needed to be executed once per machine :

```
ICACLS "C:\Users" /grant "*S-1-15-2-2:(R,RX)"
ICACLS "C:\Users\Challenge" /grant "*S-1-15-2-2:(R,RX)"
ICACLS "C:\Users\Challenge\Desktop" /grant "*S-1-15-2-2:(R,RX)"
ICACLS "C:\Users\Challenge\Desktop\DRM.zip" /grant "*S-1-15-2-2:(R,RX)"
```



Ligne de commande pour éxécuter le AppJaillauncher : 

```
 C:\Tools\appjaillauncher-rs.exe run --foldermazes "C:\users\challenge\\mazes" "C:\Tools\SSTIC.exe"
```

"C:\Tools\SSTIC.exe" argument is the binary that will be executed when a challenger connects to the port where appjaillauncher listen.

`Foldermazes` parameter is the folder that will contain the private folders.
It is needed that this folder exists before running appjaillauncher.

More parameters can be defined, as the port where the program listens, the job limitations (time, memory, number of processes), etc.

During the competition, this command was launched with Powershell.


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
