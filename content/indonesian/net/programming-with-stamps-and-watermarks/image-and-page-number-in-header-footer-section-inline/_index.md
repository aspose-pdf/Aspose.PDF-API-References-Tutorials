---
title: Gambar dan Nomor Halaman di Bagian Header Footer Sebaris
linktitle: Gambar dan Nomor Halaman di Bagian Header Footer Sebaris
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan gambar dan nomor halaman sebaris di bagian header PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini.
type: docs
weight: 120
url: /id/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## Perkenalan

Aspose.PDF untuk .NET adalah alat canggih yang menyediakan kemampuan ekstensif untuk memanipulasi dan membuat file PDF. Baik Anda perlu menambahkan gambar, menyesuaikan header dan footer, atau mengelola teks, Aspose.PDF siap membantu Anda. Dalam tutorial ini, kita akan membahas cara menambahkan gambar dan nomor halaman sebaris di header atau footer dokumen PDF. Mari kita bahas dan uraikan prosesnya langkah demi langkah.

## Prasyarat

Sebelum kita masuk ke kode, mari pastikan Anda telah menyiapkan semua hal yang diperlukan untuk mengikutinya:

-  Aspose.PDF untuk .NET: Unduh versi terbaru dari[Halaman Unduh PDF Aspose](https://releases.aspose.com/pdf/net/).
- Lingkungan Pengembangan: Anda memerlukan IDE C# seperti Visual Studio.
-  Lisensi: Jika Anda belum memiliki lisensi, Anda bisa mendapatkannya[lisensi sementara di sini](https://purchase.aspose.com/temporary-license/) atau beli yang lengkap dari[Toko Aspose](https://purchase.aspose.com/buy).

Sekarang setelah prasyaratnya siap, mari kita mulai.

## Paket Impor

Sebelum Anda memulai pengkodean, pastikan untuk mengimpor namespace yang diperlukan:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Paket-paket ini memungkinkan Anda bekerja dengan berkas PDF dan manipulasi teks.

## Langkah 1: Siapkan Direktori Dokumen

Hal pertama yang perlu kita lakukan adalah menentukan jalur ke direktori tempat file PDF kita akan disimpan. Jalur ini dapat disesuaikan dengan folder proyek Anda atau lokasi mana pun di komputer Anda.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Variabel ini menyimpan lokasi penyimpanan dokumen Anda. Ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya.

## Langkah 2: Buat Instansiasi Dokumen PDF

 Pada langkah ini, kita membuat instance baru dari`Aspose.Pdf.Document` objek. Objek ini akan berfungsi sebagai tulang punggung berkas PDF Anda.

```csharp
// Membuat instance objek Dokumen dengan memanggil konstruktor kosongnya
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Di sini, kami membuat berkas PDF kosong yang nantinya dapat kami isi dengan konten.

## Langkah 3: Tambahkan Halaman ke PDF

PDF Anda memerlukan setidaknya satu halaman tempat Anda dapat menambahkan header, footer, dan konten. Mari tambahkan halaman kosong ke dokumen kita.

```csharp
// Buat halaman di objek Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

 Dengan menyebut`pdf1.Pages.Add()`halaman baru ditambahkan ke dokumen, siap untuk kustomisasi header dan footer.

## Langkah 4: Membuat dan Mengatur Header

Sekarang saatnya membuat header untuk dokumen. Di sinilah kita akan menambahkan teks, gambar, dan nomor halaman.

```csharp
// Buat Bagian Header dokumen
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
// Mengatur header untuk file PDF
page.Header = header;
```

 Kami menciptakan sebuah`HeaderFooter` objek dan menetapkannya ke`Header` properti halaman, yang memastikan bahwa apa pun yang kita tambahkan ke header akan muncul di bagian atas halaman.

## Langkah 5: Tambahkan Teks Sebaris ke Header

 Menambahkan teks semudah membuat`TextFragment` dan menentukan propertinya. Mari tambahkan beberapa teks berwarna ke header kita.

```csharp
// Membuat objek Teks
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
// Tentukan warnanya
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

 Pada langkah ini, kita membuat`TextFragment` dengan konten "Aspose.Pdf adalah komponen yang Kuat oleh" dan atur warnanya menjadi biru.`IsInLineParagraph` Properti memastikan teks tersebut sebaris, artinya teks akan muncul pada baris yang sama dengan elemen lainnya (seperti gambar dan teks tambahan).

## Langkah 6: Masukkan Gambar Sebaris di Header

Untuk membuat tajuk Anda menarik secara visual, Anda dapat menambahkan gambar sebaris dengan teks. Gambar ini dapat berupa logo perusahaan Anda atau gambar lain.

```csharp
// Buat objek gambar di bagian
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Mengatur jalur file gambar
image1.File = dataDir + "aspose-logo.jpg";
// Mengatur lebar gambar Informasi
image1.FixWidth = 50;
image1.FixHeight = 20;
// Tunjukkan InlineParagraph seg1 adalah gambar.
image1.IsInLineParagraph = true;
```

 Di sini, kita menambahkan gambar ke header dengan membuat`Image` objek, mengatur jalurnya, dan menyesuaikan lebar dan tingginya.`IsInLineParagraph` memastikan gambar selaras dengan teks.

## Langkah 7: Tambahkan Teks Sebaris Tambahan untuk Melengkapi Header

Mari tambahkan beberapa teks lagi untuk melengkapi header sebaris.

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

 Pada bagian ini, kita membuat yang lain`TextFragment` dengan konten "Pty Ltd." dan atur warnanya menjadi merah marun. Baik fragmen teks maupun gambar ditambahkan ke header.

## Langkah 8: Simpan PDF

Setelah Anda mengatur header, waktunya menyimpan PDF.

```csharp
// Simpan PDFnya
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

 Itu`Save` metode menulis berkas PDF final ke lokasi yang ditentukan.

## Kesimpulan

Selamat! Anda telah berhasil menambahkan gambar dan teks ke header dokumen PDF menggunakan Aspose.PDF untuk .NET. Tutorial ini memandu Anda melalui langkah-langkah penting, termasuk membuat dokumen, menambahkan halaman, menyisipkan header, dan menempatkan konten sebaris seperti teks dan gambar. Aspose.PDF memberi Anda fleksibilitas luar biasa untuk mengelola PDF Anda, baik itu memanipulasi header, footer, atau konten yang kompleks. 

## Pertanyaan yang Sering Diajukan

### Bisakah saya menambahkan nomor halaman pada header juga?
 Ya! Anda dapat dengan mudah menambahkan nomor halaman dengan menggunakan`TextFragment` kelas dan memformatnya sesuai kebutuhan. Cukup masukkan ke bagian header sebagai konten sebaris.

### Bagaimana cara mengatur gambar latar belakang di header?
 Anda dapat menggunakan`BackgroundImage` milik`HeaderFooter` kelas untuk menetapkan gambar latar belakang. Namun, ini bukan konten sebaris, dan akan menutupi seluruh area tajuk.

### Apakah mungkin untuk menggunakan format gambar lain selain JPEG?
Tentu saja! Aspose.PDF mendukung berbagai format gambar seperti PNG, BMP, dan GIF.

### Bisakah saya menyesuaikan font teks di header?
 Ya, Anda bisa menggunakan`TextState`objek untuk mengubah font, ukuran, dan gaya teks.

### Apakah saya memerlukan lisensi untuk menggunakan Aspose.PDF untuk .NET?
 Ya, Aspose.PDF memerlukan lisensi untuk penggunaan produksi, tetapi Anda dapat memulai dengan[uji coba gratis di sini](https://releases.aspose.com/).