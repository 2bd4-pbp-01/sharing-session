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
Java dirancang oleh James Gosling di Sun Microsystems (sekarang milik Oracle) pada tahun 1995, dan merupakan salah satu bahasa pemrograman yang paling populer di dunia. Salah satu kekuatan utama Java adalah kemampuannya menangani multithreading dengan baik, membuatnya ideal untuk concurrent programming dalam skala besar.[3] Dengan dukungannya yang kuat untuk konkurensi berbasis thread, Java adalah salah satu bahasa yang paling populer untuk pemrograman konkuren.[2] Java adalah bahasa populer yang sering digunakan di berbagai industri, terutama di perusahaan besar. Java memiliki dukungan kuat untuk multithreading dan concurrent programming melalui berbagai API bawaan yang powerful.[3]

__USE CASE__

Perbankan, E-commerce, dan Aplikasi Enterprise yang memerlukan sistem backend kuat sering kali menggunakan Java untuk concurrent programming. Contoh: Netflix menggunakan Java untuk sebagian besar sistemnya yang berfokus pada manajemen beban kerja concurrent secara efisien.[3]

#### 2. Golang
Go atau Golang diciptakan oleh Google pada tahun 2009, dengan tujuan utama untuk menyederhanakan concurrency dan membuat pemrograman berskala besar lebih mudah dikelola. Bahasa ini terkenal dengan kecepatan eksekusi, kesederhanaan, dan dukungan concurrent programming yang kuat.[3] Go (Golang) dirancang dengan mempertimbangkan konkurensi dan memiliki dukungan asli untuk pemrograman konkuren ringan menggunakan “goroutines” dan saluran. [2] Go adalah bahasa pemrograman yang dirancang oleh Google untuk menangani concurrent programming secara efisien dan mudah digunakan. Go menonjol karena kesederhanaannya dalam mengelola concurrent tasks dibandingkan dengan bahasa lain.[3]

__USE CASE__

Go digunakan oleh banyak perusahaan besar seperti Google, Uber, Dropbox, dan Docker untuk menangani concurrent programming dalam layanan web, microservices, dan aplikasi cloud-native. Contoh: Kubernetes, salah satu platform container orchestration terkemuka, dibangun menggunakan Go.

#### 3. Erlang
Dibuat oleh Ericsson pada akhir 1980-an, Erlang dirancang untuk menangani sistem telekomunikasi yang membutuhkan high availability, scalability, dan fault tolerance.[3] Bahasa pemrograman fungsional ini dirancang khusus untuk konkurensi, toleransi kesalahan, dan distribusi, Erlang terkenal karena penggunaannya dalam infrastruktur telekomunikasi dan sistem server yang sangat konkuren.[2] Erlang dirancang khusus untuk concurrent programming sejak awal pembuatannya. Bahasa ini dikembangkan oleh perusahaan telekomunikasi Ericsson untuk sistem yang membutuhkan keandalan tinggi dan mampu menangani banyak proses secara bersamaan.[3] 

__USE CASE__

WhatsApp menggunakan Erlang untuk menangani jutaan pengguna dengan kinerja yang sangat tinggi. Sistem telekomunikasi, game online, dan perangkat lunak mission-critical yang membutuhkan keandalan juga memanfaatkan Erlang.[3]

