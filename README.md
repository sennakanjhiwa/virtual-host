# virtual-host
Setting vhost dan lain-lain

sudo systemctl start apache2
sudo systemctl start nginx

1. Mengelola Versi PHP (Switching)
sudo update-alternatives --config php

2. Pindah versi PHP di web server (misal, Apache): Jika kamu menggunakan web server seperti Apache, kamu juga perlu mengaktifkan modul PHP yang sesuai. Misalnya, untuk menggunakan PHP 7.4:
sudo a2enmod php7.4
sudo a2dismod php8.2
sudo a2dismod php8.3
sudo systemctl restart apache2

CATATAN: Periksa Mod Rewrite: Pastikan mod_rewrite diaktifkan pada Apache. Aktifkan dengan perintah:
sudo a2enmod rewrite
sudo systemctl restart apache2

4. Pengaturan Host
sudo nano /etc/hosts
Tambahkan baris berikut:
127.0.0.1   namafolder.test

3. Virtual host apache jadi .test
Pastikan mod_vhost_alias Aktif
sudo a2ensite auto-vhost
sudo systemctl restart apache2

5. Virtual host nginx jadi .test
sudo ln -s /etc/nginx/sites-available/auto-vhost /etc/nginx/sites-enabled/

6. Ubah versi php-fpm nginx
sudo nano /etc/nginx/sites-available/auto-vhost

7. Mematikan keyboard laptop
xinput list
xinput disable 20
