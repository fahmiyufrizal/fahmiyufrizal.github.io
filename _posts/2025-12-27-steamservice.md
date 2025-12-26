---
layout: post
title: Steam Client Service without SU
---
# Steam Client Service without SU

Cara menginisiasi "Steam Client Service" tanpa superuser (or atleast tanpa steam login)




## Persiapan

Server harus melakukan update Steam Client sampai latest

## Langkah-langkah
Langkah-langkah dapat disesuaikan sesuai dengan kondisi diskless di net masing-masing

- Buat sebuah folder bernama Steamservice di gamedisk
- buat sebuah file bernama "unload.bat" (tanpa petik)
- edit, lalu isikan dengan kode berikut :
```sh
@echo off
net stop "Steam Client Service"
mkdir Steam
xcopy /s "C:\Program Files (x86)\Common Files\Steam" "%~dp0Steamservice" /-y
rd /s /q "C:\Program Files (x86)\Common Files\Steam"
mklink /J "C:\Program Files (x86)\Common Files\Steam" "%~dp0Steamservice"
```
- Setelah itu, jalankan unload.bat nya
- Setelah selesai, edit Diskless script yang kamu punya (misal jika bawaan CCBoot, bisa memakai bawaannya dengan buka options > run batch command at client yang sudah dicentang)
- Isikan dengan kode berikut :
```sh
@echo off
sc CREATE "Steam Client Service" displayname= "Steam Client Service" start= demand binpath= "\"%~dp0Steamservice"\SteamService.exe\" /RunAsService"
```
- Test di client

## Jika client tidak ada diskless script?
Setelah melakukan unload, buat sebuah file bernama "steamclientservice.bat", isikan dengan kode berikut :
```sh
@echo off
sc CREATE "Steam Client Service" displayname= "Steam Client Service" start= demand binpath= "\"%~dp0Steamservice"\SteamService.exe\" /RunAsService"
```
lalu jalankan steamclientservice.bat saat mode superuser di client
