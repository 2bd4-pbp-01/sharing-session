# Concurrent Programming

#### Daftar Isi

- [Paradigma Concurrent](#paradigma-concurrent)

  - [Overview](#overview)
  - [Concurrent vs Asynchronous](#concurrent-vs-asynchronous)

- [Implementasi pada Bahasa Pemrograman](#implementasi-pada-bahasa-pemrograman)

  - [Bahasa yang Mendukung Concurrent](#bahasa-pemrograman-yang-mendukung-concurrent)
  - [Pros/Cons](#proscons-setiap-bahasa-pemrograman)

- [Studi Kasus](#studi-kasus)

  - [Race Condition](#race-condition)
  - [Deadlock](#deadlock)

---

## Paradigma Concurrent

### Overview

#### Concurrency
Concurrency berarti multiple computations yang terjadi secara bersamaan tanpa harus menunggu computation lainnya diselesaikan terlebih dahulu. Dalam pemrograman modern, concurrency sangat penting karena: [1][2]

1. Situs web harus menangani banyak pengguna secara bersamaan.
2. Aplikasi mobile sering melakukan pemrosesan di server ("di cloud").
3. Graphical user interfaces memerlukan pekerjaan latar belakang yang tidak mengganggu pengguna.

#### Concurrent Programming 
Concurrent Programming adalah model pemrograman yang memungkinkan berbagai bagian dari program berjalan secara concurrent atau tumpang tindih. Dalam pemrograman ini, kamu dapat menulis kode yang memungkinkan berbagai proses atau thread untuk bekerja bersama tanpa harus menunggu salah satu selesai sebelum yang lainnya dimulai. Dengan menggunakan teknik seperti threads, processes, atau coroutines, concurrent programming menjadi landasan penting untuk meningkatkan efisiensi dan kecepatan eksekusi pada sistem modern.[1][2]

#### Dua Model Concurrent programming
Ada dua model umum untuk Concurrent programming: [1]

1. Shared Memory: Modul-modul yang berjalan secara bersamaan berinteraksi dengan membaca dan menulis objek yang dibagikan dalam memori.
2. Message Passing: Modul-modul berinteraksi dengan mengirim pesan melalui saluran komunikasi, di mana pesan yang masuk dikelola dalam antrean.

### Concurrent vs Asynchronous

#### Concurrency :
Concurrency adalah konsep di mana banyak tugas dapat berjalan tumpang tindih atau bersamaan. Di sistem multi-core, beberapa tugas bisa berjalan benar-benar paralel, tetapi pada sistem dengan satu CPU, eksekusi dilakukan secara bergantian dengan cepat menggunakan time-slicing. Ini memungkinkan satu program untuk menangani beberapa tugas sekaligus, seperti menangani beberapa koneksi klien di server web.[4]

#### Asynchronus :
Asynchronus programming berfokus pada penanganan tugas-tugas yang memerlukan operasi I/O, di mana satu tugas dapat menunggu (misalnya saat menunggu data dari jaringan atau disk) tanpa menghentikan seluruh aplikasi. Pada pemrograman sinkron biasa, sebuah thread akan diblokir saat menunggu operasi I/O selesai. Dalam pemrograman asinkron, tugas tidak akan memblokir thread utama, tetapi akan menjalankan tugas lainnya selama menunggu hasil operasi. Ini sering digunakan pada sistem yang banyak berurusan dengan operasi I/O yang lambat.[4]

#### Perbedaan Concurrency dengan Asynchronus Programming :
Concurrency berfokus pada menjalankan banyak tugas yang tumpang tindih dalam satu atau beberapa thread. Di sini, pemrograman biasanya melibatkan sinkronisasi dan manajemen thread agar tidak terjadi konflik data atau masalah seperti race conditions. Sedangkan Asynchronous Programming fokus pada operasi I/O yang lambat, di mana alih-alih memblokir seluruh program saat menunggu hasil dari operasi tersebut, thread dapat melanjutkan tugas lain. Ini membuat pemrograman asinkron lebih efisien dalam menangani operasi I/O daripada pendekatan concurrent yang sinkron.[3][4]

#### Referensi
[1] [MIT Concurrency](https://web.mit.edu/6.005/www/fa14/classes/17-concurrency/).

[2] [Medium Concurrent Programming](https://fuadydheo.medium.com/concurrent-programming-76a548cc47b).

[3] [Medium Concurrency vs Asynchronus](https://medium.com/@suryanshshrivastava_75738/concurrency-asynchronous-programming-and-multithreading-724340dec4df).

[4] [ChatGPT](https://chatgpt.com/share/66f506a8-1370-8008-95e2-7077ebbcc570)

---

## Implementasi pada Bahasa Pemrograman

### Bahasa Pemrograman yang Mendukung Concurrent
Bahasa pemrograman yang mendukung concurrent programming sangat banyak, tetapi kelompok kami coba membahas bahasa pemrograman yang paling baik untuk mendukung concurrent programming. Menentukan bahasa “terbaik” untuk pemrograman konkuren bergantung pada berbagai faktor, termasuk domain aplikasi tertentu, infrastruktur, keahlian pengembang, dan persyaratan proyek. Namun, beberapa bahasa telah menarik perhatian karena fitur dan kemampuan pemrograman konkuren mereka. [1]

#### 1. Java
Dengan dukungannya yang kuat untuk konkurensi berbasis thread, Java adalah salah satu bahasa yang paling populer untuk pemrograman konkuren. Keuntungan menggunakan Java untuk konkurensi antara lain: [2]

* Sekumpulan API dan pustaka konkurensi yang kaya, seperti java.util.concurrent, yang mencakup konstruksi tingkat tinggi seperti ExecutorService dan ConcurrentHashMap untuk pemrograman konkuren yang disederhanakan. [2]
* Primitif untuk pembuatan dan manajemen thread, serta mekanisme sinkronisasi bawaan seperti blok tersinkronisasi, wait(), dan notify().[2]
* Komunitas pengguna yang besar dan dokumentasi yang luas untuk praktik terbaik pemrograman konkuren. [2]

#### Golang
Dikembangkan oleh Google, Go (Golang) dirancang dengan mempertimbangkan konkurensi dan memiliki dukungan asli untuk pemrograman konkuren ringan menggunakan “goroutines” dan saluran. Keuntungan Go untuk pemrograman konkuren antara lain:

* “Goroutine” dan konstruksi saluran bawaan untuk membuat dan mengoordinasikan tugas-tugas ringan, yang mengarah pada program bersamaan yang lebih efisien dan mudah. [2]
* Pengumpulan sampah otomatis, mengurangi kebutuhan untuk mengelola alokasi dan deallokasi memori secara manual dalam program bersamaan. [2]
* Kompilasi biner statis, menyederhanakan penyebaran program konkuren di berbagai platform. [2]

#### Erlang
Bahasa pemrograman fungsional yang dirancang khusus untuk konkurensi, toleransi kesalahan, dan distribusi, Erlang terkenal karena penggunaannya dalam infrastruktur telekomunikasi dan sistem server yang sangat konkuren. Keunggulannya dalam pemrograman konkuren adalah: [2]

* Model proses yang ringan dan penjadwal preemptive, yang memungkinkan penanganan konkurensi dan pemanfaatan sumber daya yang efektif, bahkan pada sistem berskala besar. [2]
* Dukungan bawaan untuk konkurensi pengiriman pesan, dengan pendekatan share-nothing yang menghilangkan kondisi balapan dan masalah inkonsistensi data yang umum terjadi pada model konkurensi lainnya. [2]
* Toleransi kesalahan yang kuat melalui model aktor, filosofi let-it-crash, dan hierarki supervisor. [2]

#### Referensi
[1] [Bahasa Pemrograman Terbaik](https://bilginc.com/en/blog/concurrent-programming-languages-5908/#:~:text=Go%20(Golang)%3A%20Developed%20by,and%20provides%20robust%20concurrency%20mechanisms)

[2] [Kelebihan Bahasa Concurrent Programming Terbaik](https://www.studysmarter.co.uk/explanations/computer-science/computer-programming/concurrent-programming/)

### Pros/Cons setiap Bahasa Pemrograman

## Kelebihan Golang:
- Dukungan Concurrency yang Kuat: Goroutines dan channels memudahkan pengelolaan banyak tugas sekaligus, ideal untuk aplikasi server dan microservices.[1]​[2]
- Garbage Collector yang Efisien: Mengelola memori secara otomatis, mengurangi beban pengembang.[1]​[2]
- Sintaks yang Sederhana: Mudah dipahami dan dipelajari, dengan dokumentasi yang komprehensif.[1]​[2]
- Skalabilitas Tinggi: Bekerja baik pada berbagai inti CPU, cocok untuk infrastruktur cloud dan sistem terdistribusi.[3]​[2]
- Ekosistem yang Mapan: Pustaka standar yang kaya dan banyak pustaka pihak ketiga.[3]​[2]

## Kekurangan Golang:
- Kurangnya Pustaka untuk Aplikasi Monolitik: Kurang memiliki kerangka kerja matang dibandingkan Java atau C#.[3]​[2]
- Pengelolaan Kesalahan yang Verbose: Penanganan kesalahan dapat membuat kode terlihat rumit.[3]​[2]
- Keterbatasan dalam Pemrograman Berorientasi Objek: Tidak ada pewarisan kelas tradisional, bisa membingungkan bagi pengembang terbiasa dengan OOP.[3]​[2]
- Waktu Kompilasi yang Lama: Meskipun lebih cepat dari C++, proyek besar dapat mengalami waktu kompilasi yang lama.[3]​[2]
- Fitur Generik yang Baru Dikenalkan: Masih baru, dan beberapa pengembang mungkin belum mengadopsinya sepenuhnya.[3]​[2]

#### Referensi

[1] [Ruangbacaku](https://www.ruangbacaku.com/detail-artikel/apa-itu-golang-kelebihan-dan-alasan-mengapa-harus-mempelajarinya).


[2] [Logique](https://www.logique.co.id/blog/2019/08/19/bahasa-pemrograman-golang/).

[3] [Silicon Review](https://thesiliconreview.com/2024/08/go-in-2024-an-in-depth-analysis-and-comparison-to-other-languages).




---

## Studi Kasus

### Race Condition

### Deadlock

---
