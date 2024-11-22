# Instalasai dan Konfigurasi Nginx

Memperoleh informasi lokasi nginx.conf
``` bash
$ nginx -V
```

## Konfigurasi .yaml file

Menggunakan jumlah core sesuai yang tersedia pada server
```
worker_processes auto;
```

Jumlah koneksi per worker 
```
events {
   worker_connections 1024;
}
```

Nama server 
```
server {
   listen 8080;
   server_name localhost
}

localhost 127.0.0.1
```

Membuat sertifikasi ssl untuk lokal
```
$ mkidir nginx-cert
```

```
$ cd nginx-cert
$ openssl
```

Konfigurasi ssl pada .yaml file
```
server {
   listen 443 ssl;
   server_name localhost;
   
   ssl_certificate <lokasi .crt>;
   ssl_certificate_key <lokasi .key>;
}

server {
   listen 8080;
   server_name localhost;
   
   location / {
      return 301 https://$host$request_uri;
   }
}
```

```
$ nginx -s reload
```
