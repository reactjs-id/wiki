#Proses Development React

Untuk mendevelop dengan react, ada beberapa urutan proses yang harus dijalani agar bisa membuat frontend web dengan react yakni memilih build system, coding, build, lalu run.

##Build System

Dalam memilih build system, sebaiknya disesuaikan dengan kebutuhan development yang diharapkan, apakah selama development kita membutuhkan hot-reload? atau cukup live-reload? Apa kita butuh compiler LESS? atau SASS? Apa kita butuh full support ES6+? atau ES5 saja cukup? Lalu tipe SPA apa yang akan kita buat? Apa butuh SSR (Server Side Rendering) juga? Atau hash saja cukup? Terlalu panjang, satu-satu saja.

Apakah saya butuh hot-loader atau cukup live-reload?

Tunggu, apa itu hot-loader? hot-loader sama seperti live-reload yakni reload web app jika ada salah satu kode kita berubah. Bedanya di hot-loader tidak ada loading sama sekali, tidak seperti live-reload yang full reload web app, dan mengulang boot dari awal lagi. Untuk app kecil, live-reload cukup. Tapi intuk app yang kompleks, dianjurkan untuk menggunakan hot-loader agar waktu tidak habis hanya untuk melakukan beberapa klik hingga masuk ke komponen yang sedang didevelop (mulai dari awal boot reload).
Jika ternyata kita hanya butuh live-reload, build system bisa menggunakan gulp dan browserify saja. Tapi jika butuh hot-loader, harus menggunakan webpack.

Apakah saya butuh ES6+ atau cukup dengan ES5?

Beberapa developer ada yang masih nyaman dengan ES5, tapi ada juga beberapa developer yang mulai lelah dengan sintaks ES5, mereka butuh sintaks javascript yang lebih mudah dibaca dan mudah dituliskan, dengan ES6+.
Tipe developer manakah anda?
Jika anda butuh support ES6+, anda harus menggunakan babel. Browserify dan Webpack mendukung babel semua, namun selama saya menggunakan browserify, saya masih belum bisa menggunakan ```import module from 'module';```. Fitur ini saya dapatkan hanya saat saya menggunakan Webpack.

Tipe web app apa yang anda ingin buat? Apa hash saja cukup? Atau butuh server side rendering?

Sesuai kebutuhan, jika anda hanya akan membuat web app untuk administrasi saja, lebih baik cukup menggunakan hash. Tapi jika app yang akan anda buat membutuhkan dukungan SEO, sangat dianjurkan untuk menggunakan opsi Server Side Rendering (SSR). SSR menggunakan html5 history api di browser, dan mensinkronkan route dengan express router di backend, tentu butuh bantuan node untuk menjalankan SSR. Ada dua keuntungan yang didapat jika menggunakan SSR, yakni bisa di crawl oleh search engine, dan memangkas waktu bootstraping app karena semua data sudah dirender sebelum sampai di user. Jadi booting app tidak akan memakan waktu lama (karna biasanya masih menunggu data datang, lama banget..). Tentu jika ada kelebihan pasti ada kekurangan, yakni masih harus terpaku dengan node dan butuh beberapa trik untuk sinkronisasi antara server dan client (react-router dan express-router). Kriteria ini tidak masuk dalam proses pemilihan build system, namun struktur build system sangat mempengaruhi.

