# Docker Pada Windows

Untuk mengakses docker cli dapat menggunakan
- command prompt
- powershell
- Ubuntu apps (lokasi working directory /home/user)

Menampilkan wsl yang terinstall
```
$ wsl --list
$ wsl --list --online
```

Masuk ke powershell melalui command prompt
```
$ wsl
```

Mencari lokasi wsl, buka file browser lalu ketik
```
\\wsl.localhost
```

Lokasi volume dari docker desktop, jika membuat volume, maka filenya ada pada
```
\\wsl.localhost\docker-desktop\mnt\docker-desktop-disk\data\docker\volumes
```

*portainer.io* --> web based untuk docker gui, bisa lewat extension atau docker image
