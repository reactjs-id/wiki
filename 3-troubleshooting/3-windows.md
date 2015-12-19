# Windows Troubleshooting

## NPM cannot find git binary / git not found

Sebelum menggunakan Node.js, pastikan anda telah menginstall [Chocolatey](https://chocolatey.org/). setelah itu, install `Git` dengan cara menjalankan perintah:

```sh
choco install git
```

setelah itu, baru lakukan instalasi nodejs seperti biasa.

## Directory path too long

Windows mempunyai batasan untuk **nested directory**. untuk mengatasinya, lakukan update `npm` ke versi 3 keatas. silahkan lihat bagian [NPM3](#NPM3).

## Error kompilasi node-gyp pada saat instalasi modul socket.io/utf-8-validate/bufferutils dan lain lain.

node-gyp banyak masalah bila dijalankan pada environment windows. untuk mengatasinya, pertama upgrade dulu NPM ke versi 3 keatas, silahkan lihat bagian [NPM3](#NPM3). apabila langkah tersebut sukses, update `node-gyp` dengan menjalankan perintah:

```sh
npm install -g node-gyp@latest
```

setelah melakukan update node-gyp, maka langkah selanjutnya adalah melakukan instalasi VC\++ Build Tools, dan Python. Perlu diperhatikan bahwa **apabila telah terinstall Visual Studio 2012/2015, maka instalasi VC++ Build Tools adalah opsional.**

### VC\++ Build Tools 2015

>Visual C\++ Build Tools 2015 (Pre-release). If you want to build your C\++ projects targeting Windows desktop without having Visual Studio installed on your computer, Microsoft Visual C\++ Build Tools 2015 provides the required tools: C\++ compilers, libraries, build scripts, Windows SDKs. This Community Technology Preview ships with the same C++ compilers and libraries packaged with Visual Studio 2015 Update 1 RC (2015.1)
>[http://blogs.msdn.com/b/vcblog/archive/2015/10/29/visual-studio-2015-update-1-rc-available.aspx](http://blogs.msdn.com/b/vcblog/archive/2015/10/29/visual-studio-2015-update-1-rc-available.aspx)

Download VC\++ Build Tools 2015 pada halaman berikut: [Microsoft Visual C++ Build Tools 2015 Technical Preview](https://www.microsoft.com/en-us/download/details.aspx?id=49983), dan lakukan instalasi seperti biasa.

**Apabila anda menggunakan Windows 10, klik button change, lalu centang opsi Windows 8.1 SDK dan Windows 10 SDK**

### Python

Versi python yang digunakan adalah Python 2.7.9. untuk melakukan instalasi Python, download pada halaman berikut: [Python 2.7.9](https://www.python.org/downloads/release/python-279/). pilih x86 apabila windows anda 32-bit, dan x86_64 apabila windows anda 64-bit ([Melihat versi *bit* windows]()).

cek environment variable `PATH` anda. apabila belum ada path ke direktori *executable* dari python, tambahkan secara manual.

### NPM

Setelah anda melakukan instalasi VC\++ Build Tool dan python, maka langkah selanjutnya adalah 'mengenalkan' NPM pada versi Visual Studio yang telah diinstall, dengan cara menjalankan perintah berikut pada command prompt:

```sh
npm config set msvs_version 2015 --global
npm config set python python2.7 --global
```

**Perhatian:** apabila anda tidak melakukan instalasi VC\++ Build Tools 2015, maka isikan value `msvs_version` sesuai dengan visual studio yang terinstall pada laptop/komputer. misal versi visual studio anda adalah 2010, maka jalankan:

```sh
npm config set msvs_version 2010 --global
```

apabila semua langkah telah dilakukan, silakan lakukan kembali instalasi modul yang diinginkan.
