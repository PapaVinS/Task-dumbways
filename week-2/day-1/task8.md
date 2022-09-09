# Day 1

## Cloud Computing

Definisi Cloud Computing berarti menyimpan dan mengakses data dan
program melalui internet dari lokasi berbeda atau menggunakan komputer
dari hard drive komputer kita. Fungsinya memudahkan penggunanya untuk
menjalankan program tanpa harus menginstall aplikasi terlebih dahulu dan
memudahkan pengguna untuk mengakses data dan informasi melalui internet.

## Membuat instance/VM untuk server aplikasi di IDCloudhost

## Step 1

Kita akses dan login ke dashbord console IDCloudhost terlebih dahulu
<https://console.idcloudhost.com/>

![](./images/media/image1.png){

## Step 2

Dibagian menu bar sebelah kiri kita pilih compute kemudian klik new

![](./images/media/image2.png)

## Step 3

Setelah itu akan muncul tab baru New Resource, kita pilih spesifikasi
instance nya

![](./images/media/image3.png)

Isikan username, password, SSH (bila digunakan), resource name kemudian
klik create.

![](./images/media/image4.png)

Step 4

Bila proses pembuatan selesai akan muncul tab instance yang sudah kita
buat tadi.

![](./images/media/image5.png)

## Cara generate RSA key SSH

Agar kita bisa mengakses instance server aplikasi kita secara remote
membutuhkan RSA key SSH sebagai kunci akses, untuk pembuatannya kita
perlu men-generate RSA key dahulu.

Kita gunakan `command ssh-keygen`

![](./images/media/image6.png)

Setelah generate, kita copy key id_rsa.pub ke server aplikasi `scp
.ssh/ide_rsa.pub <user>@<IP Instance>:~/.ssh`

![](./images/media/image7.png)

Kemudian kita masukkan isi id_rsa.pub ke file authorized_keys

`Cat id_rsa.pub >> authorized_keys`

![](./images/media/image8.png)

Jika sudah kita coba login menggunakan private key SSH

`Ssh -i .ssh/id_rsa <user>@<IP Server>`

![](./images/media/image9.png)

## Install aplikasi dumbflix dan PM2

## Step 1

Kita install nvm dan npm version 10

`curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh
| bash`

`nvm install 10`

![](./images/media/image10.png)

![](./images/media/image11.png)

## Step 2

Selanjutnya install PM2

`npm install -g pm2`

![](./images/media/image12.png)

## Step 3

Kita clone repository aplikasi dumbflix di github git clone
https://github.com/dumbwaysdev/dumbflix-frontend.git

![](./images/media/image13.png)

## Step 4

Jika sudah terclone, kita masuk ke direktori aplikasi kemudian kita
install npm

`cd dumbflix-frontend/`

`npm install`

![](./images/media/image14.png)

## Step 5

Kita create file script PM2 menggunakan `pm2 init simple`

![](./images/media/image15.png)

## Step 6

Kita ubah isi file ecosystem.config.js menjadi

Name : "dumbflix-app",

Script : "npm start"

![](./images/media/image16.png)

## Step 7

Kemudian kita jalankan scriot PM2 ecosystem tadi menggunakan

`pm2 start ecosystem.config.js`

![](./images/media/image17.png)

Setelah itu coba kita cek di web browser apakah sudah berjalan.

![](./images/media/image18.png)

## Setup DNS Cloudflare dan Reverse Proxy Nginx

## Step 1

Kita buat instance lagi yang nantinya digunakan untuk nginx dengan
spesifikasi yang sama

![](./images/media/image19.png)

Terus kita coba akses login ke server nginx nya

![](./images/media/image20.png)

## Step 2

Kita login dan masuk ke dashboard cloudflare kemudian di bagian menu
kiri atas kita pilih DNS

![](./images/media/image21.png)

Setelah itu kita klik add record kemudian kita isi nama dns nya dan Ipv4
address kita isi IP server nginx kita

![](./images/media/image22.png)

## Step 3

Setelah itu kita install nginx di dalam server `sudo apt-get update

sudo apt-get install nginx`

![](./images/media/image23.png)
![](./images/media/image24.png)

## Step 4

Kemudian kita buat file konfigurasi untuk reverse proxynya, disini kita
buat di folder

`sudo nano /etc/nginx/sites-enabled/rp-dumbflix.conf`

lalu isikan script berikut kemudian save

```
server{

server_name <url-domain>;

location / {

proxy_pass http://<ip-server>:<port>;

  }

}
```

![](./images/media/image25.png)

## Step 5

Kita cek konfigurasi reverse proxy tadi apakah sudah sukses

![](./images/media/image26.png)

## Step 6

Coba kita cek url domain di dalam web browser

![](./images/media/image27.png)
