# Day 2

## Install database menggunakan MySQL

Sebelum kita masuk ke tahap instalasi, kita buat terlebih dahulu
instance untuk server database di
idcloudhost![](./images/media/image1.png)

Kita tes login apakah sudah bisa diakses

![](./images/media/image2.png)

Jika sudah baru kita bisa lakukan instalasi MySQL

## Step 1

Pertama kita install mysql menggunakan command `sudo apt-get update &&
sudo apt-get install -y mysql-server`

![](./images/media/image3.png)

## Step 2

Kemudian masuk mysql menggunakan user root

`Sudo mysql`

![](./images/media/image4.png)

Kita lakukan alter ke user root agar bisa melakukan step setup mysql

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password
by '<password>';`

![](./images/media/image5.png)

## Step 3

Kita exit mysql kemudian kita masukkan command `mysql_secure_installation`

![](./images/media/image6.png)

## Step 4

Kemudian kita buat user khusus database dumbflix, kita masuk ke mysql
dahulu

`mysql -u root -p`

`CREATE USER '<username>'@'%' IDENTIFIED BY '<password>';`

`CREATE DATABASE <database-name>;`

`GRANT ALL ON <database-name>.* TO '<username>'@'%';`

![](./images/media/image7.png)

Jika sudah kita tes user dan database sudah bisa diakses

`mysql -u dumbflix -p`

`use dumbflix`

`show tables;`

`select database() from dual;`

![](./images/media/image8.png)

## Step 5

Setelah itu kita exit mysql dan buka file
/etc/mysql/mysql.conf.d/mysqld.cnf

`sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf`

kemudian rubah isi di baris bind-addres dan mysqlx-bind-address menjadi

`bind-address = 0.0.0.0

mysqlx-bind-address = 0.0.0.0`

fungsinya aga database bisa terbaca dan terakses dari IP mana
saja.![](./images/media/image9.png)

## Step 6

Setelah selesai kita restart mysql.service `sudo systemctl restart
mysql.service`

Lalu cek status mysql.service s`udo systemctl status mysql.service`

![](./images/media/image10.png)

## Setup aplikasi backend dan integrasi aplikasi dengan database

## Step 1

Kita clone repository aplikasi backend dumbflix

git clone <https://github.com/dumbwaysdev/dumbflix-backend.git>

![](./images/media/image11.png)

## Step 2

Kita ikuti ketentuan environment dari file readme.md

![](./images/media/image12.png)

Kita copy .env.example ke .env

![](./images/media/image13.png)

Kita sesuaikan isi file
config.json
![](./images/media/image14.jpeg)

## Step 3

Kita install mysql-client didalam backend

`Sudo apt-get install`
mysql-client![](./images/media/image15.png)

Kemudian kita import database menggunakan command

`mysql -h <ip-database? -u dumbflix -p -D dumbflix < dumbflix.sql`

![](./images/media/image16.png)

Kita cek di tables database apakah sudah terimport

![](./images/media/image17.png)

## Step 4

Kita konfigurasi url api di direktori
/dumbflix-frontend/src/config/api.js![](./images/media/image18.png)

## Step 5

Kita run aplikasi menggunakan `pm2 start ecosystem.config.js`

![](./images/media/image19.png)

## Step 6

Kita coba fitur registrasi
dumbflix![](./images/media/image20.png)![](./images/media/image21.png)

## Setup SSL dengan Certbot

Pertama kita install snapd

`sudo apt-get install snapd`

![](./images/media/image22.png)

Kemudian `sudo snap install core; sudo snap refresh core`

![](./images/media/image23.png)

Setelah itu `sudo apt-get install certbot python3-certbot-nginx`

![](./images/media/image24.png)

Jika sudah jalankan command instalasi certificate `sudo certbot --nginx`

![](./images/media/image25.png)

Kita buka di browser kita cek certificate sudah terpasang

![](./images/media/image26.png)![](./images/media/image27.png)
