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

Functional programming (FP) adalah paradigma pemrograman yang berfokus pada penggunaan fungsi murni (pure functions), yaitu fungsi yang selalu menghasilkan output yang sama untuk input yang sama dan tidak memiliki efek samping (side effects). Dalam FP, konsep seperti data immutability (data yang tidak dapat diubah) dan penghindaran shared state (berbagi status) sangat penting. FP menggunakan pendekatan deklaratif, yang lebih berfokus pada "apa yang harus dilakukan" dibandingkan dengan pendekatan imperatif yang menginstruksikan "bagaimana melakukannya"​.[1][2][3]

Dasar-Dasar Functional Programming

1. Pure Functions: Fungsi yang selalu memberikan hasil yang sama untuk input yang sama dan tidak memiliki efek samping.
2. Immutable data: Setelah data dibuat, tidak dapat diubah, sehingga menghindari masalah yang tidak terduga.
3. First-class functions: Fungsi diperlakukan seperti data lainnya, dapat diteruskan sebagai argumen atau dikembalikan dari fungsi lain.
4. Recursion: Fungsi dapat memanggil dirinya sendiri untuk melakukan iterasi tanpa menggunakan loop tradisional.
5. Higher-order functions: Fungsi yang dapat menerima fungsi lain sebagai argumen atau mengembalikannya.

### Kenapa Perlu Menggunakan Functional Programming

Ada beberapa alasan untuk memilih functional programming:[1][2][3]

1. Kode Lebih Terstruktur dan Bersih: Karena fungsi-fungsi murni dan sifat immutability, kode menjadi lebih mudah diprediksi dan dipelihara.
2. Mendukung Pemrograman Paralel: FP secara alami mendukung pemrograman paralel, karena tidak adanya shared state mengurangi potensi konflik saat fungsi berjalan secara bersamaan.
3. Memudahkan Testing dan Debugging: Karena FP menghindari efek samping, testing dan debugging lebih sederhana, karena fungsi tidak bergantung pada status eksternal​
4. Keringkasan: Mengurangi jumlah kode yang perlu ditulis.
5. Prediktabilitas: Kode lebih mudah dipahami karena tidak ada efek samping.
6. Modularitas: Fungsi murni dapat digunakan di berbagai tempat tanpa ketergantungan pada konteks luar.

### Pros/Cons

Pros: [1][2][4]

- Lebih mudah diuji: Tanpa adanya efek samping, memverifikasi fungsi dalam FP menjadi lebih sederhana.
- Dukungan parallelism/concurent: FP mendukung pemrograman paralel, yang sangat berguna di aplikasi yang membutuhkan kinerja tinggi atau skala besar seperti pemrosesan big data dan komputasi terdistribusi.
- Modular dan Reusable: FP mendorong penggunaan kembali fungsi, yang membuat kode lebih modular dan mudah dirawat
- Pure function lebih mudah dipahami karena tidak mengubah keadaan dan hanya bergantung pada input.
- Mengadopsi lazy evaluation, yang menghindari evaluasi berulang.

Cons: [1][2][4]

- Kurva belajar yang curam: Bagi pemrogram yang terbiasa dengan paradigma imperatif atau OOP, beralih ke FP membutuhkan usaha ekstra untuk memahami konsep seperti fungsi murni, komposisi fungsi, dan data immutability
- Kurang efisien untuk beberapa aplikasi: Dalam beberapa kasus, seperti pemrograman tingkat rendah yang memerlukan akses langsung ke perangkat keras, FP tidak selalu merupakan pilihan yang paling efisien​
- Menulis pure function kadang dapat mengurangi keterbacaan kode.
- Nilai yang tidak dapat diubah dan rekursi dapat mengurangi kinerja.
- Menggabungkan pure function dengan operasi I/O bisa menjadi tantangan.

#### Referensi

[1] [Syndicode Pros and Cons](https://syndicode.com/blog/pros-and-cons-of-functional-programming/).

[2] [LearnCodewithme Functional Prog](https://learntocodewith.me/learn/functional-programming/)

[3] [DailyDev Functional Prog](https://daily.dev/blog/functional-programming-for-beginners)

[4] [GeeksforGeeks Functional Prog](https://www.geeksforgeeks.org/functional-programming-paradigm/)

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

### 2D Graphics dengan OpenGL dan Haskell

---
