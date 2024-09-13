---
title: Dapatkan Jendela Dokumen
linktitle: Dapatkan Jendela Dokumen
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menggunakan fitur GetDocumentWindow dari Aspose.PDF untuk .NET untuk mengambil informasi tentang properti jendela dokumen PDF.
type: docs
weight: 170
url: /id/net/programming-with-document/getdocumentwindow/
---
# Perkenalan

Apakah Anda bekerja dengan PDF dan ingin kontrol lebih terhadap tampilannya saat dibuka? Baik itu menyembunyikan bilah menu atau mengubah ukuran jendela agar sesuai dengan halaman pertama, Aspose.PDF for .NET memberi Anda semua alat yang Anda butuhkan untuk menyesuaikan perilaku PDF saat dibuka di penampil. Dalam tutorial ini, kami akan menguraikan cara mengambil dan memanipulasi pengaturan jendela dokumen di Aspose.PDF for .NET.


# Prasyarat

Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:

- Aspose.PDF untuk .NET terinstal di lingkungan pengembangan Anda.
  - [Unduh Aspose.PDF untuk .NET](https://releases.aspose.com/pdf/net/)
-  Lisensi yang valid untuk Aspose.PDF, atau Anda bisa mendapatkannya[uji coba gratis](https://releases.aspose.com/) atau[lisensi sementara](https://purchase.aspose.com/temporary-license/).
- Pemahaman dasar tentang .NET dan C#.
- Visual Studio atau IDE lain yang sesuai.

# Paket Impor

Sebelum Anda mulai menulis kode apa pun, Anda perlu mengimpor paket yang diperlukan. Buka proyek Anda, dan di bagian atas berkas C#, tambahkan namespace berikut:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Ini akan memberi Anda akses ke semua kelas dan metode yang diperlukan untuk memanipulasi dokumen PDF menggunakan Aspose.PDF untuk .NET.

 Sekarang mari kita uraikan proses pengambilan pengaturan jendela dokumen yang berbeda. Untuk contoh ini, kita akan menggunakan contoh file PDF bernama`GetDocumentWindow.pdf`.

## Langkah 1: Tetapkan Jalur Direktori Dokumen

Pertama-tama, kita perlu menentukan jalur ke berkas PDF kita. Sangat penting untuk memiliki jalur berkas yang benar guna menghindari kesalahan selama eksekusi.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Di sini, ganti`"YOUR DOCUMENT DIRECTORY"` dengan direktori sebenarnya tempat berkas PDF Anda berada. Ini adalah direktori kerja tempat Anda akan memuat dokumen PDF.

## Langkah 2: Buka Dokumen PDF

Setelah jalur berkas ditetapkan, langkah selanjutnya adalah membuka dokumen PDF menggunakan Aspose.PDF. Ini akan memuat dokumen ke dalam memori, sehingga Anda dapat mengambil propertinya.

```csharp
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

Dengan baris kode sederhana ini, Anda telah berhasil memuat file PDF Anda ke dalam`pdfDocument` objek, yang sekarang akan memungkinkan Anda mengakses semua propertinya.

## Langkah 3: Ambil Status Pemusatan Jendela

 Selanjutnya, mari kita periksa apakah jendela dokumen harus dipusatkan saat dibuka. Nilai default untuk ini adalah`false`.

```csharp
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
```

 Jika outputnya adalah`true`, jendela dokumen akan terbuka di bagian tengah layar. Jika tidak, jendela akan terbuka pada posisi default-nya.

## Langkah 4: Periksa Arah Teks

Aspek penting lain dari tampilan PDF adalah arah teks, yang menentukan apakah teks dibaca dari kiri ke kanan (L2R) atau kanan ke kiri (R2L). Anda dapat memperoleh informasi ini menggunakan kode berikut:

```csharp
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
```

 Outputnya akan berupa`L2R` untuk teks kiri ke kanan dan`R2L` untuk teks dari kanan ke kiri. Pengaturan ini khususnya berguna untuk dokumen dalam bahasa seperti Arab atau Ibrani.

## Langkah 5: Menampilkan Judul Dokumen di Jendela

Properti berikut memungkinkan Anda untuk mengontrol apakah judul dokumen atau nama file akan ditampilkan pada bilah judul jendela. Secara default, ini diatur ke`false`, yang berarti nama berkas akan ditampilkan.

```csharp
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
```

Jika Anda ingin judul dokumen yang ditampilkan dan bukan nama file, pengaturan ini harus diaktifkan.

## Langkah 6: Ubah Ukuran Jendela agar Sesuai dengan Halaman Pertama

Terkadang, Anda mungkin ingin jendela dokumen secara otomatis mengubah ukurannya sendiri agar sesuai dengan halaman pertama PDF saat dibuka. Berikut cara memeriksa apakah fitur tersebut diaktifkan:

```csharp
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
```

 Secara default, ini diatur ke`false`, artinya ukuran jendela akan tetap apa adanya terlepas dari ukuran halaman pertama.

## Langkah 7: Sembunyikan Bilah Menu

Untuk pengalaman membaca yang lebih terfokus, Anda mungkin ingin menyembunyikan bilah menu aplikasi penampil. Anda dapat mengambil pengaturan ini menggunakan baris berikut:

```csharp
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
```

 Ini akan kembali`true` jika bilah menu disembunyikan, dan`false` jika tidak.

## Langkah 8: Sembunyikan Bilah Alat

Demikian pula, Anda mungkin juga ingin menyembunyikan bilah alat di penampil PDF agar antarmuka pengguna lebih bersih. Pengaturan ini dapat diambil sebagai berikut:

```csharp
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
```

Jika pengaturan ini diaktifkan, bilah alat akan disembunyikan saat PDF dibuka.

## Langkah 9: Sembunyikan Bilah Gulir dan Elemen UI

Jika Anda hanya ingin menampilkan konten halaman tanpa elemen UI tambahan seperti bilah gulir, pengaturan ini mengontrol perilaku tersebut:

```csharp
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
```

 Ketika diatur ke`true`, penampil PDF akan menyembunyikan bilah gulir dan elemen antarmuka pengguna lainnya, hanya menyisakan konten dokumen.

## Langkah 10: Atur Mode Halaman Non-Layar Penuh

 Anda dapat mengontrol bagaimana dokumen muncul saat keluar dari mode layar penuh menggunakan`NonFullScreenPageMode` properti. Pengaturan ini berguna untuk menentukan bagaimana pengguna harus berinteraksi dengan dokumen dalam mode layar nonpenuh.

```csharp
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
```

Output dapat diatur ke berbagai mode seperti gambar mini, garis besar, atau panel lampiran.

## Langkah 11: Tentukan Tata Letak Halaman

Pengaturan ini memungkinkan Anda untuk mengontrol tata letak halaman dokumen. Misalnya, Anda dapat memilih tampilan satu halaman atau tampilan kolom berkelanjutan:

```csharp
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
```

Hal ini memberi pengguna fleksibilitas dalam cara mereka membaca atau melihat konten dokumen.

## Langkah 12: Tentukan Mode Halaman

 Akhirnya,`PageMode` properti menentukan bagaimana dokumen akan ditampilkan saat dibuka. Pilihannya termasuk menampilkan gambar mini, memasuki mode layar penuh, atau menampilkan panel lampiran.

```csharp
Console.WriteLine("PageMode : {0}", pdfDocument.PageMode);
```

Bergantung pada kebutuhan Anda, Anda dapat mengaturnya ke mode apa pun yang sesuai dengan tujuan PDF Anda.

## Kesimpulan

Seperti yang dapat Anda lihat, Aspose.PDF untuk .NET menyediakan berbagai alat yang komprehensif untuk memanipulasi tampilan dokumen PDF Anda di berbagai penampil PDF. Apakah Anda ingin menyembunyikan bilah alat, memusatkan jendela, atau mengontrol arah teks, Aspose.PDF menawarkan fleksibilitas untuk meningkatkan pengalaman menonton pengguna.

# Tanya Jawab Umum

### Bisakah saya menyesuaikan tingkat zoom awal PDF?
Ya, Aspose.PDF memungkinkan Anda mengatur tingkat zoom saat dokumen dibuka.

### Bagaimana cara mengunci ukuran jendela PDF?
 Anda dapat mengatur`FitWindow` properti untuk mencegah jendela berubah ukuran.

### Apakah Aspose.PDF mendukung berbagai mode baca?
Ya, ini mendukung berbagai mode seperti layar penuh, gambar mini, dan lampiran.

### Apakah mungkin untuk menyembunyikan bilah gulir di penampil PDF?
 Tentu saja, Anda dapat menyembunyikan bilah gulir dengan mengatur`HideWindowUI` properti untuk`true`.

### Bisakah saya memusatkan jendela dokumen saat dibuka?
 Ya, Anda dapat mengontrolnya dengan mengatur`CenterWindow` milik.