# Windows Tips & Trick

## Melihat versi *bit* windows.

Untuk melihat apakah OS windows anda 64bit atau 32bit, buka Control panel, pilih System and Security, lalu pilih System. atau tekan Windows + Pause/Break pada keyboard. versi bit windows akan muncul pada **System Type**. Sebagai contoh, dibawah ini adalah tampilan untuk sistem windows 64bit.

![https://www.dropbox.com/s/jt8ujvnynpp81t7/Screenshot%202015-12-19%2012.41.03.png?raw=1](https://www.dropbox.com/s/jt8ujvnynpp81t7/Screenshot%202015-12-19%2012.41.03.png?raw=1)

## Menjalankan Command Prompt sebagai *Administrator*

Untuk menjalankan command prompt sebagai administrator, lakukan langkah berikut:

### Windows 7

`Start -> All Programs -> Accesories -> Command Prompt`
klik kanan shortcut, lalu pilih *run as administrator*.

### Windows 8 keatas

Tekan `Windows + X` pada keyboard, lalu pilih Command Prompt (Admin).

## NPM3

Untuk melakukan upgrade NPM, silahkan ikuti langkah berikut.

buka command prompt, lalu jalankan perintah berikut untuk menambahkan [npm-windows-upgrade](https://github.com/felixrieseberg/npm-windows-upgrade):

```sh
npm install -g npm-windows-upgrade
```

setelah itu, buka powershell (Start -> Windows Powershell -> Windows Powershell - jika tidak ada, cukup cari **powershell** di startmenu), lalu jalankan perintah berikut pada window powershell:

```sh
npm-windows-upgrade
```

setelah selesai, tutup window powershell dan buka lagi command prompt. jalankan perintah

```sh
npm version
```

apabila hasilnya adalah `NPM@3.x.x`, maka NPM telah berhasil di update ke versi 3.

Apabila masih ada masalah, atau hasilnya adalah `NPM@2`/`NPM@1`, maka anda harus melakukan update secara manual. silahkan lihat caranya pada halaman berikut: [https://github.com/npm/npm/wiki/Troubleshooting#upgrading-on-windows](https://github.com/npm/npm/wiki/Troubleshooting#upgrading-on-windows).

## Melakukan instalasi *node version manager*

Node version manager digunakan untuk bisa melakukan instalasi lebih dari 1 versi Node.js pada satu komputer/laptop. silahkan baca cara menginstallnya pada halaman berikut: [https://github.com/coreybutler/nvm-windows/wiki](https://github.com/coreybutler/nvm-windows/wiki).

## Mengatur Environment Variables pada Windows

*Environment Variables* adalah sebuah tempat untuk menyimpan variabel global, dimana variabel tersebut nantinya dapat digunakan di aplikasi yang berjalan. contoh lazimnya adalah variabel `PATH` yang berisi path dari `executable`. untuk penjelasan lebih lanjut, silahkan mereferensi ke halaman MSDN berikut: [Environment Variables](https://msdn.microsoft.com/en-us/library/windows/desktop/ms682653.aspx)

### Windows 8 Kebawah

--TODO

### Windows 10

Buka system properties seperti pada langkah [Melihat versi bit windows](), lalu klik ***Advanced System Settings*** pada sidebar. kemudian klik lagi pada button `Environment Variables`. maka akan muncul window seperti berikut:

![https://www.dropbox.com/s/d03fn7qrh14flaf/Screenshot%202015-12-19%2013.14.29.png?raw=1](https://www.dropbox.com/s/d03fn7qrh14flaf/Screenshot%202015-12-19%2013.14.29.png?raw=1)

Untuk menambahkan environment variable baru, klik **New** pada bagian **System variables**, lalu isikan nama *environment variable* dan value dari *environment variable* tersebut.