# 01 - Node, Yarn, and `package.json`

File program untuk bab ini tersedia di [sini](https://github.com/verekia/js-stack-walkthrough/tree/master/01-node-yarn-package-json).

Di bab ini, kita akan mempersiapkan Node, Yarn, file dasar `package.json`, dan mencoba sebuah paket.

## Node

> 💡 **[Node.js](https://nodejs.org/)** adalah JavaScript yang berjalan dari sisi server. Umumnya itu digunakan untuk pengembangan Back-End, tetapi juga sering digunakan untuk pemrograman script secara umum. Di konteks pengembangan Front-End, Node.js dapat juga digunakan untuk pelaksanaan seluruh tugas seperti linting, testing, dan penyusunan file-file.

Kita akan menggunakan Node pada dasarnya untuk keseluruhan yang ada di panduan ini, jadi anda akan membutuhkannya. Kita menuju ke [halaman unduh](https://nodejs.org/en/download/current/) untuk **macOS** atau **Windows** file binari, atau [halaman installasi dengan pengelola paket](https://nodejs.org/en/download/package-manager/) untuk distribusi Linux.

Contohnya, untuk **Ubuntu / Debian**, anda bisa menjalankan perintah berikut untuk menginstall Node:

```sh
curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -
sudo apt-get install -y nodejs
```

Anda membutuhkan Node versi 6.5.0 ke atas.

## NVM

Jika Node sudah terinstall, atau jika anda menginginkan fleksibilitas, anda dapat menginstall NVM ([Node Version Manager](https://github.com/creationix/nvm)), dan atur NVM untuk menginstall dan menggunakan versi terkini Node untuk anda.

## NPM

NPM adalah manajer paket standar untuk Node. NPM otomatis terinstall bersamaan dengan Node. Manajer paket digunakan untuk menginstall dan mengatur paket-paket (modul-modul dari program yang anda atau orang lain tulis). Kita akan menggunakan banyak paket di panduan ini, tetapi kita akan menggunakan Yarn, manajer paket lainnya.

## Yarn

> 💡 **[Yarn](https://yarnpkg.com/)** adalah manajer paket dari Node.js yang jauh lebih cepat daripada NPM, mendukung saat tidak ada koneksi internet, dan mengunduh dependensi [lebih terprediksi](https://yarnpkg.com/en/docs/yarn-lock).

Sejak Yarn [diluncurkan](https://code.facebook.com/posts/1840075619545360) pada Oktober 2016, banyak yang begitu cepat mencoba dan menggunakannya, sehingga Yarn menjadi pilihan manajer paket di kalangan komunitas JavaScript. Jika anda tetap ingin tetap bertahan menggunakan NPM, anda dapat dengan mudah mengganti semua perintah `yarn add` dan `yarn add --dev` di panduan ini dengan `npm install --save` dan `npm install --save-dev`.

Panduan instalasi Yarn dapat diakses di [instruksi ini](https://yarnpkg.com/en/docs/install) untuk sistem operasi anda. Saya merekomendasikan anda untuk menggunakan **Installation Script** yang ada di tab *Alternatives* jika anda menggunakan macOS atau Unix, untuk [mencegah](https://github.com/yarnpkg/yarn/issues/1505) ketergantungan pada manajer paket lainnya:

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash
```

## `package.json`

> 💡 **[package.json](https://yarnpkg.com/en/docs/package-json)** adalah file yang berisi penjelasan dan pengaturan proyek JavaScript anda. File ini berisi informasi umum (nama proyek anda, versi, kontributor, lisensi, dll), opsi-opsi konfigurasi untuk program yang anda gunakan, bahkan bagian untuk menjalankan *tugas-tugas*.

- Buatlah sebuah folder baru untuk proyek anda, dan jalankan perintah `cd` untuk masuk ke folder tersebut.
- Jalankan perintah `yarn init` dan jawab semua pertanyaannya (`yarn init -y` untuk melewati semua pertanyaan), untuk membuat file `package.json` secara otomatis.

Ini adalah isi standar dari file `package.json`. Saya akan menggunakannya di dalam panduan ini:

```json
{
  "name": "proyek-anda",
  "version": "1.0.0",
  "license": "MIT"
}
```

## Hello World

- Buat sebuah file `index.js` yang berisi `console.log('Hello world')`

🏁 Jalankan perintah `node .` di folder ini (`index.js` adalah file standar yang akan dilihat oleh Node.js di sebuah folder). Ini akan menghasilkan keluaran "Hello world".

**Catatan**: Anda lihat simbol 🏁 emoji bendera balapan ini? Saya akan menggunakan simbol ini setiap saat anda mencapai sebuah **checkpoint**. Kadang-kadang kita akan membuat banyak perubahan berturut-turut, sehingga program anda tidak akan berjalan sampai anda mencapai checkpoint berikutnya.

## Script `start`

Dengan menjalankan perintah `node .` untuk mengeksekusi program kita, itu sangat terlalu rendah levelnya. Sebagai gantinya, kita akan menggunakan script NPM/Yarn untuk memicu pengeksekusian program kita. Ini akan memberikan kita sebuah abstraksi yang bagus untuk selalu dapat menggunakan `yarn start`, bahkan ketika program kita menjadi lebih rumit.

- Di `package.json`, tambahkan sebuah objek `scripts` seperti berikut:

```json
{
  "name": "proyek-anda",
  "version": "1.0.0",
  "license": "MIT",
  "scripts": {
    "start": "node ."
  }
}
```

`start` adalah nama yang kita berikan untuk *tugas* yang akan menjalankan aplikasi kita. Kita akan membuat banyak tugas-tugas berbeda di objek `scripts` di sepanjang panduan ini. Nama `start` ini khususnya diberikan untuk tugas standar dari sebuah aplikasi. Beberapa nama standar lainnya adalah `stop` dan `test`.

`package.json` harus sebuah file JSON yang benar, yang berarti tidak boleh ada koma di bagian yang paling akhir. Jadi anda harus berhati-hati saat mengedit file `package.json` anda secara manual.

🏁 Jalankan perintah `yarn start`. Itu akan menghasilkan keluaran `Hello world`.

## Git dan `.gitignore`

- Inisialisasi sebuah repositori Git dengan `git init`

- Buatlah sebuah file `.gitignore` dan tambahkan kode berikut ini:

```gitignore
.DS_Store
/*.log
```

`.DS_Store` adalah file-file yang dihasilkan secara otomatis oleh macOS yang tidak seharusnya ada di dalam sebuah repositori.

`npm-debug.log` dan `yarn-error.log` adalah file-file yang dihasilkan ketika manajer paket anda menemukan kesalahan, kita juga tidak mau file-file ini diversikan di repositori kita.

## Instalasi dan Penggunaan Sebuah Paket

Di bagian ini, kita akan menginstal dan menggunakan sebuah paket. Sebuah "paket" sederhananya adalah sepotong program yang orang lain tulis, dan anda dapat menggunakannya di kode anda. Itu bisa apa saja. Di sini misalnya, kita akan mencoba sebuah paket yang membantu kita memanipulasi warna-warna.

- Instal sebuah paket yang dibuat oleh komunitas, bernama `color` dengan menjalankan perintah `yarn add color`

Buka file `package.json` untuk melihat bagaimana Yarn secara otomatis menambahkan `color` di bagian  `dependencies`.

Sebuah folder `node_modules` dihasilkan untuk menyimpan paket-paket.

- Tambahkan `node_modules/` ke dalam file `.gitignore` anda.

Anda juga akan melihat sebuah file `yarn.lock` dihasilkan oleh Yarn. Anda harus mengkomit file ini ke dalam repositori anda, sehinggal anda dan tim anda menggunakan paket-paket dengan versi yang sama. Jika anda tetap ingin menggunakan NPM daripada Yarn, file yang sama untuk ini adalah *shrinkwrap*.

- Tulis kode berikut ini ke dalam file `index.js` anda:

```js
const color = require('color')

const redHexa = color({ r: 255, g: 0, b: 0 }).hex()

console.log(redHexa)
```

🏁 Jalankan perintah `yarn start`. Itu akan menghasilkan keluaran `#FF0000`.

Selamat, anda telah menginstal dan menggunakan sebuah paket!

Di bagian ini, `color` hanya digunakan untuk memandu anda bagaimana menggunakan sebuah paket sederhana. Kita tidak akan membutuhkannya lagi, jadi kita bisa menghapus paket itu:

- Jalankan `yarn remove color`

## Dua Jenis Dependensi

Ada dua jenis dependensi paket, `"dependencies"` dan `"devDependencies"`:

**Dependencies** adalah kumpulan-kumpulan paket yang aplikasi anda butuhkan untuk berfungsi (React, Redux, Lodash, jQuery, dll). Anda dapat menginstal paket-paket tersebut dengan perintah `yarn add [paket]`.

**Dev Dependencies** adalah kumpulan-kumpulan paket yang digunakan selama pengembangan atau pembuatan aplikasi anda (Webpack, SASS, linters, framework untuk testing, dll). Anda dapat menginstal paket-paket tersebut dengan perintah `yarn add --dev [paket]`.

Bab selanjutnya: [02 - Babel, ES6, ESLint, Flow, Jest, Husky](02-babel-es6-eslint-flow-jest-husky.md#readme)

Kembali ke [Daftar Isi](https://github.com/finly/js-stack-from-scratch#daftar-isi).
