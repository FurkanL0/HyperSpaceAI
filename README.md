![resim](https://github.com/user-attachments/assets/26646db3-b278-453d-9910-cfab1619b1e7)


# HyperSpaceAI Installation Guide

## 3 Different Setup Options

- Browser 
- MAC / Windows 
- CLI ( Server ) 

<img src="https://github.com/user-attachments/assets/bf91e6b6-e379-4684-b11b-84106c0f2e98" alt="to0x:)" width="500">

## 1 / WEB BROWSER :

- Link : https://node.hyper.space/

#### Click on the Red Button and make it active.

![resim](https://github.com/user-attachments/assets/4a763da7-40fb-4eca-87d0-a1452fbbee37)

## After activation, check Points and make sure it has Liveness.

![resim](https://github.com/user-attachments/assets/af031538-ec03-4444-8ef5-5d76d06487ff)


![resim](https://github.com/user-attachments/assets/ced0b28d-28ec-438f-9db2-e8675826b39c)


## Then let's save the Private Key it creates for us. Don't delete it.

![resim](https://github.com/user-attachments/assets/496adc93-aff6-4bc5-bb35-66971a550592)

![resim](https://github.com/user-attachments/assets/4a0cfae8-d9e2-4739-8fd9-f4f71bf42255)


## Important Information : The nodes freezes and breaks - the work stops, the part we press the button and make green turns red. Check from time to time.


# 2 / Windows :

- Link : https://hyper.space/

![resim](https://github.com/user-attachments/assets/32f93027-4da1-4b66-8252-017e414694d6)

- GPU ( Display Card ) : Nvidia
- CPU ( Processor ) : x86 Intel

#### Click on the downloaded file and install it.

![resim](https://github.com/user-attachments/assets/640f27d6-04ee-4254-b01d-7633531915f0)


## Working : 

![resim](https://github.com/user-attachments/assets/2da9ec02-8559-4bd0-b35e-25ab38cf5907)

#### Keep a copy of the key so that your points are not lost.

- Key's File Path C:\Users\youruser\AppData\Roaming\hyperspace

![resim](https://github.com/user-attachments/assets/e1c1cc6e-f432-4b7d-98b7-c080d27cc7a2)



# Linux VPS : 

- Main Rehber : https://github.com/hyperspaceai/aios-cli?tab=readme-ov-file

#### Run the following command to update and upgrade system packages:

```bash
sudo apt update -y && sudo apt upgrade -y
```
## 2. Gerekli paketleri kurun:

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

## Download ; 

```bash
curl https://download.hyper.space/api/install | bash
```
```bash
source /root/.bashrc
```

- Sample Download : 

![resim](https://github.com/user-attachments/assets/998ec182-9893-4153-bae3-3a446fa6a298)


## Set Information  : 

- Let's get a private key like we got in the Browser section. 

![resim](https://github.com/user-attachments/assets/0a975077-26f0-4bd1-8ed6-5930d74d3de2)


## Screen ; 

```bash
screen -S hyper
```

## Let's launch : 

```bash
aios-cli start
```
 
#### We can exit the page with CTRL A + D.
- If you want to enter the back page: screen -r hyper


#### 1. Let's Import Key to Node : 

```bash
nano my.pem
```

![resim](https://github.com/user-attachments/assets/70d5ae23-feb1-46df-9a79-16bb653fdff7)

- Save the key you got from the browser with your Right Click. (I got a new key from a different browser to avoid conflicts).

- CTRL X Y Enter. Save


###### Let's import it:

```bash
aios-cli hive import-keys ./my.pem
```

![resim](https://github.com/user-attachments/assets/49c842ef-710d-4e1d-aa4a-455a476b664c)


#### Login : 


```bash
aios-cli hive login
```

####  Other Stages :

```bash
aios-cli models add hf:TheBloke/phi-2-GGUF:phi-2.Q4_K_M.gguf
```

![resim](https://github.com/user-attachments/assets/8266b70e-8add-437b-9928-b686e03da32c)


## Points

- To get a score you need to enter a tier (currently ranging from 1-5 from best to worst).

- Each tier has some required models and certain amounts of GPU memory that you need to download and save to the network:

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


- Yararlı Komutlar : 

```bash
# Eğer node durdu ise hızlı bağlantı için : 
aios-cli start --connect
# Güncelleme : 
aios-cli version
# Durdurma : 
aios-cli kill
```

## Silme : 

```bash
curl https://download.hyper.space/api/uninstall | bash
```

## Birkaç Ek Bilgi : 

```bash
# Hangi modellerin gerekli olduğunu görmek için : 
aios-cli hive select-tier 5
# Gerekli bir modeli indirin
aios-cli models add hf:TheBloke/phi-2-GGUF:phi-2.Q4_K_M.gguf
# Özel anahtarınızı içe aktarın - nano .pem kullanarak bir my.pem dosyası oluşturun ve bir özel anahtar girin (Tarayıcı sürümünden bir özel anahtar alabilirsiniz)
aios-cli hive import-keys ./my.pem
# Bu anahtarları bu oturum için tercih edilen olarak ayarlayın
aios-cli hive login
# Modelin kayıtlı olduğundan emin olun
aios-cli hive connect
aios-cli hive select-tier 5
```


- screen -r hyper yaparsanız ortalama Loglarını böyle olacak : 

![resim](https://github.com/user-attachments/assets/0e07d3da-e1a9-4b38-b01d-7e8c2bfd8bc9)
