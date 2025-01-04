![resim](https://github.com/user-attachments/assets/26646db3-b278-453d-9910-cfab1619b1e7)


# HyperSpaceAI Installation Guide

## 3 options de configuration différentes

- Browser 
- MAC / Windows 
- CLI ( Server ) 

<img src="https://github.com/user-attachments/assets/bf91e6b6-e379-4684-b11b-84106c0f2e98" alt="to0x:)" width="500">

## 1 / WEB BROWSER :

- Link : https://node.hyper.space/

#### CCliquez sur le bouton rouge pour l'activer.

![resim](https://github.com/user-attachments/assets/4a763da7-40fb-4eca-87d0-a1452fbbee37)

## Après l'activation, vérifiez les points et assurez-vous qu'ils sont actifs.

![resim](https://github.com/user-attachments/assets/af031538-ec03-4444-8ef5-5d76d06487ff)


![resim](https://github.com/user-attachments/assets/ced0b28d-28ec-438f-9db2-e8675826b39c)


## Sauvegardons ensuite la clé privée qu'il crée pour nous. Ne la supprimez pas.

![resim](https://github.com/user-attachments/assets/496adc93-aff6-4bc5-bb35-66971a550592)

![resim](https://github.com/user-attachments/assets/4a0cfae8-d9e2-4739-8fd9-f4f71bf42255)


## Information importante : Les nœuds se figent et se cassent - le travail s'arrête, la partie sur laquelle on appuie et qui devient verte devient rouge. Vérifiez de temps en temps.


# 2 / Windows :

- Link : https://hyper.space/

![resim](https://github.com/user-attachments/assets/32f93027-4da1-4b66-8252-017e414694d6)

- GPU ( Carte d'affichage ) : Nvidia
- CPU ( Processeur ) : x86 Intel

#### Cliquez sur le fichier téléchargé et installez-le.

![resim](https://github.com/user-attachments/assets/640f27d6-04ee-4254-b01d-7633531915f0)


## Travailler : 

![resim](https://github.com/user-attachments/assets/2da9ec02-8559-4bd0-b35e-25ab38cf5907)

#### Conservez une copie de la clé afin de ne pas perdre vos arguments.

- Chemin d'accès au fichier de la clé C:\Users\youruser\AppData\Roaming\hyperspace

![resim](https://github.com/user-attachments/assets/e1c1cc6e-f432-4b7d-98b7-c080d27cc7a2)



# Linux VPS : 

- Main Setup : https://github.com/hyperspaceai/aios-cli?tab=readme-ov-file

#### Exécutez la commande suivante pour mettre à jour et mettre à niveau les paquets du système :

```bash
sudo apt update -y && sudo apt upgrade -y
```
## 2. Installez les paquets nécessaires :

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

## Télécharger ;

```bash
curl https://download.hyper.space/api/install | bash
```
```bash
source /root/.bashrc
```

- Beispiel für einen Download :

![resim](https://github.com/user-attachments/assets/998ec182-9893-4153-bae3-3a446fa6a298)


## Set Information : 

- Obtenons une clé privée comme celle que nous avons obtenue dans la section Navigateur.

![resim](https://github.com/user-attachments/assets/0a975077-26f0-4bd1-8ed6-5930d74d3de2)


## Écran ;

```bash
screen -S hyper
```

## Lançons :

```bash
aios-cli start
```
 
#### On peut sortir de la page avec CTRL A + D. 
- Si l'on veut entrer dans la page précédente : screen -r hyper


#### 1. Importons la clé dans le nœud :

```bash
nano my.pem
```

![resim](https://github.com/user-attachments/assets/70d5ae23-feb1-46df-9a79-16bb653fdff7)

- Enregistrez la clé que vous avez obtenue du navigateur en cliquant avec le bouton droit de la souris. (J'ai obtenu une nouvelle clé à partir d'un autre navigateur pour éviter les conflits).

- CTRL X Y Enter. Save


###### Importons-le :

```bash
aios-cli hive import-keys ./my.pem
```

![resim](https://github.com/user-attachments/assets/49c842ef-710d-4e1d-aa4a-455a476b664c)


#### Login : 


```bash
aios-cli hive login
```

####  Autres étapes :

```bash
aios-cli models add hf:TheBloke/phi-2-GGUF:phi-2.Q4_K_M.gguf
```

![resim](https://github.com/user-attachments/assets/8266b70e-8add-437b-9928-b686e03da32c)


## Points

- Pour obtenir un score, vous devez entrer un niveau (actuellement de 1 à 5, du meilleur au pire).

- Chaque niveau comporte certains modèles requis et certaines quantités de mémoire GPU que vous devez télécharger et enregistrer sur le réseau :

    1 : 30GB
    2 : 20GB
    3 : 8GB
    4 : 4GB
    5 : 2GB

## Vérification du score :

```bash
aios-cli hive points
```

![resim](https://github.com/user-attachments/assets/bd5fede7-8b0b-4333-84d7-17dc54ac5346)


- Commandes utiles :

```bash
# For fast connection if the node is stopped : 
aios-cli start --connect
# Update : 
aios-cli version
# Stop : 
aios-cli kill
```

## Uninstall : 

```bash
curl https://download.hyper.space/api/uninstall | bash
```

## Quelques informations complémentaires :

```bash
# To see which models are needed : 
aios-cli hive select-tier 5
# Download a required model
aios-cli models add hf:TheBloke/phi-2-GGUF:phi-2.Q4_K_M.gguf
# Import your private key - create a my.pem file using nano my.pem and enter a private key (You can import a private key from the Browser version)
aios-cli hive import-keys ./my.pem
# Set these switches as preferred for this session
aios-cli hive login
# Make sure the model is registered
aios-cli hive connect
aios-cli hive select-tier 5
```


- Si vous faites screen -r hyper, les journaux moyens ressembleront à ceci :

![resim](https://github.com/user-attachments/assets/0e07d3da-e1a9-4b38-b01d-7e8c2bfd8bc9)

