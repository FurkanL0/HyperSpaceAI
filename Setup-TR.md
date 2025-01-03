![resim](https://github.com/user-attachments/assets/26646db3-b278-453d-9910-cfab1619b1e7)


# HyperSpaceAI Kurulum Rehberi 

## 3 Farklı Kurulum Yapabiliyoruz 

- Browser
- MAC / Windows
- CLI ( Sunucu )

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

source /root/.bashrc
```

- Örnek İndirme : 

![resim](https://github.com/user-attachments/assets/998ec182-9893-4153-bae3-3a446fa6a298)

## Screen ; 

```bash
screen -S hyper
```

## Başlatalım : 

```bash
aios-cli start
```


