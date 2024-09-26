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

#### Golang

#### Java

#### Erlang

### Pros/Cons setiap Bahasa Pemrograman

## Golang

## Kelebihan Golang:
- Dukungan Concurrency yang Kuat: Goroutines dan channels memudahkan pengelolaan banyak tugas sekaligus, ideal untuk aplikasi server dan microservices.[1]​[2]
- Garbage Collector yang Efisien: Mengelola memori secara otomatis, mengurangi beban pengembang.[1]​[2]
- Sintaks yang Sederhana: Mudah dipahami dan dipelajari, dengan dokumentasi yang komprehensif.[1]​[2]
- Skalabilitas Tinggi: Bekerja baik pada berbagai inti CPU, cocok untuk infrastruktur cloud dan sistem terdistribusi.[3]​[2]
- Ekosistem yang Mapan: Pustaka standar yang kaya dan banyak pustaka pihak ketiga.[3]​[2]

## Kekurangan Golang:
- Kurangnya Pustaka untuk Aplikasi Monolitik: Kurang memiliki kerangka kerja matang dibandingkan Java atau C#.[3]​[2]
- Pengelolaan Kesalahan yang Verbose: Penanganan kesalahan dapat membuat kode terlihat rumit.[3]​[2]
- Waktu Kompilasi yang Lama: Meskipun lebih cepat dari C++, proyek besar dapat mengalami waktu kompilasi yang lama.[3]​[2]
- Fitur Generik yang Baru Dikenalkan: Masih baru, dan beberapa pengembang mungkin belum mengadopsinya sepenuhnya.[3]​[2]

## Java

## Kelebihan Java:
- Model Thread yang Sederhana:
Java menyediakan API yang sederhana untuk membuat dan mengelola thread melalui kelas Thread dan antarmuka Runnable. Ini memungkinkan pengembang untuk dengan mudah membuat aplikasi yang memanfaatkan pemrosesan paralel.
- Dukungan Built-in untuk Synchronization:
Java memiliki kata kunci synchronized yang memungkinkan pengembang untuk mengontrol akses ke sumber daya yang dibagikan oleh beberapa thread, membantu mencegah race condition.
- Paket Concurrency yang Kaya:
Java menyediakan paket java.util.concurrent, yang mencakup berbagai kelas dan antarmuka untuk mendukung pemrograman konkuren, seperti ExecutorService, CountDownLatch, dan Semaphore. Ini membuat manajemen thread lebih mudah dan lebih efisien.
- Fork/Join Framework:
Java menawarkan framework fork/join yang memungkinkan pembagian tugas menjadi sub-tugas yang lebih kecil, sehingga memudahkan pemrograman paralel dan memaksimalkan penggunaan CPU.
- Garbage Collection Otomatis:
Java mengelola memori secara otomatis, yang membantu mengurangi masalah kebocoran memori yang sering muncul dalam aplikasi konkuren.

## Kekurangan Java:
- Overhead Kinerja:
Meskipun Java menawarkan banyak fitur untuk concurrency, penggunaan thread dapat menghasilkan overhead, terutama jika banyak thread yang dibuat dan dihancurkan secara berulang.
- Kompleksitas dalam Debugging:
Aplikasi konkuren dapat menjadi sulit untuk didiagnosis dan di-debug, dengan masalah seperti deadlock dan race condition yang sulit dideteksi.
- Keterbatasan dalam Model Pemrograman:
Model pemrograman berbasis thread di Java bisa menjadi rumit ketika banyak thread berinteraksi, yang dapat membuat kode menjadi sulit dibaca dan dipelihara.
- Keterbatasan pada Blok Synchronized:
Penggunaan blok synchronized dapat mengurangi tingkat paralelisme, karena hanya satu thread yang dapat mengakses blok synchronized pada satu waktu.
- Masalah Liveness dan Safety:
Jika tidak dikelola dengan benar, aplikasi Java dapat mengalami masalah liveness (tidak ada kemajuan) dan safety (konsistensi data), yang dapat menyebabkan perilaku tak terduga.

## Erlang

## Kelebihan Erlang:

## Kekurangan Erlang:

#### Referensi

[1] [Ruangbacaku](https://www.ruangbacaku.com/detail-artikel/apa-itu-golang-kelebihan-dan-alasan-mengapa-harus-mempelajarinya).


[2] [Logique](https://www.logique.co.id/blog/2019/08/19/bahasa-pemrograman-golang/).

[3] [Silicon Review](https://thesiliconreview.com/2024/08/go-in-2024-an-in-depth-analysis-and-comparison-to-other-languages).

[4] [ChatGPT(Java)](https://chatgpt.com/share/66f52e09-0f34-8010-906b-9aead7128468)


---

## Studi Kasus

### Race Condition

### Deadlock

---
