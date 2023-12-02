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
  - [Tree](#tree-1)
  - [Penggabungan IP](#penggabungan-ip)
  - [Pembagian IP](#pembagian-ip-2)

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

