# JavaScript Stack dari Nol

[![Build Status](https://travis-ci.org/verekia/js-stack-from-scratch.svg?branch=master)](https://travis-ci.org/verekia/js-stack-from-scratch)
[![Release](https://img.shields.io/github/release/verekia/js-stack-from-scratch.svg?style=flat-square)](https://github.com/verekia/js-stack-from-scratch/releases)
[![Dependencies](https://img.shields.io/david/verekia/js-stack-boilerplate.svg?style=flat-square)](https://david-dm.org/verekia/js-stack-boilerplate)
[![Dev Dependencies](https://img.shields.io/david/dev/verekia/js-stack-boilerplate.svg?style=flat-square)](https://david-dm.org/verekia/js-stack-boilerplate?type=dev)
[![Gitter](https://img.shields.io/gitter/room/js-stack-from-scratch/Lobby.svg?style=flat-square)](https://gitter.im/js-stack-from-scratch/)

[![React](/img/react-padded-90.png)](https://facebook.github.io/react/)
[![Redux](/img/redux-padded-90.png)](http://redux.js.org/)
[![React Router](/img/react-router-padded-90.png)](https://github.com/ReactTraining/react-router)
[![Flow](/img/flow-padded-90.png)](https://flowtype.org/)
[![ESLint](/img/eslint-padded-90.png)](http://eslint.org/)
[![Jest](/img/jest-padded-90.png)](https://facebook.github.io/jest/)
[![Yarn](/img/yarn-padded-90.png)](https://yarnpkg.com/)
[![Webpack](/img/webpack-padded-90.png)](https://webpack.github.io/)
[![Bootstrap](/img/bootstrap-padded-90.png)](http://getbootstrap.com/)

Selamat datang di panduan JavaScript Stack modern saya: **JavaScript Stack dari Nol**.

> Panduan ini diterjemahkan dari versi aslinya di [https://github.com/verekia/js-stack-from-scratch](https://github.com/verekia/js-stack-from-scratch)

> **Ini adalah panduan versi 2 🎉 Banyak perubahan besar sejak peluncuran tahun 2016. Lihat perubahannya di sini [Change Log](/CHANGELOG.md)!**

Ini adalah panduan ringkas dan tepat untuk membuat JavaScript Stack. Dibutuhkan sedikit pengetahuan pemrograman dan dasar-dasar JavaScript. **Tutorial ini akan berfokus pada penggunaan program-program pengembang secara bersamaan** dan memberikan anda **contoh-contoh sesederhana mungkin** untuk setiap program-program pengembang. Anda dapat mengimplementasikan panduan ini sebagai *metode untuk membuat boilerplate anda sendiri dari nol*. Oleh karena tujuan tutorial ini adalah untuk menggunakan program-program pendukung secara bersamaan, saya tidak akan merinci lebih lanjut bagaimana program-program tersebut bekerja satu per satu. Silakan periksa panduan masing-masing program tersebut atau carilah panduan penggunaan program-program tersebut jika anda ingin mengetahui lebih lanjut.

Anda tidak perlu menggunakan semua program-program pengembang yang ada di panduan ini, jika anda hanya membuat sebuah halaman web yang sederhana dengan beberapa interaksi JavaScript tentunya (kombinasi dari Browserify/Webpack + Babel + jQuery sudah cukup untuk menulis program ES6 di beberapa file), tetapi jika anda ingin membuat aplikasi web yang berskala, dan membutuhkan bantuan untuk pengaturan segala aspek aplikasi anda, tutorial ini akan sangat berguna buat anda.

Sebagian besar dari program-program yang dijelaskan di panduan ini menggunakan React. Jika anda baru saja mengenal React atau ingin mempelajarinya, [create-react-app](https://github.com/facebookincubator/create-react-app) akan membantu anda dengan cepat memulai React dan menjalankannya  dengan pengaturan-pengaturan awal yang telah tersedia. Saya sangat merekomendasikan panduan tersebut jika anda baru saja bergabung dengan tim yang telah sebelumnya menggunakan React, sehingga anda dapat mengejar pembelajaran React dengan cepat. Di panduan ini, anda tidak akan menggunakan pengaturan yang telah tersedia, karena saya ingin anda memahami semua aspek yang akan dijalankan di dalam program.

Contoh-contoh program tersedia di setiap bab, dan anda dapat menjalankan seluruh program-programnya dengan perintah `yarn && yarn start`. Saya merekomendasikan anda untuk menulis sendiri seluruh program dari nol dengan mengikuti **Instruksi Langkah demo Langkah**.

Program yang sudah selesai tersedia di [JS-Stack-Boilerplate repository](https://github.com/verekia/js-stack-boilerplate), dan di [releases](https://github.com/verekia/js-stack-from-scratch/releases). Tersedia juga [live demo](https://js-stack.herokuapp.com/).

Panduan ini berlaku untuk sistem operasi Linux, macOS, dan Windows.

## Daftar Isi

[01 - Node, Yarn, `package.json`](/tutorial/01-node-yarn-package-json.md#readme)

[02 - Babel, ES6, ESLint, Flow, Jest, Husky](/tutorial/02-babel-es6-eslint-flow-jest-husky.md#readme)

[03 - Express, Nodemon, PM2](/tutorial/03-express-nodemon-pm2.md#readme)

[04 - Webpack, React, HMR](/tutorial/04-webpack-react-hmr.md#readme)

[05 - Redux, Immutable, Fetch](/tutorial/05-redux-immutable-fetch.md#readme)

[06 - React Router, Server-Side Rendering, Helmet](/tutorial/06-react-router-ssr-helmet.md#readme)

[07 - Socket.IO](/tutorial/07-socket-io.md#readme)

[08 - Bootstrap, JSS](/tutorial/08-bootstrap-jss.md#readme)

[09 - Travis, Coveralls, Heroku](/tutorial/09-travis-coveralls-heroku.md#readme)

## Yang Akan Datang

Pengaturan editor anda (terlebih dahulu Atom), MongoDB, Progressive Web App.

## Terjemahan

Jika anda ingin menambahkan terjemahan anda, silakan baca [rekomendasi terjemahan](/how-to-translate.md) untuk memulai proses penerjemahan!

### V2

- [Bahasa Indonesia](https://github.com/finly/js-stack-from-scratch) oleh [Arifin FinLy](https://github.com/finly)

Silakan periksa [terjemahan yang tersedia](https://github.com/verekia/js-stack-from-scratch/issues/147).

### V1

- [中文](https://github.com/pd4d10/js-stack-from-scratch) oleh [@pd4d10](http://github.com/pd4d10)
- [Italiano](https://github.com/fbertone/js-stack-from-scratch) oleh [Fabrizio Bertone](https://github.com/fbertone)
- [日本語](https://github.com/takahashim/js-stack-from-scratch) oleh [@takahashim](https://github.com/takahashim)
- [Русский](https://github.com/UsulPro/js-stack-from-scratch) oleh [React Theming](https://github.com/sm-react/react-theming)
- [ไทย](https://github.com/MicroBenz/js-stack-from-scratch) oleh [MicroBenz](https://github.com/MicroBenz)

## Penghargaan

Panduan ini dibuat oleh [@verekia](https://twitter.com/verekia) – [verekia.com](http://verekia.com/).

Lisensi: MIT
