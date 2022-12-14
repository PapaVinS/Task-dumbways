# Day 2

# Definisi Computer Network

Computer network adalah jaringan telekomunikasi antara computer yang
terhubung untuk saling bertukar data dan informasi.

# Contoh perintah linux yang digunakan untuk management server linux

## Ls

command ls berfungsi menampilkan list atau daftar file

## Mv

Command mv berfungsi untuk memindahkan atau rename suatu file

## Sudo

Perintah sudo atau "super user do" berfungsi untuk melakukan suatu
command sebagai

user root tanpa harus login ke user root

## Cp

Cp perintah untuk meng-copy file

## Chown

Chown berfungsi untuk merubah kepemilikan suatu file

## Usermod

Usermod digunakan untuk merubah informasi dari suatu user seperti group,

nama, lokasi home directory, dll

## Chmod

Command chmod berfungsi merubah permission atau izin akses suatu file

antara lain read, write, dan execute

# Merubah IP server ubuntu dan tes koneksi IP baru dengan SSH

# Step 1

Pertama kita install OpenSSH server terlebih dahulu dengan command `sudo
apt install openssh-server`

![](./images/media/image1.png)

Bila proses instalasi selesai, aktifkan dahulu service SSH dengan
command

`sudo systemctl enable ssh`

![](./images/media/image2.png)

Kemudian ubah permission UFW SSH menjadi allow agar remote server bisa
login dengan command `sudo ufw allow ssh`

![](./images/media/image3.png)

# Step 2

Masukkan command `sudo nano /etc/netplan/00-installer-config.yaml`
![](./images/media/image4.png)

# Step 3

Isikan parameter IP, gateway, dan DNS sesuai kebutuhan. Bila selesai
save dengan menekan ctrl+o atau exit dan save dengan menekan ctrl + X
lalu yes.

![](./images/media/image5.png)

# Step 4

Kemudian apply parameter tadi yang sudah diisi dengan command

`Sudo netplan apply`

![](./images/media/image6.png)

# Step 5

Login SSH dengan IP yang sudah dirubah tadi

`Ssh <papavins@192.168.1.100>`

![](./images/media/image7.jpeg)

# Step 6

Lakukan tes koneksi dengan ping dan traceroute, bila traceroute belum
terinstall maka bisa menggunakan command

Sudo apt install inetutils-traceroute

![](./images/media/image8.jpeg)

# Instalasi Apache2 dan LocalTunnel

# Step 1

Install apache2 dengan command

`sudo apt-get install apache2`

![](./images/media/image9.png)

# Step 2

Kemudian cek status keaktifan apache2, bila service apache2 berjalan
akan muncul status active (running). Masukkan command

`systemctl status apache2`

![](./images/media/image10.png)

# Step 3

Cek apakah service apache2 berjalan dengan memasukkan IP melalui browser

![](./images/media/image11.jpeg)

# Step 4

Kemudian untuk instalasi localtunnel pastikan curl sudah terinstall
dengan command

`Curl`

![](./images/media/image12.png)

Bila not found, lakukan instalasi curl dengan command

`sudo apt-get install curl`

![](./images/media/image13.png)

# Step 5

Setelah itu install node.js agar localtunnel bisa menjalankan kodenya,
caranya dengan menginstall nvm dengan command

`curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh
| bash`

![](./images/media/image14.png)

# Step 6

Jika sudah install node versi 14 dengan command

`nvm install 14`

![](./images/media/image15.png)

# Step 7

Kemudian cek versi node yang sudah terinstal dengan command

`Npm -v`

`Node -v`

![](./images/media/image16.png)

# Step 8

Install localtunnel dengan command

`npm install -g localtunnel`

![](./images/media/image17.png)

# Step 9

Buat tunnel http apache port 80 dengan command

`lt --port 80`

![](./images/media/image18.png)

# Step 10

Cek URL yang diberikan kedalam browser

![](./images/media/image19.png)
