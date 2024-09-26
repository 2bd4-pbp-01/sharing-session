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
Concurrency berarti multiple computations yang terjadi secara bersamaan tanpa harus menunggu computation lainnya diselesaikan terlebih dahulu. Dalam pemrograman modern, concurrency sangat penting karena:

1. Situs web harus menangani banyak pengguna secara bersamaan.
2. Aplikasi mobile sering melakukan pemrosesan di server ("di cloud").
3. Graphical user interfaces memerlukan pekerjaan latar belakang yang tidak mengganggu pengguna.

#### Concurrent Programming 
Concurrent Programming adalah model pemrograman yang memungkinkan berbagai bagian dari program berjalan secara concurrent atau tumpang tindih. Dalam pemrograman ini, kamu dapat menulis kode yang memungkinkan berbagai proses atau thread untuk bekerja bersama tanpa harus menunggu salah satu selesai sebelum yang lainnya dimulai. Dengan menggunakan teknik seperti threads, processes, atau coroutines, concurrent programming menjadi landasan penting untuk meningkatkan efisiensi dan kecepatan eksekusi pada sistem modern.

#### Dua Model Concurrent programming
Ada dua model umum untuk Concurrent programming :

1. Shared Memory: Modul-modul yang berjalan secara bersamaan berinteraksi dengan membaca dan menulis objek yang dibagikan dalam memori.
2. Message Passing: Modul-modul berinteraksi dengan mengirim pesan melalui saluran komunikasi, di mana pesan yang masuk dikelola dalam antrean.

### Concurrent vs Asynchronous

#### Concurrency :
Concurrency adalah konsep di mana banyak tugas dapat berjalan tumpang tindih atau bersamaan. Di sistem multi-core, beberapa tugas bisa berjalan benar-benar paralel, tetapi pada sistem dengan satu CPU, eksekusi dilakukan secara bergantian dengan cepat menggunakan time-slicing. Ini memungkinkan satu program untuk menangani beberapa tugas sekaligus, seperti menangani beberapa koneksi klien di server web.

#### Asynchronus :
Asynchronus programming berfokus pada penanganan tugas-tugas yang memerlukan operasi I/O, di mana satu tugas dapat menunggu (misalnya saat menunggu data dari jaringan atau disk) tanpa menghentikan seluruh aplikasi. Pada pemrograman sinkron biasa, sebuah thread akan diblokir saat menunggu operasi I/O selesai. Dalam pemrograman asinkron, tugas tidak akan memblokir thread utama, tetapi akan menjalankan tugas lainnya selama menunggu hasil operasi. Ini sering digunakan pada sistem yang banyak berurusan dengan operasi I/O yang lambat.

#### Perbedaan Concurrency dengan Asynchronus Programming :
Concurrency berfokus pada menjalankan banyak tugas yang tumpang tindih dalam satu atau beberapa thread. Di sini, pemrograman biasanya melibatkan sinkronisasi dan manajemen thread agar tidak terjadi konflik data atau masalah seperti race conditions. Sedangkan Asynchronous Programming fokus pada operasi I/O yang lambat, di mana alih-alih memblokir seluruh program saat menunggu hasil dari operasi tersebut, thread dapat melanjutkan tugas lain. Ini membuat pemrograman asinkron lebih efisien dalam menangani operasi I/O daripada pendekatan concurrent yang sinkron.

---

## Implementasi pada Bahasa Pemrograman

### Bahasa Pemrograman yang Mendukung Concurrent

#### Golang

#### <isi/ganti-dengan-bahasa-pemrogramannya>

### Pros/Cons setiap Bahasa Pemrograman

---

## Studi Kasus

### Race Condition

### Deadlock

---
