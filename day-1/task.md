# Day 1

## Definisi DevOps

DevOps adalah gabungan orang, proses, dan teknologi untuk maintaining,
monitoring, dan developing infrastruktur pada suatu produk aplikasi

# Install Ubuntu Server

## Step 1

Download file iso ubuntu server
dari <https://ubuntu.com/download/server>

![](./images/media/image1.png

Step 2

Download dan install VMware Workstation Player
https://www.vmware.com/products/workstation-player.html

![](./images/media/image2.png)

## Step 3

Buka VMware kemudian klik Create a new virtual machine

![](./images/media/image3.png)

## Step 4

Pilih installer disc image file (iso) kemudian pilih file iso. Ubuntu
server yang akan diinstal lalu klik next.

![](./images/media/image4.png)

## Step 5

Isikan nama virtual machine dan lokasi virtual machine

![](./images/media/image5.png)

## Step 6

Kemudian atur kapasitas storage untuk virtual machine dan pilih split
virtual disk into multiple files

![](./images/media/image6.png)

## Step 7

Klik customize hardware

![](./images/media/image7.png)

## Step 8

Klik network adapter kemudian dibagian network connection pilih opsi
Bridged

![](./images/media/image8.png)

## Step 9

Jalankan atau play virtual machine yang sudah dibuat

![](./images/media/image9.png)

## Step 10

Pilih Try or install ubuntu server

![](./images/media/image10.png)

## Step 11

Pilih Bahasa yang digunakan

![](./images/media/image11.png)

## Step 12

Pilih layout keyboard

![](./images/media/image12.png)

## Step 13

Pilih Ubuntu server
![](./images/media/image13.png)

## Step 14

Pilih ens33 kemudian edit IPv4

![](./images/media/image14.png)

## Step 15

IPv4 method pilih manual

![](./images/media/image15.png)

## Step 16

Isikan subnet, address, gateway, name servers kemudian save

![](./images/media/image16.png)

## Step 17

Bila sudah pilih Done

![](./images/media/image17.png)

## Step 18

Isi proxy address bila digunakan

![](./images/media/image18.png)

## Step 19

Isi mirror address bila menggunakan address alternatif

![](./images/media/image19.png)

## Step 20

Pilih Custom storage layout

![](./images/media/image20.png)

## Step 21

Tambah partisi baru dengan memilih free space kemudian add GPT partition

![](./images/media/image21.png)

## Step 22

Isi size partition dan format untuk partisi root dan swap

![](./images/media/image22.png)

![](./images/media/image23.png)

## Step 23

Bila sudah pilih continue untuk memulai pembuatan partisi disk virtual
machine

![](./images/media/image24.png)

## Step 24

Isi nama, nama server, username dan password

![](./images/media/image25.png)

## Step 25

Pilih install OpenSSH server

![](./images/media/image26.png)

## Step 26

Pilih package yang diperlukan untuk diinstal (untuk ini kita pilih
docker)

![](./images/media/image27.png)

## Step 27

Bila sudah tunggu proses instalasi hingga selesai

![](./images/media/image28.png)

## Step 28

Jika sudah maka kita login dengan username dan password kita tes koneksi
dengan command ping

![](./images/media/image29.png)
![](./images/media/image30.png)
