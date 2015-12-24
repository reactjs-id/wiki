#Install Node di Mac

##Metode Install

Ada beberapa metode untuk menginstall node di Mac, yakni:

###NVM

Sesua dengan namanya, Node Version Manager, dengan NVM kita bisa menginstall beragam versi node dan switch antar versi node hanya dengan sekali perintah. NVM menginstall node di direktori home user yang artinya node titak diinstal secara global, hanya tersedia untuk user yang sedang login.

```sh
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.29.0/install.sh | bash
```

Masukkan baris ini ke ```~/.bash_profile```

```sh
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" # This loads nvm
```

Lalu tes dengan ```nvm``` di terminal. Jika nvm masih belum bisa dijalankan, keluar dari terminal lalu buka lagi terminal dan ulangi masukkan ```nvm``` lagi, pasti bisa.

Untuk melihat versi apa saja yang bisa di install, jalankan 

```sh
nvm ls-remote
```

Lalu install versi node yang anda inginkan, contohnya

```sh
nvm install v5.0.0
```

Untuk mengaktifkannya jalankan 

```sh
nvm alias default v5.0.0
```

Tes node dengan ```node -v``` dan npm dengan ```npm -v```.

###Metode Lain

Menginstall nodejs bisa juga menggunakan brew atau menginstall langsung dari situs node. Tapi dengan asumsi bahwa menginstall node di Mac hanya untuk development, sangat disarankan untuk menggunakan NVM karena beberapa package membutuhkan versi node yang berbeda dengan package lainnya.