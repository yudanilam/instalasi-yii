# instalasi-yii
Instalasi yii 

kebutuhan yang diperlukan:
minimum untuk membuat projek yii, web server kamu mendukung PHP 5.4.0
koneksi jaringan internet wajib
composer telah terinstall kalau belum lihat cara menginstall composer via linux maupun windows

Instalasi menggunakan via composer
1 Instalasi melalui windows 
  jika kalian menggunakan web server xampp maka instalasi yii nya sebagai berikut :
  buka terminal command ketik rumus seperti ini:
  
  composer global require "fxp/composer-asset-pluggin:~1.1.1"
  
  Note :
  Kamu harus berada di drive tempat penyimpan xampp kamu contoh di drive c maka penulisan didalam command 
  C:\xampp\htdoc\composer global require "fxp/composer-asset-pluggin:~1.1.1"
  jangan lupa masukkan token github kamu, jika belom ada sebaiknya kamu buat account di github, bila github sudah jadi
  generate new token nah setelah dibuat baru kamu masukkan token tersebut pada saat melakukan composer global require    "fxp/comopser-asset-pluggin:~1.1.1"
  
  setelah itu kamu gunakan rumus kedua untuk membuat projek yii kamu ;
  
  composer create-project --prefer-dist yiisoft/yii2-app-advanced nama_aplikasiyangingindibuat 
  contoh:
  composer create-project --prefer-dist yiisofy/yii2-app-advanced myweb
  
  NOte :
  Mengetikan rumus diatas harus tetap berada di xampp/htdocs tempat dimana xampp kamu letakkan, kebutalan saya meletakkan nya
  C:\xampp\htdocs\composer create-project --prefer-dist yiisoft/yii2-app-advanced myweb
  setelah kamu mengetik rumus di atas tunggulah beberap menit sabar............
  
2 Instalasi melalui linux versi ubuntu atau linux mint
  web server yang telah kalian install baik secara manual maupun menggunakan xampp, atau nginx yang penting letak folder htdocs atau     www harus diingat kebutulan saya menggunakn apache dengan install di linux secara manual, dimana tempat menyimpan project saya berada
  di /var/wwww
  
  caranya sama seperti di windows namun 
  hanya kamu harus masuk ke super root:
  
  l@linux ~$ su
  password:
  
  atau 
  l@linux ~$ cd /var/www/ su
  Password :
  linux www # composer global require "fxp\composer-asset-plugin:~1.1.1"
  change current directory to /root/.config/composer
  ./composer .json has been update
  loading composer repositories with package information
  Updating depedencies (including require-dev)
   - Installing fxp/composer-asset-pluggin (v1.1.2)
   - Downloading : 100 %
   - ...
   - ...
   - ..
   - dst
   
 setelah itu nanti dia minta token github:jika kalian sudah membuat account github lansung copykan ke terminal

 selanjutnya ketikkan rumus dibawah ini :
 
 composer global require "fxp/composer-asset-pluggin:~1.1.1"
 
 caranya sama seperti kamu instalasi lewat windows
 contohnya dil inux seperti ini:
 linux www # composer create-project --prefer-dist yiisoft/yii2-app-advanced myweb
 
 tunggu sampai selesai
 
 setelah instalasi selesai.
 
 PREPARING APLIKASI
 setelah selesai instalasi lanjut kita membuat initalize caranya
 masuk kedalam folder projecy yang kita buat, kebetulan saya menggunakan linux maka caranya
 
 linux www # cd myweb
 linux myweb # php init
 Yii Application Initialization Tool v1.0
 which envirotment do you want the application to be initializad in?
 [0] Development
 [1] Production
 
 Your choice [0-1, or "q" to quit] 0
 Initialize the application under 'Development' environment? [yes|no] ketikkan y
 start initialization..
 
 nah web project yang kalian buat sudah bisa running.....
 coba dibuka : localhost/myweb/frontend/web/index.php
 
 UNTUK SET DOCUMENT ROOTS WEB SERVER 
 
 untuk frontend /path/to/nm_aplikasimu/frontend/web dan menjadi URL http://frontend.dev/
 untuk backend /path/to/nm_aplikasimu/backend/web dan menjadi URL http://backend.dev/
 
 dengan cara apache:
 
 <VirtualHost *:80>
       ServerName frontend.dev
       DocumentRoot "/path/to/nm_aplikasimu/frontend/web/
    
    <directory "/path/to/nm_aplikasimu/frontend/web/
      
       #use mod_rewrite for pretty URL support
      
       RewriteEngine on
      
       #if a directory or a file exits, use the request directly
       RewriteCond %{REQUEST_FILENAME} !-f
       RewriteCond %{REQUEST_FILENAME} !-d
      
       #Otherwise forward the request to index.php
       
       #use index.php as index file
       DirectoryIndex index.php
       
       #....other settings...
    </Directory>
  </VirtualHost *:80>
  
 
 
 
 <VirtualHost *:80>
      ServerName backend.dev
      DocumentRoot "/path/to/nm_aplikasimu/backend/web/
    
    <directory "/path/to/nm_aplikasimu/backend/web/
       #use mod_rewrite for pretty URL support
       RewriteEngine on
       #if a directory or a file exits, use the request directly
       RewriteCond %{REQUEST_FILENAME} !-f
       RewriteCond %{REQUEST_FILENAME} !-d
       #Otherwise forward the request to index.php
       
       #use index.php as index file
       DirectoryIndex index.php
       
       #....other settings...
    </Directory>
  </VirtualHost *:80>
  
 kemudian rubah hosts file ke domain server kamu:
 dengan cara:
 untuk di windows: c:\Windows\System32\Drivers\etc\hosts
 untuk di linux : /etc/hosts
 
 tambahkan baris dibawah ini:
 127.0.0.1 frontend.dev
 127.0.0.1 backend.dev
 
 untuk menggunakan login kamu harus first sign up dulu masukkan email, address,, username dan password, setelah itu kamu 
 login menggunakan email dan passwordnya
  
  
  Thanks yii2-app-advanced
 
 
 



  
