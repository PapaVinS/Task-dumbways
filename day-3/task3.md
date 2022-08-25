# Day 3

## Application

Definisi dari aplikasi adalah perangkat lunak yang dibuat untuk
mengerjakan fungsi tertentu yang dapat dioperasikan oleh pengguna

# Pembuatan aplikasi sederhana Node.js

## Step 1

Buat direktori untuk node.js dengan command

`Mkdir nodejs`

![](./images/media/image1.png)

## Step 2

Untuk menjalankan aplikasi berbasis Node.js diperlukan untuk membuat
environment terlebih dahulu, jalankan command dibawahi ini untuk
menginstall package.json

`Npm init -y`

![](./images/media/image2.png)

## Step 3

Untuk menginstall aplikasi backend yang sederhana, install express.js
menggunakan command

`Npm install express \--save`

![](./images/media/image3.png)

## Step 4

Buat file index.js kemudian edit dengan text editor dengan command

`Touch index.js`

`Nano index.js`

![](./images/media/image4.png)

## Step 5

Masukkan script dibawah kemudian save

const express = require(\"express\");

const app = express();

const port = 3000;

app.get(\"/\", (req, res) =\> {

res.send(\"Hello World!\");

});

![](./images/media/image5.png)

## Step 6

Tinggal mejalankan aplikasi dengan command

`Node index.js`

![](./images/media/image6.png)

## Step 6

Akses IP server menggunakan port 3000 melalui browser

![](./images/media/image7.png)

# Pembuatan aplikasi sederhana dengan Go

## Step 1

Tahap pertama install engine Go menggunakan command

`wget https://golang.org/dl/go1.16.5.linux-amd64.tar.gz && sudo su`

![](./images/media/image8.png)

Kemudian masukkan command

`rm -rf /usr/local/go && tar -C /usr/local -xzf
go1.16.5.linux-amd64.tar.gz && exit`

![](./images/media/image9.png)

## Step 2

Kemudian buka file .bashrc dengan text editor nano .bashrc dan masukkan
line script berikut di akhir file

![](./images/media/image10.png)

![](./images/media/image11.png)

## Step 3

Jika sudah cek instalasi engine Go lalu buat file index.go

![](./images/media/image12.png)

## Step 4

isikan file index.go dengan script

`package main

import \"fmt\"

func main() {

fmt.Println(\"Hello World!\")

}`

![](./images/media/image13.png)=

Step 5

Jalankan aplikasi dengan command
`go run index.go`

g![](./images/media/image14.png)

Step 6

Build aplikasi dengan command

`go build index.go`

![](./images/media/image15.png)

Jalankan aplikasi dengan command

`./index`

![](./images/media/image16.png)

# Membuat aplikasi sederhana Python

## Step 1

Ubuntu secara default sudah terinstall python, pastikan terlebih dahulu
dengan command

`python3 -v`

Kemudian install package manager python pip dengan menggunakan command

`sudo apt install python3-pip`

![](./images/media/image17.png){width="6.268055555555556in"
height="4.25in"}Step 2

Buat aplikasi web dengan framework flask, untuk instalasinya melalui pip
dengan command

`pip install flask`
![](./images/media/image18.png)

## Step 3

buat file index.py kemudian isikan dengan script

from flask import Flask

app = Flask(\_\_name\_\_)

\@app.route(\"/\")

def helloworld():

return \"Hello World\"

if \_\_name\_\_ == \"\_\_main\_\_\":

app.run()

![](./images/media/image19.png)*Pada akhir script app.run() gunakan
app.run(host="0.0.0.0") untuk menarget IP address dikarenakan flask
secara default menarget localhost. Maksud dari 0.0.0.0 adalah alamat
non-routable yang menggambarkan target yang tidak valid atau tidak
dikenal*

## Step 4

Run aplikasi dengan menggunakan command

`python3 index.py`

![](./images/media/image20.png)

## Step 5

Buka IP server menggunakan port 5000 melalui browser

![](./images/media/image21.png)

# Menggunakan PM2 dan LocalTunnel untuk
menjalankan aplikasi

## Step 1

Pertama install PM2 dengan menggunakan command

`npm install <pm2@latest> -g`

![](./images/media/image22.png)

# Step 2

pastikan PM2 sudah terinstall denga command

`pm2 -v`

![](./images/media/image23.png)

## Step 3

Run aplikasi node yang telah dibuat dengan command

`pm2 start app-nodejs/index.js`

![](./images/media/image24.png)

## Step 4

Run aplikasi python dengan menggunakan command

`pm2 start python/index.py ---interpreter python3`

![](./images/media/image25.png)

## Step 5

Kemudian cek melalui browser aplikasi sudah berjalan

![](./images/media/image26.png)

## Step 6

Jalankan command berikut untuk melakukan akses localtunnel ke port 3000
aplikasi nodejs dan port 5000 aplikasi python

`lt --port 5000`

`lt -port 3000`

![](./images/media/image27.png)

![](./images/media/image28.png)

![](./images/media/image29.png)
![](./images/media/image30.png)
