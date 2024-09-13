---
title: Tentukan Halaman Saat Melihat
linktitle: Tentukan Halaman Saat Melihat
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menentukan halaman yang akan dilihat dalam PDF menggunakan Aspose.PDF untuk .NET. Tingkatkan navigasi pengguna dengan panduan sederhana ini.
type: docs
weight: 110
url: /id/net/programming-with-links-and-actions/specify-page-when-viewing/
---
## Perkenalan

Apakah Anda ingin menyempurnakan aplikasi PDF Anda dengan mengarahkan pengguna ke halaman tertentu saat membuka dokumen? Anda telah datang ke tempat yang tepat! Dalam panduan ini, kita akan membahas seluk-beluk penggunaan Aspose.PDF untuk .NET guna menentukan halaman yang harus ditampilkan saat PDF dibuka. Fungsionalitas ini dapat meningkatkan pengalaman pengguna secara signifikan, terutama saat Anda perlu menarik perhatian ke bagian penting dokumen Anda.

## Prasyarat

Sebelum mulai membuat kode, pastikan Anda memiliki semua yang dibutuhkan untuk memulai. Berikut ini yang Anda perlukan:

1. Pengetahuan Dasar tentang .NET: Keakraban dengan kerangka kerja .NET sangatlah penting. Jika Anda merasa nyaman dengan C# dan memiliki pemahaman dasar tentang pemrograman berorientasi objek, Anda siap!

2.  Aspose.PDF untuk .NET: Anda perlu menginstal pustaka Aspose.PDF di proyek Anda. Jika Anda belum menginstalnya, Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/pdf/net/).

3. Visual Studio: Tutorial ini mengasumsikan Anda menggunakan Visual Studio sebagai IDE. Pastikan Anda telah menginstalnya di komputer Anda.

4. Berkas PDF: Anda memerlukan berkas PDF yang sudah ada yang akan Anda gunakan. Jika belum memilikinya, Anda dapat membuat contoh dokumen atau menggunakan PDF pilihan Anda.

Setelah prasyarat ini terpenuhi, kita bisa mulai membuat kode!

## Paket Impor

Sekarang setelah semuanya siap, mari impor paket-paket yang diperlukan ke dalam proyek kita. Ikuti langkah-langkah berikut:

### Mulai Visual Studio

Buka Visual Studio dan buat proyek baru atau muat proyek yang sudah ada di mana Anda ingin mengimplementasikan fungsionalitas tampilan halaman PDF.

### Referensi Aspose.PDF

Untuk menggunakan pustaka Aspose.PDF, Anda perlu menambahkan referensi ke dalamnya:

1. Klik kanan pada proyek Anda di Solution Explorer.
2. Pilih 'Kelola Paket NuGet'.
3.  Pencarian untuk`Aspose.PDF` dan menginstal paket tersebut.

### Mengimpor Ruang Nama

Tambahkan perintah berikut di bagian atas berkas kode Anda:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Sekarang, Anda siap untuk mulai membangun logika navigasi halaman PDF Anda!

Mari kita bagi tugas kita menjadi beberapa langkah yang dapat dikelola. Kita akan menulis kode yang membuka dokumen PDF, menentukan halaman tertentu yang akan ditampilkan saat dilihat, dan menyimpan dokumen yang diperbarui. 

## Langkah 1: Mengatur Direktori Dokumen

Pertama, Anda perlu mengatur jalur ke dokumen Anda:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ganti dengan direktori Anda
```

 Baris ini pada dasarnya adalah peta jalan Anda. Anda memberi tahu kode Anda di mana menemukan file PDF. Pastikan untuk mengganti`YOUR DOCUMENT DIRECTORY` dengan jalur sebenarnya di mesin Anda.

## Langkah 2: Muat File PDF

Berikutnya, Anda akan memuat file PDF ke aplikasi Anda:

```csharp
// Muat file PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

 Apa yang terjadi di sini adalah Anda membuat contoh baru dari`Document`objek saat menentukan jalur ke berkas PDF Anda. Anda dapat menganggapnya sebagai membuka buku yang baru saja Anda taruh di atas meja.

## Langkah 3: Akses Halaman yang Diinginkan

Sekarang, mari mengakses halaman yang ingin Anda tampilkan saat dokumen dibuka:

```csharp
// Dapatkan contoh halaman kedua dokumen
Page page2 = doc.Pages[2]; // Ingat, pengindeksan dimulai pada 1
```

