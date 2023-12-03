# Jarkom-Modul-4-A09-2023
**Praktikum Jaringan Komputer Modul 4 Tahun 2023**

## Author
| Nama | NRP |Github |
|---------------------------|------------|--------|
|Andika Laksana Putra | 5025211001 | https://github.com/DikaPutra07 |
|M. Naufal Badruttamam | 5025211240 | https://github.com/Caknoooo |

# Laporan Resmi

Disini kami mengimplementasikan ``CIDR`` dengan menggunakan ``Cisco`` dan ``VLSM`` dengan menggunakan ``GNS3``

## Daftar Isi
- [Laporan Resmi](#laporan-resmi)
- [Daftar Isi](#daftar-isi)
  - [Topologi PKT CIDR](#topologi-pkt-cidr)
  - [Topologi GNS VLSM](#topologi-gns-vlsm)
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
  - [Pembagian IP](#pembagian-ip-2)

## Topologi PKT CIDR

![image](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/257d48f1-40ff-48b2-8504-65d7d8cc982d)

## Topologi GNS VLSM 

![image](https://github.com/Caknoooo/Jarkom-Modul-4-A09-2023/assets/92671053/69389c81-e897-4c92-b8c7-7f419a915ee4)

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

### Konfigurasi Network

- RoyalCapital (63 Host)

```
#A1
auto eth0
iface eth0 inet static
address 192.173.8.5
netmask 255.255.255.0
gateway 192.173.8.1
```

- WilleRegion (63 Host)

```
#A1
auto eth0
iface eth0 inet static
address 192.173.8.10
netmask 255.255.255.0
gateway 192.173.8.1
```

- Denken 

```
auto lo
iface lo inet loopback

#A2
auto eth0
iface eth0 inet static
address 192.173.7.106
netmask 255.255.255.252
gateway 192.173.7.105

#A1
auto eth1
iface eth1 inet static
address 192.173.8.1
netmask 255.255.255.0
```

- Aura 

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp

#A20
auto eth1
iface eth1 inet static
address 192.173.7.141
netmask 255.255.255.252

#A2
auto eth2
iface eth2 inet static
address 192.173.7.105
netmask 255.255.255.252

#A3
auto eth3
iface eth3 inet static
address 192.173.7.109
netmask 255.255.255.252
```

- Frieren 

```
auto lo
iface lo inet loopback

#A20
auto eth0
iface eth0 inet static
address 192.173.7.142
netmask 255.255.255.252
gateway 192.173.7.141

#A19
auto eth1
iface eth1 inet static
address 192.173.7.137
netmask 255.255.255.252

#A21
auto eth2
iface eth2 inet static
address 192.173.7.161
netmask 255.255.255.224
```

- LakeKorridor (24 Host)

```
#A21
auto eth0
iface eth0 inet static
address 192.173.7.165
netmask 255.255.255.224
gateway 192.173.7.161
```

- Flamme 

```
auto lo
iface lo inet loopback

#A19
auto eth0
iface eth0 inet static
address 192.173.7.138
netmask 255.255.255.252
gateway 192.173.7.137

#A14
auto eth1
iface eth1 inet static
address 192.173.7.129
netmask 255.255.255.252

#A16
auto eth2
iface eth2 inet static
address 192.173.20.1
netmask 255.255.252.0

#A17
auto eth3
iface eth3 inet static
address 192.173.7.133
netmask 255.255.255.252
```

- Fern 

```
auto lo
iface lo inet loopback

#A17
auto eth0
iface eth0 inet static
address 192.173.7.134
netmask 255.255.255.252
gateway 192.173.7.133

#A18
auto eth1
iface eth1 inet static
address 192.173.24.1
netmask 255.255.248.0
```

- LaubHills (397 Host)

```
auto eth0
iface eth0 inet static
address 192.173.25.5
netmask 255.255.248.0
gateway 192.173.24.1
```

- AppetitRegion (625 Host)

```
auto eth0
iface eth0 inet static
address 192.173.25.10
netmask 255.255.248.0
gateway 192.173.24.1
```

- RohrRoad (1000 Host)

```
#A16
auto eth0
iface eth0 inet static
address 192.173.20.5
netmask 255.255.252.0
gateway 192.173.20.1
```

- Himmel 

```
auto lo
iface lo inet loopback

#A14
auto eth0
iface eth0 inet static
address 192.173.7.130
netmask 255.255.255.252
gateway 192.173.7.129

#A13
auto eth1
iface eth1 inet static
address 192.173.7.145
netmask 255.255.255.248
```

- ShcwerMountains (5 Host)

```
auto eth0
iface eth0 inet static
address 192.173.7.147
netmask 255.255.255.248
gateway 192.173.7.145
```

- Eisen 

```
auto lo
iface lo inet loopback

#A3
auto eth0
iface eth0 inet static
address 192.173.7.110
netmask 255.255.255.252
gateway 192.173.7.109

#A15
auto eth1
iface eth1 inet static
address 192.173.7.153
netmask 255.255.255.248

#A4
auto eth2
iface eth2 inet static
address 192.173.7.113
netmask 255.255.255.252

#A5
auto eth3
iface eth3 inet static
address 192.173.7.117
netmask 255.255.255.252

#A8
auto eth4
iface eth4 inet static
address 192.173.7.121
netmask 255.255.255.252
```

- Stark 

```
auto eth0
iface eth0 inet static
address 192.173.7.114
netmask 255.255.252.0
gateway 192.173.7.113
```

- Lugner 

```
auto lo
iface lo inet loopback

#A5
auto eth0
iface eth0 inet static
address 192.173.7.118
gateway 192.173.7.117
netmask 255.255.255.252

#A6
auto eth1
iface eth1 inet static
address 192.173.12.1
netmask 255.255.252.0

#A7
auto eth2
iface eth2 inet static
address 192.173.9.1
netmask 255.255.255.0
```

- TurkRegion (1000 Host)

```
auto eth0
iface eth0 inet static
address 192.173.12.5
netmask 255.255.252.0
gateway 192.173.12.1
```

- GrobeForest (250 Host)

```
auto eth0
iface eth0 inet static
address 192.173.9.5
netmask 255.255.255.0
gateway 192.173.9.1
```

- Richter 

```
auto eth0
iface eth0 inet static
address 192.173.7.154
netmask 255.255.252.0
gateway 192.173.7.153
```

- Revolte

```
auto eth0
iface eth0 inet static
address 192.173.7.155
netmask 255.255.252.0
gateway 192.173.7.153
```

- Linie 

```
auto lo
iface lo inet loopback

#A8
auto eth0
iface eth0 inet static
address 192.173.7.122
gateway 192.173.7.121
netmask 255.255.255.252

#A9
auto eth1
iface eth1 inet static
address 192.173.10.1
netmask 255.255.254.0

#A10
auto eth2
iface eth2 inet static
address 192.173.7.125
netmask 255.255.255.252
```

- GranzChannel (254 Host)

```
auto eth0
iface eth0 inet static
address 192.173.10.5
netmask 255.255.254.0
gateway 192.173.10.1
```

- Lawine 

```
auto lo
iface lo inet loopback

#A10
auto eth0
iface eth0 inet static
address 192.173.7.126
netmask 255.255.255.252
gateway 192.173.7.125

#A11
auto eth1
iface eth1 inet static
address 192.173.7.193
netmask 255.255.255.192
```

- BredtRegion (29 Host)

```
auto eth0
iface eth0 inet static
address 192.173.7.197
netmask 255.255.255.192
gateway 192.173.7.193
```

- Heiter 

```
auto lo
iface lo inet loopback

#A11
auto eth0
iface eth0 inet static
address 192.173.7.222
netmask 255.255.255.192
gateway 192.173.7.193

#A12
auto eth1
iface eth1 inet static
address 192.173.16.1
netmask 255.255.252.0
```

- Sein 

```
auto eth0
iface eth0 inet static
address 192.173.16.2
netmask 255.255.252.0
gateway 192.173.16.1
```

- RiegelCanyon (510 Host)

```
auto eth0
iface eth0 inet static
address 192.173.16.7
netmask 255.255.252.0
gateway 192.173.16.1
```

### Routing 

- Denken 

```
up route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.173.7.105
```

- Lugner 

```
up route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.173.7.110
```

- Linie 

```
up route add -net 192.173.7.192 netmask 255.255.255.192 gw 192.173.7.126
up route add -net 192.173.16.0 netmask 255.255.252.0 gw 192.173.7.126
```

- Lawine 

```
up route add -net 192.173.16.0 netmask 255.255.252.0 gw 192.173.7.222
```

- Heiter

```
up route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.173.7.126
```

- Himmel 

```
up route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.173.7.138
```

- Flamme 

```
up route add -net 192.173.24.0 netmask 255.255.248.0 gw 192.173.7.134
up route add -net 192.173.7.144 netmask 255.255.255.248 gw 192.173.7.130
```

- Fern 

```
up route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.173.7.138
```

- Frieren

```
up route add -net 192.173.7.132 netmask 255.255.255.252 gw 192.173.7.138
up route add -net 192.173.24.0 netmask 255.255.248.0 gw 192.173.7.138
up route add -net 192.173.20.0 netmask 255.255.252.0 gw 192.173.7.138
up route add -net 192.173.7.128 netmask 255.255.255.252 gw 192.173.7.138
up route add -net 192.173.7.144 netmask 255.255.255.248 gw 192.173.7.138
```

- Eisen 

```
up route add -net 192.173.12.0 netmask 255.255.252.0 gw 192.173.7.118
up route add -net 192.173.9.0 netmask 255.255.255.0 gw 192.173.7.118

up route add -net 192.173.10.0 netmask 255.255.254.0 gw 192.173.7.122
up route add -net 192.173.7.124 netmask 255.255.255.252 gw 192.173.7.122
up route add -net 192.173.7.192 netmask 255.255.255.192 gw 192.173.7.122
up route add -net 192.173.16.0 netmask 255.255.252.0 gw 192.173.7.122
```

- Aura 

```
# Frieren
up route add -net 192.173.7.160 netmask 255.255.255.224 gw 192.173.7.142
up route add -net 192.173.7.136 netmask 255.255.255.252 gw 192.173.7.142
up route add -net 192.173.7.132 netmask 255.255.255.252 gw 192.173.7.142
up route add -net 192.173.24.0 netmask 255.255.248.0 gw 192.173.7.142
up route add -net 192.173.20.0 netmask 255.255.252.0 gw 192.173.7.142
up route add -net 192.173.7.128 netmask 255.255.255.252 gw 192.173.7.142
up route add -net 192.173.7.144 netmask 255.255.255.248 gw 192.173.7.142

# Denken
up route add -net 192.173.8.0 netmask 255.255.255.0 gw 192.173.7.106

# Eisen
up route add -net 192.173.7.112 netmask 255.255.255.252 gw 192.173.7.110
up route add -net 192.173.7.116 netmask 255.255.255.252 gw 192.173.7.110
up route add -net 192.173.12.0 netmask 255.255.252.0 gw 192.173.7.110
up route add -net 192.173.9.0 netmask 255.255.255.0 gw 192.173.7.110
up route add -net 192.173.7.120 netmask 255.255.255.252 gw 192.173.7.110
up route add -net 192.173.10.0 netmask 255.255.254.0 gw 192.173.7.110
up route add -net 192.173.7.124 netmask 255.255.255.252 gw 192.173.7.110
up route add -net 192.173.7.192 netmask 255.255.255.192 gw 192.173.7.110
up route add -net 192.173.16.0 netmask 255.255.252.0 gw 192.173.7.110
up route add -net 192.173.7.152 netmask 255.255.255.248 gw 192.173.7.110
```

### Testing

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

### Result 

![video](https://github.com/Caknoooo/Jarkom-Modul-3-A09-2023/assets/92671053/72368866-f77b-4bbf-a979-86aed03e464c)
