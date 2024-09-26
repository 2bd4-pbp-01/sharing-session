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

  - [Prana Menarik](#prana-menarik)
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

### Prana Menarik

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
