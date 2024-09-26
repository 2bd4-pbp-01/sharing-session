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

Functional programming (FP) adalah paradigma pemrograman yang berfokus pada penggunaan pure functions, yaitu fungsi yang selalu menghasilkan output yang sama untuk input yang sama dan tidak memiliki side effects[^4]. Dalam FP, konsep seperti data immutability (data yang tidak dapat diubah) dan penghindaran shared state (berbagi status) sangat penting. FP menggunakan pendekatan deklaratif, yang lebih berfokus pada "apa yang harus dilakukan" dibandingkan dengan pendekatan imperatif yang menginstruksikan "bagaimana melakukannya"[^2]

Dasar-Dasar Functional Programming

1. **Pure Functions**: Fungsi yang selalu memberikan hasil yang sama untuk input yang sama dan tidak memiliki efek samping.

2. **Immutable Data**: Setelah data dibuat, tidak dapat diubah, sehingga menghindari masalah yang tidak terduga.

3. **First-Class Functions**: Fungsi diperlakukan seperti data lainnya, dapat diteruskan sebagai argumen atau dikembalikan dari fungsi lain.

4. **Recursion**: Fungsi dapat memanggil dirinya sendiri untuk melakukan iterasi tanpa menggunakan loop tradisional.

5. **Higher-order Functions**: Fungsi yang dapat menerima fungsi lain sebagai argumen atau mengembalikannya.

### Kenapa Perlu Menggunakan Functional Programming

Ada beberapa alasan untuk memilih functional programming[^3]:

1. **Kode Lebih Terstruktur dan Bersih**: Karena fungsi-fungsi murni dan sifat immutability, kode menjadi lebih mudah diprediksi dan dipelihara.

2. **Mendukung Pemrograman Paralel**: FP secara alami mendukung pemrograman paralel, karena tidak adanya shared state mengurangi potensi konflik saat fungsi berjalan secara bersamaan.

3. **Memudahkan Testing dan Debugging**: Karena FP menghindari efek samping, testing dan debugging lebih sederhana, karena fungsi tidak bergantung pada status eksternal​

4. **Keringkasan**: Mengurangi jumlah kode yang perlu ditulis.

5. **Prediktabilitas**: Kode lebih mudah dipahami karena tidak ada efek samping.

6. **Modularitas**: Fungsi murni dapat digunakan di berbagai tempat tanpa ketergantungan pada konteks luar.

### Pros/Cons

Adapun kelebihan yang dimiliki Functional programming[^1], diantaranya:

- **Lebih mudah diuji**: Tanpa adanya efek samping, memverifikasi fungsi dalam FP menjadi lebih sederhana;
- **Dukungan parallelism/concurent**: FP mendukung pemrograman paralel, yang sangat berguna di aplikasi yang membutuhkan kinerja tinggi atau skala besar seperti pemrosesan big data dan komputasi terdistribusi;
- **Modular dan Reusable**: FP mendorong penggunaan kembali fungsi, yang membuat kode lebih modular dan mudah dirawat;
- Pure function lebih mudah dipahami karena tidak mengubah keadaan dan hanya bergantung pada input;
- Mengadopsi lazy evaluation, yang menghindari evaluasi berulang.

Meskipun begitu, terdapat kekurangan yang dimiliki oleh Functional programming[^1], diantaranya:

- **Kurva belajar yang curam**: Bagi pemrogram yang terbiasa dengan paradigma imperatif atau OOP, beralih ke FP membutuhkan usaha ekstra untuk memahami konsep seperti fungsi murni, komposisi fungsi, dan data immutability;
- **Kurang efisien untuk beberapa aplikasi**: Dalam beberapa kasus, seperti pemrograman tingkat rendah yang memerlukan akses langsung ke perangkat keras, FP tidak selalu merupakan pilihan yang paling efisien;
- Menulis pure function kadang dapat mengurangi keterbacaan kode;
- Nilai yang tidak dapat diubah dan rekursi dapat mengurangi kinerja;
- Menggabungkan pure function dengan operasi I/O bisa menjadi tantangan.

[^1]: [Syndicode Pros and Cons](https://syndicode.com/blog/pros-and-cons-of-functional-programming/).

[^2]: [LearnCodewithme Functional Prog](https://learntocodewith.me/learn/functional-programming/)

[^3]: [DailyDev Functional Prog](https://daily.dev/blog/functional-programming-for-beginners)

[^4]: [GeeksforGeeks Functional Prog](https://www.geeksforgeeks.org/functional-programming-paradigm/)

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

  > Facebook menggunakan Haskell untuk membuat sistem pendeteksi penyalahgunaan
  > seperti spam, akun palsu, dan penipuan bernama Sigma. Sigma merupakan sistem
  > yang krusial dan digunakan dalam produksi skala besar (hampir 1 juta request
  > per detik).
  >
  > Alasan Facebook menggunakan Haskell adalah untuk mengimplementasikan konsep
  > bernama [dependent type](https://stackoverflow.com/questions/9338709/what-is-dependent-typing),
  > yaitu sebuah tipe yang pendefinisiannya tergantung suatu nilai. Hal ini karena
  > Haskell mendukung [static type](#tipe-data-data-type).
  >
  > Selain itu, penulisan kode dengan bahasa lain lebih sering terjadi bug seperti
  > infinite loop, seringkali menerima kesalahan tulisan pada input, dan sebagainya
  > ketimbang menggunakan Haskell.

    </details>

- [Github Semantic: Tool untuk parsing, analisis, dan membandingan source code untuk berbagai bahasa pemrograman](https://github.com/github/semantic/blob/main/docs/why-haskell.md)

    <details>
      <summary>TLDR</summary>

  > Github Semantic menggunakan Haskell karena fiturnya memungkinkan untuk
  > mengekspresikan struktur data dan algoritmanya secara ringkas, benar,
  > dan elegan. Haskell juga memberikan kemudahan dalam merepresentasikan
  > aljabar di dalam sintaks bahasa pemrograman.

    </details>

- [(Blog) Cardano: Platform blockchain dan cryptocurrency](https://forkast.news/video-audio/watch-charles-hoskinson-co-founder-of-ethereum-and-iohk-on-why-cardano-is-a-better-platform-part-i-2-2/)
    <details>
      <summary>TLDR</summary>

  > Alasan Cardano mengadopsi Haskell untuk implementasinya yaitu karena Haskell
  > lebih menjamin ketepatan / keakuratan (high-assurance). Haskell menurunkan konsep
  > dari [Functional Programming](#overview), yaitu sebuah variabel yang stateless
  > atau mutable. Selain itu fungsi yang didefinisikan tidak memiliki side-effect
  > yang berimbas pada bug.

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
