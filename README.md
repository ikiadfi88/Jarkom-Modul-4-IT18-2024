# **LAPORAN RESMI PRAKTIKUM KOMUNIKASI DATA & JARINGAN KOMPUTER MODUL 4**

Berikut adalah Laporan Resmi Praktikum Komunikasi Data & Jaringan Komputer Modul 4 oleh Kelompok IT18.

| Nama                 | NRP        |
| -------------------- | ---------- |
| Iki Adfi Nur Mohamad | 5027221033 |
| Siti Nur Ellyzah     | 5027221014 |

---

# Laporan Resmi

Pada modul kali ini, kami mengimplementasikan `CIDR` dengan menggunakan `Cisco` dan `VLSM` dengan menggunakan `GNS3`

## Daftar Isi

- [Laporan Resmi](#laporan-resmi)
- [Daftar Isi](#daftar-isi)
  - [Topologi PKT VLSM](#topologi-pkt-vlsm)
  - [Topologi GNS CIDR](#topologi-gns-cidr)
  - [Prefix IP](#prefix-ip)
  - [Rute](#rute)
- [VLSM](#vlsm)
  - [Tree](#tree)
  - [Pembagian IP](#pembagian-ip)
  - [Konfigurasi Network](#konfigurasi-network)
  - [Routing](#routing)
  - [Testing](#testing)
- [CIDR](#cidr)
  - [Penggabungan IP](#penggabungan-ip)
  - [Tree](#tree-1)
  - [Pembagian IP](#pembagian-ip-1)
  - [Testing](#testing-1)

# Topologi PKT VLSM

![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/4187bd5a-8791-4867-92da-abc142408f9b)

# Topologi GNS CIDR

# Prefix IP

Kelompok kami memiliki prefix IP `192.242`

# Rute

Setelah melakukan analisis, diperoleh hasil dari `rute` yang kami dapatkan adalah sebagai berikut

![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/93adcecd-a7c9-443d-b650-924f76d85bda)

# VLSM

VLSM atau biasa dikenal sebagai _Variable Length Subnet Masking_ merupakan teknik `subnetting` untuk mengefisienkan pembagian `IP` di dalam jaringan. Besar `netmask` disesuaikan dengan banyaknya komputer / host yang membutuhkan alamat IP

Dalam suatu subnet. Dengan menggunakan `VLSM`, kita dapat mengalokasikan blok alamat `IP` yang sesuai dengan kebutuhan tiap subnet, tanpa perlu mengikuti batasan-batasan yang seragam. Ini memungkinkan administrator jaringan untuk lebih fleksibel dalam mengoptimalkan penggunaan alamat `IP` dan menghindari pemborosan sumber daya.

Proses implementasi `VLSM` melibatkan pembagian suatu jaringan besar menjadi subnet yang lebih kecil dengan ukuran yang berbeda-beda. Setiap subnet kemudian diberikan `netmask` sesuai dengan jumlah host yang diperlukan di dalamnya. Dengan cara ini, subnet yang memiliki lebih banyak host akan mendapatkan `netmask` dengan jumlah bit yang lebih sedikit, sementara subnet yang membutuhkan lebih sedikit host akan memiliki `netmask` dengan jumlah `bit` yang lebih banyak.

Keunggulan utama dari `VLSM` adalah efisiensi penggunaan alamat IP, karena kita dapat menghindari memberikan `subnet` dengan ukuran yang besar kepada jaringan kecil yang sebenarnya hanya membutuhkan sejumlah kecil alamat IP. Selain itu, `VLSM` juga membantu dalam mengurangi penggunaan alamat IP secara keseluruhan di dalam jaringan, sehingga dapat mendukung pertumbuhan dan perluasan jaringan secara lebih efektif.

## Tree

Berikut merupakan hasil bentuk tree terhadap subnet besar yang akan dibentuk menjadi `jaringan` yang lebih kecil

![TREE JARKOM VSLM](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/6410d370-6ba4-49cf-840b-cf9333eb154a)

## Pembagian IP

Berikut adalah hasil dari pembagian `IP` yang telah kami peroleh dari hasil pembagian tadi menjadi jaringan yang lebih kecil

![Topologi_IT18](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/80c3b8ab-3d31-4779-982f-a551fa2dcd6f)

![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/c47e2f73-59b6-4fa1-92a2-8876a14a5a96)

## Konfigurasi Network

### Router

1. Untuk konfigurasi Router, pertama masukkan IP dan Gateaway masing-masing router di port Ethernet yang sesuai dengan arah subnet pada pembagian di atas.

2. Tentukan mana ethernet yang akan dikonfigurasikan antar router. Jika dilihat pada jaringan Jawa terdapat `Fa0/1` , `Fa1/1` , `Fa1/0` , dan `Fa0/0`. Kita perlu memasukkan IP dan subnet mask yang seusai pada masing-masing jaringan ethernet yang tersambung ke router lain

![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/4b61fdc2-cc30-4457-b6b3-261ccfd3a002)

3. Contoh pada router Jawa, kemudian lakukan ke semua router lainnya. Beriut contoh konfigurasi pada ethernet `Fa0/1` .

![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/3d6fbbeb-256d-4ff5-a1a1-33aaf2c7d45f)

Note: untuk sambungan `Fa0/0` (JAWA ke Cloud) tidak perlu dikonfigurasikan.

Ulangi langkah ini pada semua router lain

### Client & Server

1. Konfigurasikan IP, Mask, dan Gateaway sesuai dengan tabel pembagian IP di atas.

2. Untuk node Client & Server, buka tab desktop dan pilih IP Configuration. Kemudian pada node server, tambahkan DNS Server sesuai dengan Subnet Mask

3. Contoh pada client Sebuku dan server Sebesi

![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/6a5b7329-bb64-4fe2-acdc-3272cb210d3b)

![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/0f6aaa5f-ff78-4c5b-8329-f47d1f91f8cd)

Ulangi langkah di atas ke client dan server lain juga

### Konfigurasi Routing

1. Pada masing-masing router buka tab static. Kemudian lakukan konfigurasi sesuai berikut

    - **JAWA**

      ![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/57e269a6-fdcc-4d63-af2b-64bc4e45f434)

      ![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/3a5a24c7-df2e-470d-bd2f-0be4e4baf6b7)

    - **SUMATERA**

      ![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/b0784163-2dde-4a86-8f36-5abf0769e140)

    - **KALIMANTAN**

      ![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/1f87a1e8-4f8f-4940-bbf8-a2e97216bfe3)

    - **SULAWESI**
      
      ![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/116c81b6-ac7e-40e3-a746-ec2312066af6)

    - **LAMPUNG**

      ![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/f84234ca-5091-49ca-b19f-ffaee0afeef4)

    - **SUMATERA UTARA**

      ![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/8ce80a7d-ca3e-486c-ae28-b61a3d9e86f5)

    - **ACEH**
   
      ![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/3fa7fb67-f7b8-4ae9-b97f-d31964ca299b)

    - **KALIMANTAN UTARA**

      ![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/0226436a-7704-4e1b-989d-01cf88106a6b)

    - **KALIMANTAN TIMUR**

      ![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/251936f6-93d2-4b28-99d6-6539ec2a620a)

    - **KALIMANTAN SELATAN**

      ![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/f78f5524-ee07-4d23-9432-2ab3375e5c49)
      
    - **MAKASSAR**

      ![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/b743e143-54e3-4652-9fbc-5dc7cebfcb99)

    - **BELAWA**

      ![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/093f231d-8cd5-46c4-a29f-55cd2bdf32d6)

    - **MALUKU UTARA**

      ![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/ea7c3c78-bd9a-4989-aafa-58ce8a8f132d)

      
## Testing

![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/883bc059-1ea9-415e-a4d7-3c52d8b4bbc2)

![image](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/c95eab88-4bb9-4c35-8f52-9ba5740a3b5e)

----------

# CIDR

CIDR atau biasa dikenal _Classless Inter-Domain_ Routing adalah suatu metode `pengalamatan dan pengelompokan alamat IP` yang memungkinkan penggunaan lebih efisien dari ruang alamat IP yang tersedia di Internet. Sebelum diperkenalkannya `CIDR`, pengalamatan IP didasarkan pada kelas-kelas, seperti `kelas A, kelas B, dan kelas C`. Setiap kelas memiliki `ukuran tetap` untuk jaringan dan host, yang seringkali mengakibatkan pemborosan alamat IP.

**CIDR** menggantikan `pendekatan kelas` dengan memperkenalkan notasi format baru yang memungkinkan `fleksibilitas` lebih besar dalam pengelompokan dan alokasi alamat IP. Format notasi CIDR terdiri dari alamat IP dan prefiks (subnet mask) yang diwakili dalam `format bilangan biner`, seperti contoh berikut:

```
192.242.0.0 / 24
```

Dalam contoh ini, `"192.242..0.0"` adalah alamat jaringan, dan `"/24"` menunjukkan bahwa `24 bit pertama` dari alamat ini digunakan sebagai `netmask` (subnet mask). Dengan menggunakan CIDR, `administrator jaringan` dapat menentukan ukuran subnet yang sesuai dengan kebutuhan tanpa terikat pada batasan kelas tradisional.

**Keuntungan utama** CIDR melibatkan `penghematan alamat IP dan pengurangan pemborosan`. Dengan CIDR, tidak perlu lagi mengalokasikan blok alamat IP dengan ukuran yang tetap berdasarkan kelas. Sebagai contoh, jika suatu jaringan `memerlukan 300 alamat IP`, administrator dapat menggunakan CIDR untuk mengalokasikan subnet dengan panjang netmask yang sesuai tanpa harus memilih kelas yang lebih besar dari yang dibutuhkan.

CIDR juga `mendukung agregasi rute`, yang memungkinkan penyederhanaan tabel routing di Internet. Dengan `menggabungkan beberapa blok alamat IP ke dalam satu entri routing`, CIDR membantu mengurangi ukuran tabel routing dan efektif meningkatkan efisiensi dalam pengelolaan lalu lintas jaringan global.

## Penggabungan IP

Berikut merupakan metode yang kami gunakan untuk melakukan penggabungan IP

### Kondisi Node Awal

### Penggabungan Node Pertama (B)

### Penggabungan Node Kedua (C)

### Penggabungan Node Ketiga

### Penggabungan Node Keempat

### Penggabungan Node Kelima

### Penggabungan Node Keenam

### Penggabungan Node Ketujuh

### Penggabungan Node Kedelapan

## Tree

Setelah dilakukannya `penggabungan IP`, sekarang kita melakukan pembagian IP dengan menggunakan `tree` pada masing-masing kelompok yang telah dibuat sebelumnya sebagai berikut

## Pembagian IP

Berikut merupakan hasil dari pembagian IP berdasarkan Tree yang telah dibuat pada GNS menggunakan CIRD

## Testing
