# Jarkom-Modul-4-A09-2023
**Praktikum Jaringan Komputer Modul 4 Tahun 2023**

## Author
| Nama | NRP |Github |
|---------------------------|------------|--------|
|Andika Laksana Putra | 5025211001 | https://github.com/DikaPutra07 |
|M. Naufal Badruttamam | 5025211240 | https://github.com/Caknoooo |

# Laporan Resmi
## Daftar Isi
- [Laporan Resmi](#laporan-resmi)
  - [Daftar Isi](#daftar-isi)
  - [Topologi](#topologi)
  - [Prefix IP](#prefix-ip)
  - [Rute](#rute)
- [VLSM](#vlsm)
  - [Tree](#tree)
  - [Pembagian IP](#pembagian-ip)
- [CIDR](#cidr)
  - [Penggabungan IP](#penggabungan-ip)
  - [Tree](#tree-1)
  - [Pembagian IP](#pembagian-ip-2)
  - [Testing](#testing)

## Topologi

![image](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/257d48f1-40ff-48b2-8504-65d7d8cc982d)

## Prefix IP 
Kelompok kami memiliki prefix IP `192.173`

## Rute
Setelah melakukan riset dan melakukan percobaan serta melihat cara melakukan routing pada modul [jarkom](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/tree/master/Modul-4), diperoleh hasil dari ``rute`` yang kami dapatkan adalah sebagai berikut 

![image](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/c804eac6-777a-4ba4-b383-e44d496643a4)

## VLSM
VLSM atau biasa dikenal sebagai *Variable Length Subnet Masking* merupakan teknik ``subnetting`` untuk mengefisienkan pembagian ``IP`` di dalam jaringan. Besar ``netmask`` disesuaikan dengan banyaknya komputer / host yang membutuhkan alamat IP


Dalam suatu subnet. Dengan menggunakan ``VLSM``, kita dapat mengalokasikan blok alamat ``IP`` yang sesuai dengan kebutuhan tiap subnet, tanpa perlu mengikuti batasan-batasan yang seragam. Ini memungkinkan administrator jaringan untuk lebih ``fleksibel`` dalam mengoptimalkan penggunaan alamat ``IP`` dan ``menghindari pemborosan`` sumber daya.

Proses implementasi ``VLSM`` melibatkan ``pemecahan`` suatu jaringan besar ``menjadi subnet yang lebih kecil`` dengan ukuran yang berbeda-beda. Setiap subnet kemudian diberikan ``netmask`` sesuai dengan jumlah host yang diperlukan di dalamnya. Dengan cara ini, subnet yang memiliki lebih banyak host akan mendapatkan ``netmask`` dengan jumlah bit yang lebih sedikit, sementara subnet yang membutuhkan lebih sedikit host akan memiliki ``netmask`` dengan jumlah ``bit`` yang lebih banyak.

Keunggulan utama dari ``VLSM`` adalah ``efisiensi`` penggunaan alamat IP, karena kita dapat menghindari memberikan ``subnet`` dengan ukuran yang besar kepada jaringan kecil yang sebenarnya hanya membutuhkan sejumlah kecil alamat IP. Selain itu, ``VLSM`` juga membantu dalam mengurangi ``konsumsi`` alamat IP secara keseluruhan di dalam jaringan, sehingga dapat ``mendukung pertumbuhan dan perluasan jaringan`` secara lebih efektif.

### Tree
Berikut merupakan hasil ``pemecahan`` subnet besar yang akan dibentuk menjadi ``jaringan`` yang lebih kecil

![VLSM A09](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/6cb8b8ab-a72d-4ea8-bd3f-0fac8bde180a)

### Pembagian IP
Berikut adalah hasil dari pembagian ``IP`` yang telah kami peroleh dari hasil ``pemecahan`` tadi menjadi jaringan yang lebih kecil

![image](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/99979f3a-e407-4923-926d-07cf22ec1e7e)

## CIDR
CIDR atau biasa dikenal *Classless Inter-Domain* Routing adalah suatu metode ``pengalamatan dan pengelompokan alamat IP`` yang memungkinkan penggunaan lebih efisien dari ruang alamat IP yang tersedia di Internet. Sebelum diperkenalkannya ``CIDR``, pengalamatan IP didasarkan pada kelas-kelas, seperti ``kelas A, kelas B, dan kelas C``. Setiap kelas memiliki ``ukuran tetap`` untuk jaringan dan host, yang seringkali mengakibatkan pemborosan alamat IP. 

**CIDR** menggantikan ``pendekatan kelas`` dengan memperkenalkan notasi format baru yang memungkinkan ``fleksibilitas`` lebih besar dalam pengelompokan dan alokasi alamat IP. Format notasi CIDR terdiri dari alamat IP dan prefiks (subnet mask) yang diwakili dalam ``format bilangan biner``, seperti contoh berikut:
```
192.173.0.0 / 24
```
Dalam contoh ini, ``"192.173.0.0"`` adalah alamat jaringan, dan ``"/24"`` menunjukkan bahwa ``24 bit pertama`` dari alamat ini digunakan sebagai ``netmask`` (subnet mask). Dengan menggunakan CIDR, ``administrator jaringan`` dapat menentukan ukuran subnet yang sesuai dengan kebutuhan tanpa terikat pada batasan kelas tradisional.

**Keuntungan utama** CIDR melibatkan ``penghematan alamat IP dan pengurangan pemborosan``. Dengan CIDR, tidak perlu lagi mengalokasikan blok alamat IP dengan ukuran yang tetap berdasarkan kelas. Sebagai contoh, jika suatu jaringan ``memerlukan 300 alamat IP``, administrator dapat menggunakan CIDR untuk mengalokasikan subnet dengan panjang netmask yang sesuai tanpa harus memilih kelas yang lebih besar dari yang dibutuhkan.

CIDR juga ``mendukung agregasi rute``, yang memungkinkan penyederhanaan tabel routing di Internet. Dengan ``menggabungkan beberapa blok alamat IP ke dalam satu entri routing``, CIDR membantu mengurangi ukuran tabel routing dan efektif meningkatkan efisiensi dalam pengelolaan lalu lintas jaringan global.

### Penggabungan IP
Berikut merupakan inisialisasi kami yang akan digunakan untuk melakukan penggabungan IP

#### Kondisi Node Awal

![Node Pertama](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/e4bf530c-10f2-4d08-b082-d0e32af4537a)


![image](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/be65147a-45a0-4cb3-831e-9094fc46e098)

#### Penggabungan Node Pertama (B)

![Node Kedua](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/c71e62d4-7dd4-4aeb-9975-2c61f17f2303)

![image](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/e6edd05d-1b46-4d71-a776-b6e73abf8b4f)

#### Penggabungan Node Kedua (C)

![Node Ketiga](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/455da297-fa41-48b4-a645-51d75ae4acde)

![image](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/1b087af3-f122-4832-8585-78e237559529)

#### Penggabungan Node Ketiga

![Node Keempat](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/fd9341b3-4501-48fb-92b2-8635b2986ac7)


![image](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/2ab47d8c-fa03-4ce1-ba3e-7a30556223da)

#### Penggabungan Node Keempat

![Node Kelima](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/704d1e9e-c7d6-4c75-814e-d444b8251936)

![image](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/1231d69d-3dc3-4367-a324-e6c6ff832774)

#### Penggabungan Node Kelima

![Node Keenam](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/dbcb8a17-1c4c-488f-87da-de8883752c04)

![image](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/2583282e-889e-449c-88a8-982641f481e7)

#### Penggabungan Node Keenam

![Node Ketujuh](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/cc141291-0540-4f6c-9e35-718921101a78)

![image](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/a4ef6088-83a0-481d-9ec7-f4c0895dc4e4)

#### Penggabungan Node Ketujuh

![Node Kedelapan](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/520a647f-ba3b-490b-8fa5-d1b2d9deb6d8)

![image](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/4b6135ed-058f-4029-b391-0b12c5d3c1a0)

#### Penggabungan Node Kedelapan

![Node Kesembilan](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/3c0a9590-703a-4df5-8572-e2566292e43b)

![image](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/a13429ee-aa4f-4481-b1bb-964ed0d98c55)

### Tree
Setelah dilakukannya ``penggabungan IP``, sekarang kita melakukan pembagian IP dengan menggunakan ``tree`` pada masing-masing kelompok yang telah dibuat sebelumnya sebagai berikut

![VLSM A09 (1)](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/b8f51411-59f6-413f-a832-4d0414773d57)

### Pembagian IP
Berikut merupakan hasil dari pembagian IP berdasarkan Tree yang telah dibuat sebelumnya 

![image](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/1eed8a35-3ae0-4b03-9a3d-cd853c297f9d)

### Testing

https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/72368866-f77b-4bbf-a979-86aed03e464c
