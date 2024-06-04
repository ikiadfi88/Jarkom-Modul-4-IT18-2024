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

## Topologi PKT VLSM

## Topologi GNS CIDR

## Prefix IP

Kelompok kami memiliki prefix IP `192.242`

## Rute

Setelah melakukan riset dan melakukan percobaan serta melihat cara melakukan routing pada modul 4 jarkom, diperoleh hasil dari `rute` yang kami dapatkan adalah sebagai berikut

## VLSM

VLSM atau biasa dikenal sebagai _Variable Length Subnet Masking_ merupakan teknik `subnetting` untuk mengefisienkan pembagian `IP` di dalam jaringan. Besar `netmask` disesuaikan dengan banyaknya komputer / host yang membutuhkan alamat IP

Dalam suatu subnet. Dengan menggunakan `VLSM`, kita dapat mengalokasikan blok alamat `IP` yang sesuai dengan kebutuhan tiap subnet, tanpa perlu mengikuti batasan-batasan yang seragam. Ini memungkinkan administrator jaringan untuk lebih `fleksibel` dalam mengoptimalkan penggunaan alamat `IP` dan `menghindari pemborosan` sumber daya.

Proses implementasi `VLSM` melibatkan `pemecahan` suatu jaringan besar `menjadi subnet yang lebih kecil` dengan ukuran yang berbeda-beda. Setiap subnet kemudian diberikan `netmask` sesuai dengan jumlah host yang diperlukan di dalamnya. Dengan cara ini, subnet yang memiliki lebih banyak host akan mendapatkan `netmask` dengan jumlah bit yang lebih sedikit, sementara subnet yang membutuhkan lebih sedikit host akan memiliki `netmask` dengan jumlah `bit` yang lebih banyak.

Keunggulan utama dari `VLSM` adalah `efisiensi` penggunaan alamat IP, karena kita dapat menghindari memberikan `subnet` dengan ukuran yang besar kepada jaringan kecil yang sebenarnya hanya membutuhkan sejumlah kecil alamat IP. Selain itu, `VLSM` juga membantu dalam mengurangi `konsumsi` alamat IP secara keseluruhan di dalam jaringan, sehingga dapat `mendukung pertumbuhan dan perluasan jaringan` secara lebih efektif.

### Tree

Berikut merupakan hasil `pemecahan` subnet besar yang akan dibentuk menjadi `jaringan` yang lebih kecil

![TREE JARKOM](https://github.com/ikiadfi88/Jarkom-Modul-4-IT18-2024/assets/120791817/14096c3f-718f-4be3-a960-e4fe6e8e45b2)

### Pembagian IP

Berikut adalah hasil dari pembagian `IP` yang telah kami peroleh dari hasil `pemecahan` tadi menjadi jaringan yang lebih kecil

### Konfigurasi Network

### Testing

## CIDR

CIDR atau biasa dikenal _Classless Inter-Domain_ Routing adalah suatu metode `pengalamatan dan pengelompokan alamat IP` yang memungkinkan penggunaan lebih efisien dari ruang alamat IP yang tersedia di Internet. Sebelum diperkenalkannya `CIDR`, pengalamatan IP didasarkan pada kelas-kelas, seperti `kelas A, kelas B, dan kelas C`. Setiap kelas memiliki `ukuran tetap` untuk jaringan dan host, yang seringkali mengakibatkan pemborosan alamat IP.

**CIDR** menggantikan `pendekatan kelas` dengan memperkenalkan notasi format baru yang memungkinkan `fleksibilitas` lebih besar dalam pengelompokan dan alokasi alamat IP. Format notasi CIDR terdiri dari alamat IP dan prefiks (subnet mask) yang diwakili dalam `format bilangan biner`, seperti contoh berikut:

```
192.242.0.0 / 24
```

Dalam contoh ini, `"192.242..0.0"` adalah alamat jaringan, dan `"/24"` menunjukkan bahwa `24 bit pertama` dari alamat ini digunakan sebagai `netmask` (subnet mask). Dengan menggunakan CIDR, `administrator jaringan` dapat menentukan ukuran subnet yang sesuai dengan kebutuhan tanpa terikat pada batasan kelas tradisional.

**Keuntungan utama** CIDR melibatkan `penghematan alamat IP dan pengurangan pemborosan`. Dengan CIDR, tidak perlu lagi mengalokasikan blok alamat IP dengan ukuran yang tetap berdasarkan kelas. Sebagai contoh, jika suatu jaringan `memerlukan 300 alamat IP`, administrator dapat menggunakan CIDR untuk mengalokasikan subnet dengan panjang netmask yang sesuai tanpa harus memilih kelas yang lebih besar dari yang dibutuhkan.

CIDR juga `mendukung agregasi rute`, yang memungkinkan penyederhanaan tabel routing di Internet. Dengan `menggabungkan beberapa blok alamat IP ke dalam satu entri routing`, CIDR membantu mengurangi ukuran tabel routing dan efektif meningkatkan efisiensi dalam pengelolaan lalu lintas jaringan global.

### Penggabungan IP

Berikut merupakan metode yang kami gunakan untuk melakukan penggabungan IP

#### Kondisi Node Awal

#### Penggabungan Node Pertama (B)

#### Penggabungan Node Kedua (C)

#### Penggabungan Node Ketiga

#### Penggabungan Node Keempat

#### Penggabungan Node Kelima

#### Penggabungan Node Keenam

#### Penggabungan Node Ketujuh

#### Penggabungan Node Kedelapan

### Tree

Setelah dilakukannya `penggabungan IP`, sekarang kita melakukan pembagian IP dengan menggunakan `tree` pada masing-masing kelompok yang telah dibuat sebelumnya sebagai berikut

### Pembagian IP

Berikut merupakan hasil dari pembagian IP berdasarkan Tree yang telah dibuat pada GNS menggunakan CIRD

### Testing
