![resim](https://github.com/user-attachments/assets/26646db3-b278-453d-9910-cfab1619b1e7)


# HyperSpaceAI Panduan Instalasi

## 3 Opsi Pengaturan yang Berbeda

- Browser 
- MAC / Windows 
- CLI ( Server ) 

<img src="https://github.com/user-attachments/assets/bf91e6b6-e379-4684-b11b-84106c0f2e98" alt="to0x:)" width="500">

## 1 / WEB BROWSER :

- Link : https://node.hyper.space/

#### Klik pada Tombol Merah dan aktifkan.

![resim](https://github.com/user-attachments/assets/4a763da7-40fb-4eca-87d0-a1452fbbee37)

## Setelah aktivasi, periksa Poin dan pastikan ia memiliki Keaktifan.

![resim](https://github.com/user-attachments/assets/af031538-ec03-4444-8ef5-5d76d06487ff)


![resim](https://github.com/user-attachments/assets/ced0b28d-28ec-438f-9db2-e8675826b39c)


## Kemudian mari kita simpan Kunci Pribadi yang dibuatnya untuk kita. Jangan hapus.

![resim](https://github.com/user-attachments/assets/496adc93-aff6-4bc5-bb35-66971a550592)

![resim](https://github.com/user-attachments/assets/4a0cfae8-d9e2-4739-8fd9-f4f71bf42255)


## Informasi Penting : Node membeku dan rusak - pekerjaan berhenti, bagian yang kita tekan tombolnya dan membuat warna hijau berubah menjadi merah. Periksa dari waktu ke waktu.


# 2 / Windows :

- Link : https://hyper.space/

![resim](https://github.com/user-attachments/assets/32f93027-4da1-4b66-8252-017e414694d6)

- GPU ( Kartu Tampilan ) : Nvidia
- CPU ( Prosesor ) : x86 Intel

#### Klik pada file yang diunduh dan instal.

![resim](https://github.com/user-attachments/assets/640f27d6-04ee-4254-b01d-7633531915f0)


## Bekerja: 

![resim](https://github.com/user-attachments/assets/2da9ec02-8559-4bd0-b35e-25ab38cf5907)

#### Simpan salinan kunci agar poin Anda tidak hilang.

- Jalur File Kunci C:\Users\youruser\AppData\Roaming\hyperspace

![resim](https://github.com/user-attachments/assets/e1c1cc6e-f432-4b7d-98b7-c080d27cc7a2)



# Linux VPS : 

- Main Setup : https://github.com/hyperspaceai/aios-cli?tab=readme-ov-file

#### Jalankan perintah berikut untuk memperbarui dan meng-upgrade paket sistem:

```bash
sudo apt update -y && sudo apt upgrade -y
```
## 2. Instal paket yang diperlukan:

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen unzip lz4 -y
```

## Unduh ; 

```bash
curl https://download.hyper.space/api/install | bash
```
```bash
source /root/.bashrc
```

- Unduh Sampel :

![resim](https://github.com/user-attachments/assets/998ec182-9893-4153-bae3-3a446fa6a298)


## Tetapkan Informasi : 

- Mari kita dapatkan kunci privat seperti yang kita dapatkan di bagian Browser.

![resim](https://github.com/user-attachments/assets/0a975077-26f0-4bd1-8ed6-5930d74d3de2)


## Layar ; 

```bash
screen -S hyper
```

## Mari kita luncurkan : 

```bash
aios-cli start
```
 
#### Kita dapat keluar dari halaman tersebut dengan CTRL A + D. 
- Jika Anda ingin masuk ke halaman belakang: screen -r hyper


#### 1. Mari Mengimpor Kunci ke Node:

```bash
nano my.pem
```

![resim](https://github.com/user-attachments/assets/70d5ae23-feb1-46df-9a79-16bb653fdff7)

- Simpan kunci yang Anda dapatkan dari browser dengan Klik Kanan. (Saya mendapatkan kunci baru dari browser yang berbeda untuk menghindari konflik).

- CTRL X Y Enter. Save


###### Mari kita impor:

```bash
aios-cli hive import-keys ./my.pem
```

![resim](https://github.com/user-attachments/assets/49c842ef-710d-4e1d-aa4a-455a476b664c)


#### Login:


```bash
aios-cli hive login
```

####  Tahapan Lainnya :

```bash
aios-cli models add hf:TheBloke/phi-2-GGUF:phi-2.Q4_K_M.gguf
```

![resim](https://github.com/user-attachments/assets/8266b70e-8add-437b-9928-b686e03da32c)


## Poin

- Untuk mendapatkan skor, Anda harus memasukkan tingkatan (saat ini berkisar antara 1-5 dari yang terbaik hingga yang terburuk).

- Setiap tingkat memiliki beberapa model yang diperlukan dan sejumlah memori GPU yang perlu Anda unduh dan simpan ke jaringan:

    1 : 30GB
    2 : 20GB
    3 : 8GB
    4 : 4GB
    5 : 2GB

## Pemeriksaan Poin :

```bash
aios-cli hive points
```

![resim](https://github.com/user-attachments/assets/bd5fede7-8b0b-4333-84d7-17dc54ac5346)


- Perintah yang Berguna :

```bash
# For fast connection if the node is stopped : 
aios-cli start --connect
# Update : 
aios-cli version
# Stop : 
aios-cli kill
```

## Copot pemasangan : 

```bash
curl https://download.hyper.space/api/uninstall | bash
```

## SBeberapa Informasi Tambahan:

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


- Jika Anda melakukan screen -r hyper, log rata-rata akan seperti ini:

![resim](https://github.com/user-attachments/assets/0e07d3da-e1a9-4b38-b01d-7e8c2bfd8bc9)

