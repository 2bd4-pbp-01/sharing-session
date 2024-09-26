# Functional Programming

#### Daftar Isi

- [Functional Programming](#functional)

  - [Overview](#overview)
  - [Kenapa Perlu Menggunakan Functional Programming?](#kenapa-perlu-menggunakan-functional-programming)
  - [Pros/Cons](#proscons)

- [Haskell](#haskell)

  - [Overview Haskell](#overview-haskell)
  - [Tipe Data (Data Type)](#tipe-data-data-type)
  - [Modularitas](#modularitas)
  - [Keamanan Tipe (Type Safety)](#tipe-data-data-type)
  - [Error / Exception Handling](#error-dan-exception-handling)
  - [Fun Facts](#fun-facts)

- [Studi Kasus](#studi-kasus)

  - [Pranala Menarik](#pranala-menarik)
  - [Haskell Development Environments](#haskell-development-environments)
  - [2D Graphics with OpenGL dan Haskell](#2d-graphics-dengan-opengl-dan-haskell)

  ***

## Functional

### Overview

### Kenapa Perlu Menggunakan Functional Programming

### Pros/Cons

---

## Haskell

### Overview Haskell

### Tipe Data (_Data Type_)

### Modularitas

### Keamanan Tipe (_Type Safety_)

### Error dan Exception Handling

### Fun Facts

#### Memory Management

#### High-Order Function

#### Monad

---

## Studi Kasus

### Pranala Menarik

Haskell digunakan di berbagai lingkup seperti [pengembangan (_research_)](https://wiki.haskell.org/Haskell_in_research),
[industri](https://wiki.haskell.org/Haskell_in_industry), dan [pendidikan](https://wiki.haskell.org/Haskell_in_education).
Haskell juga digunakan oleh berbagai perusahaan besar untuk mengembangkan project
/ service / tool spesifik. Berikut terdapat beberapa sumber eksternal yang membahas
mengenai bagaimana Haskell digunakan:

- [(YouTube) Beberapa project berbasis Haskell yang dikembangkan oleh Meta / Facebook](https://youtu.be/10gSoVZ5yXY?si=G9Avy3wBKAUT_4Lp)

<details>
  <summary>TLDR</summary>

Facebook menggunakan Haskell untuk membuat sistem pendeteksi penyalahgunaan
seperti spam, akun palsu, dan penipuan bernama Sigma. Sigma merupakan sistem
yang krusial dan digunakan dalam produksi skala besar (hampir 1 juta request
per detik).

Alasan Facebook menggunakan Haskell adalah untuk mengimplementasikan konsep
bernama [dependent type](https://stackoverflow.com/questions/9338709/what-is-dependent-typing),
yaitu sebuah tipe yang pendefinisiannya tergantung suatu nilai. Hal ini karena
Haskell mendukung [static type](#tipe-data-data-type).

Selain itu, penulisan kode dengan bahasa lain lebih sering terjadi bug seperti
infinite loop, seringkali menerima kesalahan tulisan pada input, dan sebagainya
ketimbang menggunakan Haskell.

</details>

- [Github Semantic: Tool untuk parsing, analisis, dan membandingan source code untuk berbagai bahasa pemrograman](https://github.com/github/semantic/blob/main/docs/why-haskell.md)

<details>
  <summary>TLDR</summary>

Github Semantic menggunakan Haskell karena fiturnya memungkinkan untuk
mengekspresikan struktur data dan algoritmanya secara ringkas, benar,
dan elegan. Haskell juga memberikan kemudahan dalam merepresentasikan
aljabar di dalam sintaks bahasa pemrograman.

</details>

- [(Blog) Cardano: Platform blockchain dan cryptocurrency](https://forkast.news/video-audio/watch-charles-hoskinson-co-founder-of-ethereum-and-iohk-on-why-cardano-is-a-better-platform-part-i-2-2/)

<details>
  <summary>TLDR</summary>

Alasan Cardano mengadopsi Haskell untuk implementasinya yaitu karena Haskell lebih
menjamin ketepatan / keakuratan (high-assurance). Haskell menurunkan konsep dari
[Functional Programming](#overview), yaitu sebuah variabel yang stateless atau mutable.
Selain itu fungsi yang didefinisikan tidak memiliki side-effect yang berimbas pada
bug.

</details>

### Haskell Development Environments

Pengembangan program/software di Haskell perlu beberapa tools yang perlu dipersiapkan,
kumpulan _tools_ tersebut disebut _toolchain_. Haskell memberikan kemudahan pada
penggunanya untuk melakukan pengelolaan toolchain yang dibutuhkan dengan adanya [GHCup](ttps://www.haskell.org/ghcup/#).
Toolchain sendiri meliputi:

1. Compiler

Haskell adalah bahasa pemrograman yang memerlukan compiler untuk menjalankan programnya.
Sehingga tool paling utama yang diperlukan yaitu compiler,bernama GHC (Glasgow Haskell
Compiler). GHC merupakan compiler yang berbasis open-source dan memungkinkan untuk
berjalan di platform / sistem operasi yang berbeda meliputi Linux, macOS, Windows,
dan lainnya.

> [!NOTE]
> Selain digunakan untuk melakukan kompilasi pada program Haskell, GHC juga mendukung
> extensions, library, dan beberapa parameter untuk melakukan optimisasi pada saat
> proses kompilasi program.

2. Language Server

Haskell Language server (HSL) berjalan di latar belakang dan digunakan oleh kode
editor atau IDE untuk memberikan pengalaman yang lebih baik pada saat menulis kode
Haskell, seperti adanya fitur _syntax highlighting_ yang berfungsi membuat kode lebih
terbaca. Selain itu memberikan fitur _auto suggestion_ yang berfungsi untuk memberikan
kemudahan pencarian pada library, modul, function, dan variabel yang telah dibuat.

3. Build Tools

Build tools merupakan tool untuk mengelola project Haskell. Dengan menggunakan
build tools, pengelolaan seperti build project (melakukan kompilasi pada serangkaian
file), menjalankan program, mengelola dependencies, dan library eksternal dapat lebih
mudah. Terdapat 2 build tools yang populer di Haskell, yaitu [Cabal](https://www.haskell.org/cabal/)
dan [Stack](https://docs.haskellstack.org/en/stable/).

### 2D Graphics dengan OpenGL dan Haskell

---
