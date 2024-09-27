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

- [Referensi](#referensi)

  ***

## Functional

### Overview

Functional programming (FP) adalah paradigma pemrograman yang berfokus pada penggunaan pure functions, yaitu fungsi yang selalu menghasilkan output yang sama untuk input yang sama dan tidak memiliki side effects[^4]. Dalam FP, konsep seperti data immutability (data yang tidak dapat diubah) dan penghindaran shared state (berbagi status) sangat penting. FP menggunakan pendekatan deklaratif, yang lebih berfokus pada "apa yang harus dilakukan" dibandingkan dengan pendekatan imperatif yang menginstruksikan "bagaimana melakukannya"[^2]

Dasar-Dasar Functional Programming

1. **Pure Functions**: Fungsi yang selalu memberikan hasil yang sama untuk input yang sama dan tidak memiliki side effect.

2. **Immutable Data**: Setelah data dibuat, tidak dapat diubah, sehingga menghindari masalah yang tidak terduga.

3. **First-Class Functions**: Fungsi diperlakukan seperti data lainnya, dapat diteruskan sebagai argumen atau dikembalikan dari fungsi lain.

4. **Recursion**: Fungsi dapat memanggil dirinya sendiri untuk melakukan iterasi tanpa menggunakan loop tradisional.

5. **Higher-order Functions**: Fungsi yang dapat menerima fungsi lain sebagai argumen atau mengembalikannya.

### Kenapa Perlu Menggunakan Functional Programming

Ada beberapa alasan untuk memilih functional programming[^3]:

1. **Kode Lebih Terstruktur dan Bersih**: Karena fungsi-fungsi murni dan sifat immutability, kode menjadi lebih mudah diprediksi dan dipelihara.

2. **Mendukung Pemrograman Paralel**: FP secara alami mendukung pemrograman paralel, karena tidak adanya shared state mengurangi potensi konflik saat fungsi berjalan secara bersamaan.

3. **Memudahkan Testing dan Debugging**: Karena FP menghindari side effect, testing dan debugging lebih sederhana, karena fungsi tidak bergantung pada status eksternal​

4. **Keringkasan**: Mengurangi jumlah kode yang perlu ditulis.

5. **Prediktabilitas**: Kode lebih mudah dipahami karena tidak ada side effect.

6. **Modularitas**: Fungsi murni dapat digunakan di berbagai tempat tanpa ketergantungan pada konteks luar.

### Pros/Cons

Adapun kelebihan yang dimiliki Functional programming[^1], diantaranya:

- **Lebih mudah diuji**: Tanpa adanya side effect, memverifikasi fungsi dalam FP menjadi lebih sederhana;
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

<p align="center">
  <img src="https://raw.githubusercontent.com/SAWARATSUKI/KawaiiLogos/refs/heads/main/Haskell/haskell.png" alt="haskell" />
  </br>
  <sub>Haskell logo by <a href="https://github.com/SAWARATSUKI/KawaiiLogos/tree/main/Haskell">Sawaratsuki</a></sub>
</p>

### Overview Haskell

Haskell adalah Bahasa pemrograman general purpose, statically typed, functional murni yang mendukung type inference, dan lazy evaluation yang pertama muncul di akhir tahun 80an dan mengeluarkan stable release pada tahun 2010. Haskell didesain untuk pengajaran, riset, dan aplikasi industri. Bahasa ini dikenal sebagai pelopor fitur seperti type class dan monadic I/O, serta menggunakan compiler Glasgow Haskell Compiler (GHC).

Di Haskell, function dan value diperlakukan sama yaitu dengan mengevaluasi expression bukan mengeksekusi perintah. Haskell beroperasi berdasarkan konsep pure expression, yang memiliki sifat immutable (value tidak dapat diubah), tanpa side effects (tidak mengubah state), dan deterministic (argumen yang sama menghasilkan output yang sama)[^5].

[^5]: <https://global.thepower.education/blog/what-is-haskell-and-what-is-it-for>

Dengan dukungan lazy evaluation, expression dalam Haskell hanya dievaluasi ketika dibutuhkan, yang bisa meningkatkan performa namun membuat penggunaan memori saat runtime tidak dapat diprediksi. Haskell juga merupakan bahasa dengan static typing, artinya tipe setiap expression ditentukan saat kompilasi, sehingga program dengan type error tidak dapat dikompilasi atau dijalankan.

### Tipe Data (_Data Type_)

Haskell mendukung type inference dimana compiler akan tau tipe data yang digunakan namun programmer bisa secara eksplisit mendeklarasi data type yang digunakan menggunakan syntax sebagai berikut

```hs
x :: Int
x = 3
```

#### 1. Basic Data Types

- **Int**: Menampung value angka dan dipastikan bisa menampung value paling tidak ±2^29 tapi sizenya bergantung pada arsitektur mesin yang dipakai (mesin 64-bit bisa sampai ±2^63)
- **Integer**: Menampung value angka dan kapasitasnya dibatasi memory mesin yang dipakai
- **Float**: Single precision floating-point numbers, jarang dipakai karena kurang presisi
- **Double**: Double-precision floating-point numbers, lebih sering dipakai untuk angka berdesimal
- **Boolean**: Berisi logical value 'true' dan 'false'
- **Char**: Menampung satu karakter unicode

#### 2. Composite Data Types

- **List**: Kumpulan terurut element dengan satu tipe data yang sama
- **String**: List of Char
- **Tuple**: Kumpulan terurut element bertipe apapun

#### 3. Algebraic Data Types

Enumeration

```hs
data Thing = Shoe
      | Ship
      | SealingWax
      | Cabbage
      | King
  deriving Show
```

#### 4. Type Classes

Type `Class` adalah serangkaian method yang digunakan bersama oleh beberapa type, konsepnya mirip dengan generic programming.

Contoh typeclass:

```hs
class Num a where
  (+) :: a -> a -> a
  (-) :: a -> a -> a
  (*) :: a -> a -> a
  negate :: a -> a
  abs :: a -> a
  signum :: a -> a
  fromInteger :: Integer -> a
```

Agar suatu tipe termasuk dalam type class `Num`, tipe tersebut perlu mengimplementasikan metode-metodenye dan metode tersebut hanya bisa dipakai pada tipe yang memiliki instance `Num`. Jika metode tersebut mengambil anggota diluar typeclass-nya code tidak akan di-compile.

Penggunaan

```hs
plusOnePoly :: Num a => a -> a
plusOnePoly a = a + 1
```

### Modularitas

#### 1. Self-Defined Modules

Self-Defined module adalah modul atau library yang dibuat oleh
pengembang / developer itu sendiri.

```hs
module Geometry
( sphereVolume
, sphereArea
) where

sphereVolume :: Float -> Float
sphereVolume radius = (4.0 / 3.0) * pi * (radius ^ 3)

sphereArea :: Float -> Float
sphereArea radius = 4 * pi * (radius ^ 2)
```

#### 2. Standard Library

Standary library merupakan library yang disediakan oleh Haskell secara default.
Fungsinya memberikan utility untuk hal umum seperti interaksi dengan Input/output
(IO). [Dokumentasi resmi Haskell](https://hackage.haskell.org/package/base) menyediakan
daftar standary library yang ada dan dapat digunakan.

Berikut sintaks untuk melakukan import modul dalam kode Haskell

```hs
import <Nama.Modul>
```

Contoh:

```hs
import Data.List
```

Cara pemakaiannya mirip dengan memanggil modul pada umumnya. seperti contoh berikut dalam library data list:

```hs
numUniques :: (Eq a) => [a] -> Int
numUniques = length . nub
```

#### 3. External Library / Dependencies

External atau shared library / dependencies merupakan library yang tersedia
secara online dan umumnya bisa digunakan oleh siapapun. External library
tidak dibuat oleh mengembang yang mengelola Haskell melainkan, dapat dibuat
oleh siapapun. Haskell menyediakan repositori bernama [Hackage](https://hackage.haskell.org/)
untuk mencari external library yang dapat digunakan.

Untuk melakukan instalasi dapat menggunakan [package manager atau build tools](#haskell-development-environments)
seperti [Cabal](https://www.haskell.org/cabal/) atau [Stack](https://docs.haskellstack.org/en/stable/).

Berikut contoh melakukan instalasi dengan [Cabal](https://www.haskell.org/cabal/).

```sh
cabal install cabal-install
cabal --version # melakukan verifikasi instalasi
```

Setelah melakukan instalasi, dapat melakukan import external shared library
seperti melakukan import pada libary pada umumnya.

```hs
import <nama.External.Library>
```

### Keamanan Tipe (_Type Safety_)

Haskell merupakan bahasa pemrograman yang statically typed dimana program dievaluasi oleh kompiler dan dikompilasi menjadi bytecode sebelum dijalankan.

Program Haskell harus diperiksa tipenya sebelum dikompilasi dan kode dieksekusi. Jika ada kesalahan dalam tipe data, kode akan gagal dicompile dan tidakbisa dijalankan. Haskell hanya melakukan pemeriksaan tipe satu kali, yang membantu meningkatkan kinerja secara keseluruhan, dibandingkan dengan bahasa lain seperti Java yang melakukannya lebih dari satu kali[^6].

Haskell dianggap kuat karena risiko kesalahannya rendah. Error safety pada waktu kompilasi bagus, yang berarti setelah dikompilasi kode pasti bisa berfungsi dengan baik.

[^6]: <https://scrapingrobot.com/blog/haskell-programing-language/>

### Error dan Exception Handling

#### 1. Exception

Unexpected code path, biasanya disebabkan oleh kesalahan IO seperti file handling,
network failures atau system-level issues lain.

Berikut contohnya:

```hs
import Control.Exception (Exception, throw, try, SomeException)

-- Define a custom exception
data MyException = SomethingWentWrong deriving (Show, Typeable)
instance Exception MyException

-- Example function that throws an exception
riskyFunction :: IO ()
riskyFunction = throw SomethingWentWrong

-- Handling the exception
main :: IO ()
main = do
  result <- try riskyFunction :: IO (Either SomeException ())
  case result of
    Left ex  -> putStrLn $ "Caught exception: " ++ show ex
    Right _  -> putStrLn "Everything went fine"
```

#### 2. Pure Code

Method ini harus dihindari dalam kebanyakan kasus karena penggunaan error akan membuat program crash jika terjadi situasi yang tidak valid.
Method ini dapat digunakan dalam skenario sederhana ketika kegagalan tidak dapat dihindari atau logika program sudah rusak.
Alternatif yang lebih aman seperti Maybe atau Either harus lebih dipilih untuk mencegah terjadinya crash.

Berikut contohnya:

```hs
-- Using error in pure code (not recommended for safe programs)
headSafe :: [a] -> a
headSafe [] = error "empty list"
headSafe (x:_) = x
```

#### 3. Either Type

`Either` digunakan ketika kesalahan expected dan merupakan bagian dari regular program logic. Either memungkinkan pengembalian error beserta hasil yang berhasil secara terstruktur. Hal ini umum terjadi dalam penguraian, validasi, atau perhitungan dimana kesalahan bersifat biasa dan tidak menunjukkan logika yang rusak, hanya input yang salah.

Berikut contohnya:

```hs
-- Define an error type
data ParseError = ParseError String deriving (Show)

-- A function that returns Either error or success
parseValue :: String -> Either ParseError Int
parseValue str =
  case reads str of
    [(val, "")] -> Right val
    _           -> Left (ParseError "Failed to parse the integer")

-- Handling the Either result
main :: IO ()
main = do
  let result = parseValue "123a"
  case result of
    Left err     -> print ("Error: " ++ show err)
    Right value  -> print ("Parsed value: " ++ show value)
```

#### 4. Missing Value dengan Maybe

`Maybe` digunakan saat tidak adanya nilai bukan menunjukan kesalahan tetapi kondisi normal. `Maybe` berguna ketika expected suatu value mungkin tidak ada, tetapi tidak perlu menjelaskan mengapa value itu tidak ada. Contohnya seperti pada search engine[^12].

Berikut contohnya:

```hs
-- Lookup function returning Maybe
lookupValue :: Eq a => a -> [(a, b)] -> Maybe b
lookupValue key list = lookup key list

-- Handling the Maybe result
main :: IO ()
main = do
  let dictionary = [("age", 25), ("name", "John")]
  case lookupValue "age" dictionary of
    Nothing    -> putStrLn "No value found"
    Just value -> putStrLn $ "Found value: " ++ show value

-- Or using the maybe function for simpler code
main2 :: IO ()
main2 = do
  let dictionary = [("age", 25), ("name", "John")]
  putStrLn $ maybe "No value found" (\v -> "Found value: " ++ show v) (lookupValue "age" dictionary)
```

[^12]: <https://wiki.haskell.org/Handling_errors_in_Haskell>

### Fun Facts

- Pada bulan Mei 2021 Haskell merupakan Bahasa pemrograman terpopuler ke-28 berdasarkan pencarian tutorial pada search engine dan memiliki pengguna aktif GitHub aktif sebanyak kurang dari 1%[^7].

[^7]: "PYPL PopularitY of Programming Language index". pypl.github.io. May 2021. Archived from the original on 7 May 2021. Retrieved 16 May 2021.

- Haskell memiliki beberapa versi sebelum menjadi Haskell pada hari ini yaitu versi 1.0, 1.1, 1.2, 1.3, 1.4, dan 98[^8].

[^8]: Hudak, Paul; Hughes, John; Peyton Jones, Simon; Wadler, Philip (2007). "A history of Haskell" (PDF). Proceedings of the third ACM SIGPLAN conference on History of programming languages. pp. 12–1–55. doi:10.1145/1238844.1238856. ISBN 978-1-59593-766-7. S2CID 52847907.

#### Memory Management

Komputasi Haskell menghasilkan banyak memory garbage yang jauh lebih banyak daripada bahasa imperatif konvensional. Hal ini dikarenakan data tidak dapat diubah sehingga satu-satunya cara untuk menyimpan hasil setiap operasi berikutnya adalah dengan membuat nilai baru. Khususnya, setiap iterasi perhitungan rekursif menghasilkan nilai baru. Namun GHC mampu mengelola garbage collection secara efisien, sehingga tidak jarang untuk menghasilkan 1gb data per detik (sebagian besar akan langsung masuk garbage collector)[^9][^10].

[^9]: Marlow, Simon; Harris, Tim; James, Roshan P.; Jones, Simon Peyton. 2008. [_Parallel Generational-Copying Garbage Collection with a Block-Structured Heap_](https://simonmar.github.io/bib/papers/parallel-gc.pdf).

#### High-Order Function

Fungsi pada Haskell dapat mengambil fungsi lain sebagai parameter dan mengembalikan fungsi sebagai return value. Fungsi yang melakukan salah satu dari itu disebut High-Order Function. Jika ingin mendefinisikan komputasi hanya dengan mendefinisikan apa yang ingin dituju dan bukan step-by-step Hig-Orger Function tidak bisa tergantikan[^10].

[^10]: <https://www.schoolofhaskell.com/user/school/starting-with-haskell/introduction-to-haskell/4-higher-order-programming-and-type-inference#anonymous-functions>

#### Monad

Konsep dasar yang digunakan untuk menangani komputasi yang mencakup side effect (seperti state, IO, exceptions, atau non-determinism) dengan cara yang murni fungsional. Monad menyediakan struktur yang konsisten untuk operasi berantai (chain operation), mengelola konteks (seperti possible failure, state transitions, atau IO operations), dan mengabstraksi side effect.

Monad dalam Haskell adalah type class dengan tiga komponen utama[^11]:

- **return (pure dalam konteks applicative)**: Wrapping nilai dalam konteks monad.

- **`>>=` (bind)**: Merantai operasi manjadi satu, meneruskan hasil dari satu operasi ke operasi berikutnya.

- **Hukum monad**: Tiga hukum yang memastikan bahwa monad berperilaku secara konsisten.

  - Left identity: `return a` >>= `h` ≡ `h a`
  - Right identity: `return a` >>= `h` ≡ `h a`
  - Associativity: `m >>= g` >>= `h` ≡ `m >>= (\x -> g x >>= h)`

> [!NOTE]
> Jika tertarik lebih lanjut mengenai Monad, terdapat [website](https://www.adit.io/posts/2013-04-17-functors,_applicatives,_and_monads_in_pictures.html) yang menjelaskan Monad dengan ilustrasi yang menarik.

`p ≡ q` berarti variabel `p` dapat diganti `q` atau sebaliknya, dan perilaku
dari program tidak akan berubah karena `p` dan `q` ekuivalen.

[^11]: <https://wiki.haskell.org/All_About_Monads>

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

   Haskell adalah bahasa pemrograman yang memerlukan compiler untuk menjalankan
   programnya. Sehingga tool paling utama yang diperlukan yaitu compiler,bernama
   GHC (Glasgow Haskell Compiler). GHC merupakan compiler yang berbasis open-source
   dan memungkinkan untuk berjalan di platform / sistem operasi yang berbeda meliputi
   Linux, macOS, Windows, dan lainnya.

> [!NOTE]
> Selain digunakan untuk melakukan kompilasi pada program Haskell, GHC juga
> mendukung extensions, library, dan beberapa parameter untuk melakukan
> optimisasi pada saat proses kompilasi program.

2. Language Server

   Haskell Language server (HSL) berjalan di latar belakang dan digunakan oleh kode
   editor atau IDE untuk memberikan pengalaman yang lebih baik pada saat menulis
   kode Haskell, seperti adanya fitur _syntax highlighting_ yang berfungsi membuat
   kode lebih terbaca. Selain itu memberikan fitur _auto suggestion_ yang berfungsi
   untuk memberikan kemudahan pencarian pada library, modul, function, dan variabel
   yang telah dibuat.

3. Build Tools

   Build tools merupakan tool untuk mengelola project Haskell. Dengan menggunakan
   build tools, pengelolaan seperti build project (melakukan kompilasi pada serangkaian
   file), menjalankan program, mengelola dependencies, dan library eksternal dapat
   lebih mudah. Terdapat 2 build tools yang populer di Haskell, yaitu [Cabal](https://www.haskell.org/cabal/)
   dan [Stack](https://docs.haskellstack.org/en/stable/).

### 2D Graphics dengan OpenGL dan Haskell

**💻 Source Code**: [github.com/2bd4-pbp-01/pbp_12_experiment/tree/main/haskell-opengl](https://github.com/2bd4-pbp-01/pbp_12_experiment/tree/main/haskell-opengl)

#### Skenario

Mengimplementasikan libary OpenGL dengan membuat objek 2D dari mulai
yang sederhana hingga interaktif.

Beberapa library eksternal yang digunakan yaitu

- [OpenGL](https://hackage.haskell.org/package/OpenGL)

  Library yang digunakan untuk menghubungkan Haskell dengan
  OpenGL graphics system.

- [GLUT](https://hackage.haskell.org/package/GLUT)

  Libary yang menyediakan toolkit sistem window untuk mengembangkan
  program berbasis OpenGL.

- [GLFW-b](https://hackage.haskell.org/package/GLFW-b)

  Library untuk mengelola window dengan konteks dari OpenGL dan
  mengelola input dan event sehingga objek 2D yang dibuat dapat
  lebih interaktif.

#### Why?

Haskell adalah Bahasa paling dekat dengan konsep-konsep matematis. Grafik 2d banyak menggunakan operasi geometri, transformasi, dan fungsi matematika lain sehingga penulisan persamaan dan fungsi matematika untuk memanipulasi bangun datar sangat didukung dengan Haskell. Setiap gambar dan trasformasi merupakan hasil dari sebuah fungsi sehingga jika dilakukan manipulasi state sebelumnya tidak akan mempengaruhi gambar baru yang tercipta. Penggunaan Haskell juga lebih mudah karena menggunakan pendekatan deklaratif yang fokusnya lebih ke apa yang ingin digambar dan bukan bagaimana menggambarnya.

---

### Referensi

- Haskell Official Documentation. Retrieved from: <https://wiki.haskell.org/Haskell>.
- Lipovača, Miran. 2021. [_Learn You a Haskell_](https://learnyouahaskell.github.io/). Retrieved from 20 Sep 2024.
- O'Sullivan, Bryan; Stewart, Don; Goerzen, John. 2008. [_Real World Haskell_](https://book.realworldhaskell.org/read/). Retrieved from 26 Sep 2024.
- Snoyman, Michael, _et al_. 2013. [_School of Haskell_](https://www.schoolofhaskell.com/school/starting-with-haskell/introduction-to-haskell). Introduction to Haskell. Retrieved from 26 Sep 2024.
