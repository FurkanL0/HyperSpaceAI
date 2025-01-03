![resim](https://github.com/user-attachments/assets/26646db3-b278-453d-9910-cfab1619b1e7)


# HyperSpaceAI Kurulum Rehberi 

## 3 Farklı Kurulum Yapabiliyoruz 

- Browser https://github.com/FurkanL0/HyperSpaceAI/blob/main/Setup-TR.md#1--web-browser-
- MAC / Windows https://github.com/FurkanL0/HyperSpaceAI/blob/main/Setup-TR.md#1--web-browser-
- CLI ( Sunucu ) https://github.com/FurkanL0/HyperSpaceAI/blob/main/Setup-TR.md#linux-vps-

<img src="https://github.com/user-attachments/assets/bf91e6b6-e379-4684-b11b-84106c0f2e98" alt="to0x:)" width="500">

## 1 / WEB BROWSER :

- Link : https://node.hyper.space/

#### Sizde Kırmızıdır Butona tıklayıp Aktif olmasını sağlayın.

![resim](https://github.com/user-attachments/assets/0e6c54d2-948f-4ef7-b875-999d2a7cd9b7)

## Aktif olduktan sonra Points kısmından kontrol yapıp Liveness olduğundan emin olun.

![resim](https://github.com/user-attachments/assets/af031538-ec03-4444-8ef5-5d76d06487ff)


![resim](https://github.com/user-attachments/assets/ced0b28d-28ec-438f-9db2-e8675826b39c)


## Sonrasında bize oluşturduğu Key'i kaydedelim. Yoksa puanlar püff olabilir.

![resim](https://github.com/user-attachments/assets/496adc93-aff6-4bc5-bb35-66971a550592)

![resim](https://github.com/user-attachments/assets/4a0cfae8-d9e2-4739-8fd9-f4f71bf42255)

#### Önemli Bilgilendirme : Sistem ara ara donuyor kopuyor - çalışma duruyor butona basıp yeşil yaptığımız kısım Kırmızıya dönüyor. Ara ara kontrol edin.


## 2 / Windows :

- Link : https://hyper.space/

![resim](https://github.com/user-attachments/assets/32f93027-4da1-4b66-8252-017e414694d6)

- GPU ( Ekran Kartı ) : Nvidia
- CPU ( İşlemci ) : x86 Intel

#### İndirilen dosyaya NEXT NEXT NEXT - Kuruldu mis gibi.

![resim](https://github.com/user-attachments/assets/645320e7-4ee9-4578-802f-4983e727cf2f)

#### Bundada Puanlarınızın gitmemesi için key'in bir kopyasını saklayın. 

- Key'in Dosya Yolu C:\Users\burayasizinusergelecek\AppData\Roaming\hyperspace

![resim](https://github.com/user-attachments/assets/e1c1cc6e-f432-4b7d-98b7-c080d27cc7a2)



## Linux VPS : 

- Main Rehber : https://github.com/hyperspaceai/aios-cli?tab=readme-ov-file

#### Sistem paketlerini güncellemek ve yükseltmek için aşağıdaki komutu çalıştırın:

```bash
sudo apt update -y && sudo apt upgrade -y
```
## 2. Gerekli paketleri kurun:

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

## İndirelim ; 

```bash
curl https://download.hyper.space/api/install | bash
```
```bash
source /root/.bashrc
```

- Örnek İndirme : 

![resim](https://github.com/user-attachments/assets/998ec182-9893-4153-bae3-3a446fa6a298)


## Bilgileri Ayarlayalım  : 

- Browser kısmındaki aldığımız gibi bir private key alalım. 

![resim](https://github.com/user-attachments/assets/0a975077-26f0-4bd1-8ed6-5930d74d3de2)


## Screen ; 

```bash
screen -S hyper
```

## Başlatalım : 

```bash
aios-cli start
```
 
- CTRL A + D ile sayfadan çıkabiliriz. 
- Geri sayfaya girmek isterseniz : screen -r  hyper

Node'umuza bilgileri girelim. : 

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

#### 1. İçeride Key İmport Edelim : 

```bash
nano my.pem
```

![resim](https://github.com/user-attachments/assets/70d5ae23-feb1-46df-9a79-16bb653fdff7)

- Browser'dan aldığınız keyi Sağ Tık'ınız ile kaydedin. ( Ben Farklı bir browser'dan yeni key aldım çakışmasın diye ).

- CTRL X Y Enter. Kaydedin. 


###### İmport Edelim : 

```bash
aios-cli hive import-keys ./my.pem
```

![resim](https://github.com/user-attachments/assets/49c842ef-710d-4e1d-aa4a-455a476b664c)


#### Giriş Yapalım : 


```bash
aios-cli hive login
```

####  Diğer Aşamalar : 

```bash
aios-cli hive select-tier 5
```
```bash
aios-cli models add hf:TheBloke/phi-2-GGUF:phi-2.Q4_K_M.gguf
```

![resim](https://github.com/user-attachments/assets/8266b70e-8add-437b-9928-b686e03da32c)


## Puanlar

- Puan almak için bir kademeye girmeniz gerekir (şu anda en iyiden en kötüye 1-5 arasında değişmektedir).

- Her tier'lerde indirmeniz ve ağa kaydetmeniz gereken bazı gerekli modeller ve belirli miktarlarda GPU belleği vardır:

    1 : 30GB
    2 : 20GB
    3 : 8GB
    4 : 4GB
    5 : 2GB

## Puan Kontrolü : 

```bash
aios-cli hive points
```

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


- screen -r hyper yaparsanız ortalama Loglarını böyle olacak : 

![resim](https://github.com/user-attachments/assets/0e07d3da-e1a9-4b38-b01d-7e8c2bfd8bc9)
