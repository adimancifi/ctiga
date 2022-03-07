# CiFireCMS - Gratis Rasa Premium
CiFireCMS adalah platform CMS open source gratis Indonesia dibuat menggunakan framework CodeIgniter3 dengan konsep yang menarik dan mudah digunakan oleh siapa saja.


## Minimum System Requirements
```
+--------------+----------------+
|  System      |  Version       |
+--------------+----------------+
|  Web server  |  Apache 2.4.x  |
|  PHP         |  7.3.x, 5.6.x  |
|  MySQL       |  5.7.x         |
|  MariaDB     |  10.3.x        |
+--------------+----------------+
```


## PHP Extension
```
+--------------+----------+
|  Extension   |  Config  |
+--------------+----------+
|  pdo_mysql   |  ON      |
|  pdo_sqlite  |  ON      |
|  pdo_sqlite  |  ON      |
|  json        |  ON      |
|  fileinfo    |  ON      |
|  intl        |  ON      |
+--------------+----------+
```


## Dowwnload via composer
* Untuk mengambil rilis terakhir :
```
composer create-project cifirecms/cifirecms cifirecms-project
```

* Untuk mengambil paket dari master (kemungkinan terdapat error/bugs) :
```
composer create-project cifirecms/cifirecms:dev-master cifirecms-project
```


## Permission
Ubah user permission folder dan file berikut menjadi ``0777``.
```
cifirecms
├── app/
│   ├── cache  -->  777
│   └── config
│   │   └── routes
│   │       └── slug_routes.php  -->  777
│   ├── controllers  -->  777 (semua folder dan file)
│   ├── language  -->  777 (semua folder dan file)
│   ├── logs  -->  777
│   ├── models  -->  777 (semua folder dan file)
│   └── views
│       ├── mod  -->  777 (semua folder dan file)
│       ├── themes  -->  777 (semua folder dan file)
│       └── meta_social.php  -->  777
└── public  -->  0777 (semua folder dan file)
```


## .htaccess
Standard **.htaccess** configuration.
```
RewriteEngine On
RewriteCond $1 !^(index\.php|resources|robots\.txt)
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^(.*)$ index.php/$1 [L,QSA]
```

Untuk menentukan web anda di akses dengan alamat **http** atau **https** silahkan ubah konfigurasi file **.htaccess** dan tambahkan kode berikut di bawah baris kode ``RewriteEngine On``.


#### Redirect HTTP to HTTPS

```
# non-www to www.
RewriteCond %{HTTPS} off [OR]
RewriteCond %{HTTP_HOST} !^www\. [NC]
RewriteCond %{HTTP_HOST} ^(?:www\.)?(.+)$ [NC]
RewriteRule ^ https://www.%1%{REQUEST_URI} [L,NE,R=301]

# www to non-www.
RewriteCond %{HTTPS} off [OR]
RewriteCond %{HTTP_HOST} ^www\. [NC]
RewriteCond %{HTTP_HOST} ^(?:www\.)?(.+)$ [NC]
RewriteRule ^ https://%1%{REQUEST_URI} [L,NE,R=301]
```


#### Redirect HTTPS to HTTP
```
# non-www to www.
RewriteCond %{HTTPS} on [OR]
RewriteCond %{HTTP_HOST} !^www\. [NC]
RewriteCond %{HTTP_HOST} ^(?:www\.)?(.+)$ [NC]
RewriteRule ^ http://www.%1%{REQUEST_URI} [L,NE,R=301]

# www to non-www.
RewriteCond %{HTTPS} on [OR]
RewriteCond %{HTTP_HOST} ^www\. [NC]
RewriteCond %{HTTP_HOST} ^(?:www\.)?(.+)$ [NC]
RewriteRule ^ http://%1%{REQUEST_URI} [L,NE,R=301]
```


### Environment
Jika web sudah siap di online-kan silahkan ubah kode pada ``.env`` cari code ``CI_ENV=development`` edit menadi ``CI_ENV=production``


## Backend
* Untuk mengakses halaman administrator kunjungi link ``http://your-web-domain/l-admin``
* Masukan Username dan Password seperti pada awal instalasi.


## Official Links
* Official       : https://www.cifirecms.org
* GitHub         : https://github.com/CiFireCMS
* Facebook Page  : https://web.facebook.com/cifirecms
* Facebook group : https://web.facebook.com/groups/cifirecms


## License
CiFireCMS is licensed under the MIT License.