---
title: Stempel Nomor Halaman Dalam File PDF
linktitle: Stempel Nomor Halaman Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan stempel nomor halaman ke file PDF menggunakan Aspose.PDF untuk .NET melalui panduan kami yang mudah diikuti, lengkap dengan contoh kode.
type: docs
weight: 160
url: /id/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
## Perkenalan

Pernahkah Anda merasa kesulitan dengan dokumen PDF, dan berharap dokumen tersebut memiliki nomor halaman untuk memudahkan navigasi? Baik Anda seorang pelajar yang berbagi catatan, seorang profesional yang menyajikan laporan, atau siapa pun yang mengelola dokumen multi-halaman, menambahkan nomor halaman benar-benar dapat meningkatkan kejelasan file PDF Anda. Untungnya, dengan pustaka Aspose.PDF for .NET yang canggih, Anda dapat menambahkan stempel nomor halaman ke dokumen PDF Anda dengan mudah. Dalam panduan ini, kami akan memandu Anda melalui seluruh proses langkah demi langkah, memastikan bahwa Anda dibekali dengan semua pengetahuan yang Anda butuhkan. Mari kita mulai!

## Prasyarat

Sebelum kita mulai menambahkan stempel nomor halaman ke dokumen PDF Anda, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di sistem Anda. Anda akan menulis dan menjalankan kode di sini.
2. .NET Framework: Kemampuan dalam pemrograman C# dan .NET Framework sangat penting karena Aspose.PDF dirancang untuk aplikasi .NET.
3.  Pustaka Aspose.PDF: Anda dapat mengunduh pustaka Aspose.PDF dari[Rilis PDF Aspose](https://releases.aspose.com/pdf/net/). 
4. Pemahaman dasar tentang PDF: Meskipun Anda tidak perlu menjadi seorang ahli, pemahaman dasar tentang cara kerja file PDF akan membantu Anda memahami tutorial dengan lebih baik.

Setelah Anda menyiapkan prasyarat ini, Anda akan siap untuk mulai membubuhkan cap nomor halaman tersebut!

## Paket Impor

Sebelum mulai membuat kode, Anda perlu memastikan paket Aspose.PDF yang diperlukan telah diimpor ke proyek Anda. Hal ini penting untuk memanfaatkan fungsi pustaka dengan lancar. Berikut cara melakukannya:

### Buat Proyek Baru

1. Buka Visual Studio.
2.  Klik di sini`File` >`New` >`Project`.
3.  Pilih template yang sesuai untuk C# (misalnya, Aplikasi Konsol), beri nama, dan klik`Create`.

### Tambahkan Referensi Aspose.PDF

1. Klik kanan pada nama proyek di Solution Explorer.
2.  Klik di sini`Manage NuGet Packages`.
3.  Pencarian untuk`Aspose.PDF` dan instal versi terbaru.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Karena pustaka sudah siap, mari masuk ke pengkodean!

Setelah lingkungan kita siap, saatnya menambahkan stempel nomor halaman ke berkas PDF. Kita akan membagi proses ini menjadi beberapa langkah yang jelas agar lebih mudah dipahami.

## Langkah 1: Tentukan Direktori Dokumen

Untuk memulai, Anda perlu menentukan direktori tempat file PDF Anda berada. Ini adalah titik awal proyek Anda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Perbarui jalur ini
```

 Penjelasan: Ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur yang mengarah ke direktori yang berisi berkas PDF Anda. Hal ini penting karena memberi tahu kode Anda di mana menemukan berkas yang ingin Anda manipulasi.

## Langkah 2: Buka Dokumen

Berikutnya, kita akan membuka dokumen PDF yang sudah ada yang ingin kita tambahkan stempel nomor halaman.

```csharp
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

 Penjelasan: Di sini, kita menggunakan`Document` kelas yang disediakan oleh Aspose.PDF untuk membuka berkas PDF tertentu. Pastikan nama berkas sesuai dengan berkas sebenarnya yang ada di direktori Anda.

## Langkah 3: Buat Stempel Nomor Halaman

Sekarang tibalah bagian yang menyenangkan! Mari kita buat stempel nomor halaman untuk ditambahkan ke PDF kita.

```csharp
PageNumberStamp pageNumberStamp = new PageNumberStamp();
```

 Penjelasan:`PageNumberStamp`Kelas ini akan memungkinkan kita membuat prangko yang akan menampilkan nomor halaman saat ini berdasarkan jumlah total halaman dalam dokumen.

## Langkah 4: Konfigurasikan Stempel

Sekarang, Anda perlu mengonfigurasi pengaturan prangko. Di sinilah Anda mendesain tampilan dan perilaku prangko.

```csharp
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;
```

Penjelasan:
- `Background = false`: Ini berarti perangko akan muncul di latar depan.
- `Format`: Di sini, Anda mengatur format untuk menampilkan "Halaman X dari Y", di mana Anda secara dinamis mengambil total halaman dalam dokumen.
- `BottomMargin`: Menyesuaikan jarak dari bagian bawah halaman.
- `HorizontalAlignment`: Memusatkan prangko secara horizontal.
- `StartingNumber`: Mengatur nomor halaman awal, biasanya dari 1.

## Langkah 5: Mengatur Properti Teks

Berikutnya, Anda dapat menyesuaikan tampilan teks pada prangko.

```csharp
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Penjelasan: Atribut ini mengonfigurasi jenis font, ukuran font, gaya (tebal dan miring), dan warna teks dalam prangko untuk membuatnya menarik secara visual.

## Langkah 6: Tambahkan Prangko ke Halaman Tertentu

Setelah prangko Anda dikonfigurasi, saatnya menambahkannya ke halaman tertentu dalam dokumen Anda.

```csharp
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

 Penjelasan: Baris ini menambahkan stempel ke halaman pertama PDF. Anda dapat menyesuaikannya`Pages[1]` indeks untuk halaman lain bila diperlukan.

## Langkah 7: Simpan Dokumen Output

Terakhir, simpan dokumen PDF yang sudah dimodifikasi agar perubahan Anda bersifat permanen.

```csharp
dataDir = dataDir + "PageNumberStamp_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);
```

Penjelasan: Anda menentukan jalur file output dan menyimpan dokumen. Konsol akan memberi tahu Anda bahwa prangko berhasil ditambahkan dan di mana file disimpan.

## Kesimpulan

Menambahkan stempel nomor halaman ke berkas PDF Anda menggunakan Aspose.PDF untuk .NET tidak hanya mudah tetapi juga sangat dapat disesuaikan. Kami memandu Anda melalui pembuatan stempel nomor halaman langkah demi langkah, memastikan Anda memiliki panduan yang jelas selama prosesnya. Kini Anda memiliki pengetahuan untuk menyempurnakan dokumen PDF Anda, menjadikannya lebih ramah pengguna dan profesional. 

## Pertanyaan yang Sering Diajukan

### Bisakah saya menyesuaikan tampilan nomor halaman?  
Ya! Anda dapat mengubah jenis huruf, ukuran, warna, dan format nomor halaman seperti yang ditunjukkan dalam panduan.

### Apakah Aspose.PDF gratis untuk digunakan?  
 Aspose.PDF menawarkan uji coba gratis, tetapi Anda memerlukan lisensi untuk penggunaan yang ekstensif. Lihat[halaman pembelian](https://purchase.aspose.com/buy) untuk info lebih lanjut.

### Bagaimana jika saya menghadapi masalah saat implementasi?  
 Anda dapat mengunjungi[Forum Dukungan Aspose](https://forum.aspose.com/c/pdf/10) untuk bantuan.

### Bagaimana cara membuat nomor halaman secara otomatis untuk beberapa halaman?  
Kode panduan secara otomatis menghitung jumlah total halaman, sehingga memudahkan penyesuaian untuk beberapa halaman.

### Bisakah saya menggunakan Aspose.PDF dalam bahasa pemrograman lain?  
Meskipun panduan ini berfokus pada .NET, Aspose memiliki pustaka untuk Java, Python, dan banyak lagi.