Di sini, kita mengakses halaman kedua dokumen Anda. Perlu dicatat bahwa penomoran halaman dimulai dari 1 dalam konteks ini, jadi jika Anda bermaksud halaman 2, Anda perlu menggunakan indeks 2.

## Langkah 4: Mengatur Faktor Zoom

Anda dapat menyesuaikan tingkat zoom untuk halaman yang akan ditampilkan:

```csharp
// Buat variabel untuk mengatur faktor zoom halaman target
double zoom = 1; // 1 berarti 100% zoom
```

Menetapkan faktor zoom membantu menentukan seberapa banyak halaman yang dapat dilihat pengguna segera setelah dibuka. Nilai 1 berarti halaman akan ditampilkan pada zoom 100%, yang umumnya merupakan nilai default yang baik.

## Langkah 5: Buat Instansi GoToAction

Mari kita gunakan fitur navigasi:

```csharp
// Buat instance GoToAction
GoToAction action = new GoToAction(doc.Pages[2]); 
```

 Pada langkah ini, Anda membuat sebuah instance dari`GoToAction` yang pada dasarnya mewakili tindakan menavigasi ke titik tertentu dalam PDF – dalam hal ini, halaman kedua.

## Langkah 6: Tentukan Tujuannya

Sekarang, Anda perlu menentukan ke mana tindakan tersebut harus mengarah:

```csharp
// Buka halaman 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

Baris ini seperti menetapkan tujuan GPS untuk GoToAction. Anda memberi tahunya untuk menuju ke halaman 2 di bagian atas halaman (ketinggian) dan pada tingkat zoom yang ditentukan.

## Langkah 7: Mengatur Tindakan Terbuka

Mari pastikan tindakan ini terjadi saat dokumen dibuka:

```csharp
// Mengatur tindakan membuka dokumen
doc.OpenAction = action;
```

Dengan ini, Anda telah menyatakan bahwa saat PDF Anda dibuka, tindakan navigasi yang baru saja kita definisikan diaktifkan. Ini seperti Anda telah menyiapkan keset selamat datang di pintu depan dokumen Anda.

## Langkah 8: Simpan Dokumen yang Diperbarui

Terakhir, mari simpan dokumen dengan perubahan yang dibuat:

```csharp
// Simpan dokumen yang diperbarui
doc.Save(dataDir + "goto2page_out.pdf");
```

Langkah ini menyelesaikan pekerjaan Anda! Anda akan memiliki file PDF baru bernama`goto2page_out.pdf` yang terbuka langsung ke halaman yang Anda tentukan.

Dengan demikian, bagian pengkodean telah selesai! Anda telah berhasil memprogram Aspose.PDF untuk menampilkan halaman tertentu saat PDF dibuka. 

## Kesimpulan

Dalam panduan ini, kami telah mengambil pendekatan langkah demi langkah untuk memahami cara menentukan halaman dalam file PDF menggunakan Aspose.PDF untuk .NET. Fungsionalitas ini tidak hanya meningkatkan navigasi bagi pengguna Anda tetapi juga menyederhanakan interaksi mereka dengan konten penting dalam dokumen Anda. Dengan menggunakan fitur-fitur tersebut, Anda menciptakan pengalaman yang lebih ramah pengguna yang dapat membedakan aplikasi PDF Anda.

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka yang memungkinkan pengembang untuk membuat, memodifikasi, dan mengelola dokumen PDF dalam aplikasi .NET.

### Bisakah saya menentukan beberapa halaman untuk dilihat?
Tidak, Anda hanya dapat mengatur dokumen agar dibuka pada satu halaman tertentu. Namun, Anda dapat membuat dokumen yang berbeda untuk halaman awal yang berbeda.

### Bagaimana jika saya ingin melihat halaman pada tingkat zoom yang berbeda?
 Anda dapat mengubah tingkat zoom dengan menyesuaikan`zoom` variabel sebelum menyimpan dokumen.

### Di mana saya dapat menemukan lebih banyak contoh penggunaan Aspose.PDF?
 Anda dapat memeriksa[dokumentasi](https://reference.aspose.com/pdf/net/) untuk lebih banyak contoh dan fungsi.

### Apakah ada uji coba gratis yang tersedia untuk Aspose.PDF untuk .NET?
 Ya! Anda dapat mengunduh uji coba Aspose.PDF secara gratis[Di Sini](https://releases.aspose.com/).