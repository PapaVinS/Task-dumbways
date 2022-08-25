# Day 4

## Version Control System (VCS)

Git adalah salah satu sistem pengontrol versi (Version Control System)
yang telah digunakan oleh para developer untuk dapat mengembangkan
software secara bersamaan pada proyek perangkat lunak

# Contoh Command Git

## Git log

Digunakan untuk meninjau dan membaca riwayat segala sesuatu yang terjadi
pada repositori.

![](./images/media/image1.png)

## Git checkout

perintah untuk beralih antar branch yang
ada.![](./images/media/image2.png)

## Membuat environtment Git di Ubuntu

## Konfigurasi user, email dan SSH key

## Step 1

Cek terlebih dahulu apakah git sudah terinstall dengan command `git
--version`
![](./images/media/image3.png)

## Step 2

Mengisi email github dan username github dengan command

`Git config --global user.email "\<email github\>"`

`Git config --global user.name "\<username github\>"`

![](./images/media/image4.png)

## Step 3

Membuat key SSH dengan command ssh-keygen

![](./images/media/image5.png)

## Step 4

Buka file \~/.ssh/id_rsa.pub yang sudah digenerate dari command
ssh-keygen dengan command

`Cat /home/papavins/.ssh/id_rsa.pub`

![](./images/media/image6.png)

## Step 5

Buka github.com kemudian pada bagian pojok kanan atas klik profil
kemudian masuk ke menu setting

![](./images/media/image7.png)

## Step 6

Pilih SSH dan GPG keys

![](./images/media/image8.png)

## Step 7

Isikan title ssh keys dan paste key public yang sudah digenerate tadi

![](./images/media/image9.png)

Step 8

Lakukan cek koneksi ke github menggunakan command

`Ssh -T git@github.com`

![](./images/media/image10.png)

# Membuat dan mengisi repository dan branch

## Step 1

Masuk ke direktori yang akan diupload kedalam github kemudian buat
folder .git dengan command `git init`

![](./images/media/image11.png)

## Step 2

Kemudian buat file .gitignore untuk memilih file atau folder yang tidak
diupload ke github, sebagai contoh disini tidak mengupload folder
node_modules

`Touch .gitignore`

`Echo "node_modules" \> .gitignore`

![](./images/media/image12.png)

## Step 3

Tahap berikutnya memilih file yang akan memasuki fase staged dimana file
yang akan diupload untuk di commit ke repository dengan menggunakan
command

`Git add \<folder/file\>`

![](./images/media/image13.png)

## Step 4

Selanjutkan Kembali ke web github, pada pojok kanan atas klik ikon
tambah (+) kemudikan pilih new repository

![](./images/media/image14.png)

## Step 5

Beri nama repository kemudian creat repository

![](./images/media/image15.png)

## Step 6

Kemudian copy key SSH repository yang sudah dibuat

![](./images/media/image16.png)

## Step 7

Kembai ke terminal lalu tambahkan remote github dengan key SSH yang
sudah di copy tadi kemudian cek remote yang sudah terdaftar di
repository local menggunakan command

`Git remote add origin \<key SSH github repository\>`

`Git remote -v`

![](./images/media/image17.png)

## Step 8

Selanjutnya lakukan commit untuk menulis file kedalam repository local
dengan command

`Git commit -m "first
commit"`

![](./images/media/image18.png)

## Step 9

Kemudian lakukan push pada file yang di repository lokal ke repository
github dengan command

`Git push \<remote-name\> \<branch-name\>`

![](./images/media/image19.png)

Cek web github bila sudah melakukan push

![](./images/media/image20.png){width="6.268055555555556in"
height="2.877083333333333in"}

# Step 10

Buat branch development, staging dan production dengan command

`Git branch development`

`Git branch staging`

`Git branch production`

Lalu cek daftar branch `Git branch -a`

![](./images/media/image21.png)

Untuk memilih antar branch menggunakan command

`Git checkout \<nama branch\>`

![](./images/media/image2.png)