#### Referensi
[1] [Bilginc](https://bilginc.com/en/blog/concurrent-programming-languages-5908/#:~:text=Go%20(Golang)%3A%20Developed%20by,and%20provides%20robust%20concurrency%20mechanisms)

[2] [StudySmarter](https://www.studysmarter.co.uk/explanations/computer-science/computer-programming/concurrent-programming/)

[3] [ChatGPT](https://chatgpt.com/share/66f52e95-5f00-8002-b2c7-d029cb98ac9e)


### Pros/Cons setiap Bahasa Pemrograman

## Golang

## Kelebihan Golang:
1. Dukungan Concurrency yang Kuat: Goroutines dan channels memudahkan pengelolaan banyak tugas sekaligus, ideal untuk aplikasi server dan microservices.[1]​[2]
2. Garbage Collector yang Efisien: Mengelola memori secara otomatis, mengurangi beban pengembang.[1]​[2]
3. Sintaks yang Sederhana: Mudah dipahami dan dipelajari, dengan dokumentasi yang komprehensif.[1]​[2]
4. Skalabilitas Tinggi: Bekerja baik pada berbagai inti CPU, cocok untuk infrastruktur cloud dan sistem terdistribusi.[3]​[2]
5. Ekosistem yang Mapan: Pustaka standar yang kaya dan banyak pustaka pihak ketiga.[3]​[2]

## Kekurangan Golang:
1. Kurangnya Pustaka untuk Aplikasi Monolitik: Kurang memiliki kerangka kerja matang dibandingkan Java atau C#.[3]​[2]
2. Pengelolaan Kesalahan yang Verbose: Penanganan kesalahan dapat membuat kode terlihat rumit.[3]​[2]
3. Waktu Kompilasi yang Lama: Meskipun lebih cepat dari C++, proyek besar dapat mengalami waktu kompilasi yang lama.[3]​[2]


## Java

## Kelebihan Java:
1. Model Thread yang Sederhana:
Java menyediakan API yang sederhana untuk membuat dan mengelola thread melalui kelas Thread dan antarmuka Runnable. Ini memungkinkan pengembang untuk dengan mudah membuat aplikasi yang memanfaatkan pemrosesan paralel.[4]
2. Dukungan Built-in untuk Synchronization:
Java memiliki kata kunci synchronized yang memungkinkan pengembang untuk mengontrol akses ke sumber daya yang dibagikan oleh beberapa thread, membantu mencegah race condition.[4]
3. Paket Concurrency yang Kaya:
Java menyediakan paket java.util.concurrent, yang mencakup berbagai kelas dan antarmuka untuk mendukung pemrograman konkuren, seperti ExecutorService, CountDownLatch, dan Semaphore. Ini membuat manajemen thread lebih mudah dan lebih efisien.[4]
4. Fork/Join Framework:
Java menawarkan framework fork/join yang memungkinkan pembagian tugas menjadi sub-tugas yang lebih kecil, sehingga memudahkan pemrograman paralel dan memaksimalkan penggunaan CPU.[4]
5. Garbage Collection Otomatis:
Java mengelola memori secara otomatis, yang membantu mengurangi masalah kebocoran memori yang sering muncul dalam aplikasi konkuren.[4]

## Kekurangan Java:
1. Overhead Kinerja:
Meskipun Java menawarkan banyak fitur untuk concurrency, penggunaan thread dapat menghasilkan overhead, terutama jika banyak thread yang dibuat dan dihancurkan secara berulang.[4]
2. Kompleksitas dalam Debugging:
Aplikasi konkuren dapat menjadi sulit untuk didiagnosis dan di-debug, dengan masalah seperti deadlock dan race condition yang sulit dideteksi.[4]
3. Keterbatasan dalam Model Pemrograman:
Model pemrograman berbasis thread di Java bisa menjadi rumit ketika banyak thread berinteraksi, yang dapat membuat kode menjadi sulit dibaca dan dipelihara.[4]
4. Keterbatasan pada Blok Synchronized:
Penggunaan blok synchronized dapat mengurangi tingkat paralelisme, karena hanya satu thread yang dapat mengakses blok synchronized pada satu waktu.[4]
5. Masalah Liveness dan Safety:
Jika tidak dikelola dengan benar, aplikasi Java dapat mengalami masalah liveness (tidak ada kemajuan) dan safety (konsistensi data), yang dapat menyebabkan perilaku tak terduga.[4]

## Erlang

## Kelebihan Erlang:
1. Desain dari Awal untuk Konkurensi: Erlang dirancang dengan dukungan konkuren dan paralelitas sebagai fitur inti. Proses-proses ringan dalam Erlang dapat dieksekusi secara paralel dan berkomunikasi melalui pengiriman pesan, yang memudahkan pembangunan sistem yang sangat konkuren​.[5]

2. Model Proses Ringan: Proses di Erlang sangat ringan, memungkinkan pembuatan jutaan proses tanpa mengurangi kinerja. Hal ini memudahkan pengelolaan dan pemrograman aplikasi dengan banyak pengguna secara bersamaan​.[5]

3. Toleransi Terhadap Kesalahan: Dengan filosofi "Let it Crash", Erlang mengizinkan proses yang gagal untuk dimulai kembali secara otomatis. Ini meminimalkan kebutuhan untuk kode yang berlebihan untuk penanganan kesalahan, dan memungkinkan sistem untuk tetap berjalan meskipun ada kesalahan yang terjadi​.[5]

4. Supervisi Proses: Dengan penggunaan supervision tree, Erlang memudahkan pemantauan dan pengelolaan proses. Supervisor bertanggung jawab atas proses anak dan dapat memulai ulang mereka jika terjadi kesalahan, yang meningkatkan keandalan sistem​.[5]

5. Hot Code Loading: Fitur ini memungkinkan pengembang untuk memperbarui kode tanpa menghentikan sistem, sehingga cocok untuk aplikasi yang memerlukan ketersediaan tinggi, seperti sistem telekomunikasi​.[5]
## Kekurangan Erlang:
1. Learning Curve: Walaupun memiliki banyak keunggulan, Erlang memiliki learning curve yang cukup tinggi, terutama bagi pengembang yang terbiasa dengan paradigma pemrograman yang berbeda. Struktur dan sintaksis Erlang bisa terasa asing bagi banyak orang​.[5]

2. Performa untuk Tugas Berbasis Komputasi Intensif: Untuk aplikasi yang sangat bergantung pada pemrosesan komputasi berat, performa Erlang dapat kalah dibandingkan dengan bahasa lain yang lebih berorientasi pada kecepatan eksekusi​.[5]

3. Ekosistem yang Terbatas: Meskipun Erlang banyak digunakan dalam beberapa domain, ekosistem pustaka dan alat pendukungnya lebih kecil dibandingkan bahasa pemrograman lainnya, seperti Java atau Python. Hal ini bisa membatasi pilihan dan fleksibilitas pengembang​.[5]

4. Pengelolaan Memori: Meskipun Erlang memiliki memory footprint yang kecil, pengelolaan memori untuk sejumlah besar proses bisa menjadi tantangan dan mungkin memerlukan optimasi lebih lanjut​.[5]

#### Referensi

[1] [Ruangbacaku](https://www.ruangbacaku.com/detail-artikel/apa-itu-golang-kelebihan-dan-alasan-mengapa-harus-mempelajarinya).


[2] [Logique](https://www.logique.co.id/blog/2019/08/19/bahasa-pemrograman-golang/).

[3] [Silicon Review](https://thesiliconreview.com/2024/08/go-in-2024-an-in-depth-analysis-and-comparison-to-other-languages).

[4] [ChatGPT(Java)](https://chatgpt.com/share/66f52e09-0f34-8010-906b-9aead7128468)

[5] [ChatGPT(Erlang)](https://chatgpt.com/share/66f53a9a-be98-8010-bd72-a8a51f495cd8)

---

## Studi Kasus

### Race Condition

Race condition adalah masalah umum dalam pemrograman concurrent yang terjadi ketika hasil akhir dari program bergantung pada urutan atau timing dari eksekusi thread. Kondisi ini dapat menyebabkan perilaku tak terduga, yang sering kali sulit untuk di-debug.
![image](https://uploads.sitepoint.com/wp-content/uploads/2017/02/1486567898race-condition.jpg)
Race condition terjadi ketika dua atau lebih thread atau proses secara bersamaan mengakses dan memodifikasi shared resource tanpa adanya mekanisme sinkronisasi yang memadai. Hal ini menyebabkan urutan eksekusi yang tidak terprediksi, yang dapat menyebabkan bug atau hasil yang tidak diinginkan.


### Deadlock

---
