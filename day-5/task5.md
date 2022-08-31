# Day 5

## CI/CD dengan Cloudflare Pages

Cloudflare adalah salah satu Content Delivery (CD) yang menyediakan
layanan cloudflare pages, yang digunakan developer untuk kolaborasi
pengembangan front-end dan deploy website .

# Deploy aplikasi wayhub-frontend ke Cloudflare Pages menggunakan Github

## Step 1

Step pertama lakukan create fork repository wayhub-frontend dengan
membuka repository github
https://github.com/dumbwaysdev/wayshub-frontend

![](./images/media/image1.png)

## Step 2

Kemudian isi repository name dan description yang diinginkan, bila sudah
klik create fork

![](./images/media/image2.png)

## Step 3

Langkah berikutnya kita hubungan repository Github dengan Cloudflare
Pages, masuk ke dashboard Cloudflare pilih menu Pages kemudian connect
to Git kemudian Connect Github

![](./images/media/image3.png)

![](./images/media/image4.png)

## Step 4

Pilih repository wayhub-frontend kemudian begin setup

![](./images/media/image5.png)

Isikan project name dan production branch

![](./images/media/image6.png)

Untuk build settings disini kita pilih framework preset "create react
app" kemudian build command "npm run build" terakhir build output
directory /build

![](./images/media/image7.png)

Tunggu proses building dan deploying selesai

![](./images/media/image8.png)

Bila sudah success kita klik continue to project

![](./images/media/image9.png)

![](./images/media/image10.png)

Kita cek hasil deployment webnya

![](./images/media/image11.png)

## Test CI/CD code aplikasi

Disini kita akan mencoba testing perubahan source code untuk mengecek
apakah CI/CD berjalan dan bisa secara otomatis melakukan deployment

Pertama kita buka repository github wayhub-frontend/public/index.html

![](./images/media/image12.png)

Kita coba ganti title web nya

![](./images/media/image13.png)

![](./images/media/image14.png)

Setelah commit change kita cek apakah CI/CD berjalan saat merubah source
code

![](./images/media/image15.png)

![](./images/media/image16.png)
