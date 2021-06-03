## SSTIC Challenge 2021

This repository contains the minimum instructions for deploying the remote part of the SSTIC challenge 2021.

### Step 1

Download the challenge archive on the [challenge page](https://www.sstic.org/2021/challenge/) ([en](https://www.sstic.org/2021/challenge_en/)).

### Step 2

Command line to add the RW rights to the file on the Desktop of the user, only needed to be executed once per machine :

```
ICACLS "C:\Users" /grant "*S-1-15-2-2:(R,RX)"
ICACLS "C:\Users\Challenge" /grant "*S-1-15-2-2:(R,RX)"
ICACLS "C:\Users\Challenge\Desktop" /grant "*S-1-15-2-2:(R,RX)"
ICACLS "C:\Users\Challenge\Desktop\DRM.zip" /grant "*S-1-15-2-2:(R,RX)"
```

Command line to run AppJaillauncher :

```
 C:\Tools\appjaillauncher-rs.exe run --foldermazes "C:\users\challenge\\mazes" "C:\Tools\A..Mazing.exe"
```

"C:\Tools\SSTIC.exe" argument is the binary that will be executed when a challenger connects to the port where appjaillauncher listen.

`Foldermazes` parameter is the folder that will contain the private folders.
It is needed that this folder exists before running appjaillauncher.

More parameters can be defined, as the port where the program listens, the job limitations (time, memory, number of processes), etc.

During the competition, this command was launched with Powershell.

The archive DRM.zip should be place on the user Desktop. The player should retrieve the archive with a remote exploit.

### Step 3 to 5

Steps 3 to 5 can be deployed on a Linux machine using docker and docker-compose.

```bash
$ cd step-345
$ docker-compose up
```

## References

[challenge page](https://www.sstic.org/2021/challenge/) ([en](https://www.sstic.org/2021/challenge_en/))

git repositories of [step 2](https://github.com/challengeSSTIC2021/Step2_challenge) and [AppJailLauncher](https://github.com/challengeSSTIC2021/appjaillauncher-rs)

git repository of [step 3](https://github.com/challengeSSTIC2021/wb)

git repositories of [step 4 and 5](https://github.com/challengeSSTIC2021/service) and [qemu](https://github.com/challengeSSTIC2021/qemu)
