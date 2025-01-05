![resim](https://github.com/user-attachments/assets/26646db3-b278-453d-9910-cfab1619b1e7)


# HyperSpaceAI Installationsanleitung

## 3 verschiedene Setup-Optionen

- Browser 
- MAC / Windows 
- CLI ( Server ) 

<img src="https://github.com/user-attachments/assets/bf91e6b6-e379-4684-b11b-84106c0f2e98" alt="to0x:)" width="500">

## 1 / WEB BROWSER :

- Link : https://node.hyper.space/

#### Klicken Sie auf den roten Button und aktivieren Sie ihn.

![resim](https://github.com/user-attachments/assets/4a763da7-40fb-4eca-87d0-a1452fbbee37)

## Überprüfen Sie nach der Aktivierung die Punkte und vergewissern Sie sich, dass sie aktiv sind.

![resim](https://github.com/user-attachments/assets/af031538-ec03-4444-8ef5-5d76d06487ff)


![resim](https://github.com/user-attachments/assets/ced0b28d-28ec-438f-9db2-e8675826b39c)


## Dann speichern wir den privaten Schlüssel, den er für uns erstellt. Löschen Sie ihn nicht.

![resim](https://github.com/user-attachments/assets/496adc93-aff6-4bc5-bb35-66971a550592)

![resim](https://github.com/user-attachments/assets/4a0cfae8-d9e2-4739-8fd9-f4f71bf42255)


## Wichtige Information: Der Knoten friert ein und bricht ab - die Arbeit stoppt, der Teil, den wir auf den Knopf drücken und grün machen, wird rot. Überprüfen Sie von Zeit zu Zeit.


# 2 / Windows :

- Link : https://hyper.space/

![resim](https://github.com/user-attachments/assets/32f93027-4da1-4b66-8252-017e414694d6)

- GPU ( Karte anzeigen ) : Nvidia
- CPU ( Prozessor ) : x86 Intel

#### Klicken Sie auf die heruntergeladene Datei und installieren Sie sie.

![resim](https://github.com/user-attachments/assets/640f27d6-04ee-4254-b01d-7633531915f0)


## Arbeiten : 

![resim](https://github.com/user-attachments/assets/2da9ec02-8559-4bd0-b35e-25ab38cf5907)

#### Bewahren Sie eine Kopie des Schlüssels auf, damit Ihre Punkte nicht verloren gehen.

- Dateipfad des Schlüssels C:\Users\youruser\AppData\Roaming\hyperspace

![resim](https://github.com/user-attachments/assets/e1c1cc6e-f432-4b7d-98b7-c080d27cc7a2)



# Linux VPS : 

- Main Setup : https://github.com/hyperspaceai/aios-cli?tab=readme-ov-file

#### Führen Sie den folgenden Befehl aus, um Systempakete zu aktualisieren und zu aktualisieren:

```bash
sudo apt update -y && sudo apt upgrade -y
```
## 2. Installieren Sie die erforderlichen Pakete:

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

## Herunterladen ; 

```bash
curl https://download.hyper.space/api/install | bash
```
```bash
source /root/.bashrc
```

- Muster-Download : 

![resim](https://github.com/user-attachments/assets/998ec182-9893-4153-bae3-3a446fa6a298)


## Set Information  : 

- Besorgen wir uns einen privaten Schlüssel, wie wir ihn im Abschnitt Browser erhalten haben.

![resim](https://github.com/user-attachments/assets/0a975077-26f0-4bd1-8ed6-5930d74d3de2)


## Bildschirm;

```bash
screen -S hyper
```

## Starten wir:

```bash
aios-cli start
```
 
#### Wir können die Seite mit CTRL A + D verlassen. 
- Wenn Sie die letzte Seite aufrufen wollen: screen -r hyper


#### 1. Let's Import Key to Node : 

```bash
nano my.pem
```

![resim](https://github.com/user-attachments/assets/70d5ae23-feb1-46df-9a79-16bb653fdff7)

- Speichern Sie den Schlüssel, den Sie vom Browser erhalten haben, mit einem Rechtsklick. (Ich habe einen neuen Schlüssel von einem anderen Browser erhalten, um Konflikte zu vermeiden).

- CTRL X Y Enter. Save


###### Lassen Sie es uns importieren:

```bash
aios-cli hive import-keys ./my.pem
```

![resim](https://github.com/user-attachments/assets/49c842ef-710d-4e1d-aa4a-455a476b664c)


#### Anmeldung:


```bash
aios-cli hive login
```

####  Andere Stadien :

```bash
aios-cli models add hf:TheBloke/phi-2-GGUF:phi-2.Q4_K_M.gguf
```

```bash
aios-cli hive select-tier 5
```

```bash
aios-cli hive connect
```

```bash
aios-cli hive select-tier 5
```

![resim](https://github.com/user-attachments/assets/8266b70e-8add-437b-9928-b686e03da32c)


## Punkte

- Um eine Punktzahl zu erhalten, müssen Sie eine Stufe eingeben (derzeit von 1-5, von der besten bis zur schlechtesten).

- Für jede Ebene sind bestimmte Modelle und eine bestimmte Menge an GPU-Speicher erforderlich, die Sie herunterladen und im Netzwerk speichern müssen:

    1 : 30GB
    2 : 20GB
    3 : 8GB
    4 : 4GB
    5 : 2GB

## Puan Kontrolü : 

```bash
aios-cli hive points
```

![resim](https://github.com/user-attachments/assets/bd5fede7-8b0b-4333-84d7-17dc54ac5346)


- Nützliche Befehle :

```bash
# For fast connection if the node is stopped : 
aios-cli start --connect
# Update : 
aios-cli version
# Stop : 
aios-cli kill
```

## Deinstallieren: 

```bash
curl https://download.hyper.space/api/uninstall | bash
```

## Ein paar zusätzliche Informationen: 

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


- If you do screen -r hyper the average logs will be like this:

![resim](https://github.com/user-attachments/assets/0e07d3da-e1a9-4b38-b01d-7e8c2bfd8bc9)

