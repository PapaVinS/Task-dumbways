Day 4

Version Control System (VCS)

Git adalah salah satu sistem pengontrol versi (Version Control System)
yang telah digunakan oleh para developer untuk dapat mengembangkan
software secara bersamaan pada proyek perangkat lunak

Contoh Command Git

Git log

Digunakan untuk meninjau dan membaca riwayat segala sesuatu yang terjadi
pada repositori.

![](./images/media/image1.png){width="6.261111111111111in"
height="4.24375in"}

Git checkout

perintah untuk beralih antar branch yang
ada.![](./images/media/image2.png){width="6.261111111111111in"
height="4.461111111111111in"}

Membuat environtment Git di Ubuntu

Konfigurasi user, email dan SSH key

Step 1

Cek terlebih dahulu apakah git sudah terinstall dengan command git
\--version![](./images/media/image3.png){width="4.991532152230971in"
height="3.556522309711286in"}

Step 2

Mengisi email github dan username github dengan command

Git config --global user.email "\<email github\>"

Git config --global user.name "\<username github\>"

![](./images/media/image4.png){width="6.261111111111111in"
height="4.461111111111111in"}

Step 3

Membuat key SSH dengan command ssh-keygen

![](./images/media/image5.png){width="5.391304680664917in"
height="3.8413648293963254in"}

Step 4

Buka file \~/.ssh/id_rsa.pub yang sudah digenerate dari command
ssh-keygen dengan command

Cat /home/papavins/.ssh/id_rsa.pub

![](./images/media/image6.png){width="6.261111111111111in"
height="4.461111111111111in"}

Step 5

Buka github.com kemudian pada bagian pojok kanan atas klik profil
kemudian masuk ke menu setting

![](./images/media/image7.png){width="2.165277777777778in"
height="5.147916666666666in"}

Step 6

Pilih SSH dan GPG keys

![](./images/media/image8.png){width="6.261111111111111in"
height="2.84375in"}

Step 7

Isikan title ssh keys dan paste key public yang sudah digenerate tadi

![](./images/media/image9.png){width="6.261111111111111in"
height="2.84375in"}

Step 8

Lakukan cek koneksi ke github menggunakan command

Ssh -T git@github.com

![](./images/media/image10.png){width="6.261111111111111in"
height="4.461111111111111in"}

Membuat dan mengisi repository dan branch

Step 1

Masuk ke direktori yang akan diupload kedalam github kemudian buat
folder .git dengan command git init

![](./images/media/image11.png){width="6.261111111111111in"
height="4.461111111111111in"}

Step 2

Kemudian buat file .gitignore untuk memilih file atau folder yang tidak
diupload ke github, sebagai contoh disini tidak mengupload folder
node_modules

Touch .gitignore

Echo "node_modules" \> .gitignore

![](./images/media/image12.png){width="6.261111111111111in"
height="4.461111111111111in"}

Step 3

Tahap berikutnya memilih file yang akan memasuki fase staged dimana file
yang akan diupload untuk di commit ke repository dengan menggunakan
command

Git add \<folder/file\>

![](./images/media/image13.png){width="6.261111111111111in"
height="4.461111111111111in"}

Step 4

Selanjutkan Kembali ke web github, pada pojok kanan atas klik ikon
tambah (+) kemudikan pilih new repository

![](./images/media/image14.png){width="2.3826388888888888in"
height="2.009027777777778in"}

Step 5

Beri nama repository kemudian creat repository

![](./images/media/image15.png){width="6.268055555555556in"
height="4.969444444444444in"}

Step 6

Kemudian copy key SSH repository yang sudah dibuat

![](./images/media/image16.png){width="4.104166666666667in"
height="3.6875in"}

Step 7

Kembai ke terminal lalu tambahkan remote github dengan key SSH yang
sudah di copy tadi kemudian cek remote yang sudah terdaftar di
repository local menggunakan command

Git remote add origin \<key SSH github repository\>

Git remote -v

![](./images/media/image17.png){width="6.261111111111111in"
height="4.461111111111111in"}

Step 8

Selanjutnya lakukan commit untuk menulis file kedalam repository local
dengan command

Git commit -m "first
commit"![](./images/media/image18.png){width="6.261111111111111in"
height="4.461111111111111in"}

Step 9

Kemudian lakukan push pada file yang di repository lokal ke repository
github dengan command

Git push \<remote-name\> \<branch-name\>

![](./images/media/image19.png){width="6.260416666666667in"
height="4.458333333333333in"}

Cek web github bila sudah melakukan push

![](./images/media/image20.png){width="6.268055555555556in"
height="2.877083333333333in"}

Step 10

Buat branch development, staging dan production dengan command

Git branch development

Git branch staging

Git branch production

Lalu cek daftar branch Git branch -a

![](./images/media/image21.png){width="6.260416666666667in"
height="4.458333333333333in"}

Untuk memilih antar branch menggunakan command

Git checkout \<nama branch\>

![](./images/media/image2.png){width="6.260416666666667in"
height="4.458333333333333in"}
