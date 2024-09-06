---
title: Tambahkan Anotasi lnk
linktitle: Tambahkan Anotasi lnk
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan anotasi tinta ke file PDF dengan Aspose.PDF untuk .NET dalam panduan langkah demi langkah yang menarik ini.
type: docs
weight: 20
url: /id/net/annotations/addlnkannotation/
---
## Perkenalan

Selamat datang di dunia manipulasi PDF dengan Aspose.PDF untuk .NET! Jika Anda ingin menyempurnakan dokumen PDF Anda, baik untuk penggunaan profesional, proyek pribadi, atau apa pun di antaranya, Anda berada di tempat yang tepat. Hari ini, kita akan membahas fitur Aspose.PDF yang spesifik namun praktis: menambahkan anotasi tinta ke berkas PDF Anda. Fungsionalitas ini dapat sangat berguna saat Anda ingin menambahkan catatan atau tanda tangan seperti tulisan tangan ke dokumen Anda, membuatnya lebih interaktif dan menarik.

## Prasyarat

Sebelum kita menyelami keajaiban pengkodean, mari pastikan Anda memiliki semua yang dibutuhkan untuk memulai:

1. .NET Framework: Pastikan Anda telah menginstal .NET di komputer Anda. Pustaka ini berfungsi dengan lancar dengan berbagai versi .NET, termasuk .NET Core.
2.  Pustaka Aspose.PDF: Anda harus mengunduh dan merujuk pustaka Aspose.PDF untuk .NET ke dalam proyek Anda. Jika Anda belum melakukannya, Anda dapat mengunduh versi terbaru dari[tautan unduhan](https://releases.aspose.com/pdf/net/).
3. Editor Kode: Anda dapat menggunakan editor kode pilihan Anda, tetapi Visual Studio sangat direkomendasikan karena kemudahan penggunaannya dengan aplikasi .NET.
4. Pemahaman Dasar C#: Pengetahuan praktis tentang C# akan membantu Anda menavigasi contoh pengkodean dengan lancar.
5. Menyiapkan Lingkungan Pengembangan Anda: Pastikan IDE Anda diatur untuk menangani proyek .NET dan Anda telah mereferensikan pustaka Aspose.PDF dengan benar dalam proyek Anda. 

Jika prasyarat ini terpenuhi, Anda siap untuk mulai menambahkan anotasi tinta ke PDF Anda!

## Paket Impor

Sebelum memulai pengodean, mari impor paket-paket yang diperlukan. Di bagian atas berkas C# Anda, tambahkan pernyataan berikut:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using System;
using System.Collections;
using System.Collections.Generic;
```

Ini akan memberi Anda akses ke semua kelas dan metode yang Anda perlukan untuk bekerja dengan anotasi PDF.

Setelah kita menyiapkan semuanya, saatnya untuk mulai bekerja! Kami akan menguraikan setiap langkah untuk memastikan Anda memahami dengan tepat cara membuat dan menambahkan anotasi tinta ke dokumen PDF Anda.

## Langkah 1: Mengatur Dokumen dan Direktori

Hal pertama yang ingin Anda lakukan adalah menyiapkan dokumen Anda dan jalur tempat Anda ingin menyimpan berkas keluaran Anda. 

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
```
 Kami mendefinisikan sebuah variabel`dataDir` , yang menunjuk ke direktori tempat PDF yang dihasilkan akan disimpan.`Document` Objek tersebut kemudian diwujudkan, menciptakan dokumen PDF baru untuk diedit.

## Langkah 2: Tambahkan Halaman ke Dokumen Anda

Berikutnya, Anda ingin menambahkan halaman ke dokumen yang baru Anda buat.

```csharp
Page pdfPage = doc.Pages.Add();
```
Di sini, kita akan menambahkan halaman baru ke dokumen kita. Setiap PDF memerlukan setidaknya satu halaman, jadi langkah ini penting.

## Langkah 3: Tentukan Persegi Panjang Gambar

Sebelum Anda dapat menggambar apa pun, Anda perlu menentukan di mana pada halaman Anda akan menempatkan anotasi tinta.

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
```
 Di sini, kita membuat`Rectangle` objek yang menentukan area pada halaman tempat kita akan menambahkan anotasi tinta. Kita mengatur dimensinya agar sesuai dengan seluruh halaman, mulai dari (0,0).

## Langkah 4: Siapkan Titik Tinta

Sekarang tibalah pada bagian yang menyenangkan—mendefinisikan titik-titik yang membentuk anotasi tinta Anda. 

```csharp
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
```
Blok kode ini membuat daftar larik Titik, di mana setiap larik mewakili sekumpulan titik untuk goresan tinta Anda. Di sini, kami mendefinisikan tiga titik yang membentuk segitiga; Anda dapat menyesuaikan koordinat agar sesuai dengan desain Anda.

## Langkah 5: Buat Anotasi Tinta

Setelah titik-titik Anda ditentukan, waktunya membuat anotasi tinta yang sebenarnya.

```csharp
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList)
{
    Title = "XXX",
    Color = Aspose.Pdf.Color.LightBlue,
    CapStyle = CapStyle.Rounded
};
```
 Kami mewujudkan`InkAnnotation`objek, meneruskan halaman, persegi panjang, dan titik tinta. Selain itu, kami menetapkan beberapa properti seperti`Title`, `Color` , Dan`CapStyle`Sesuaikan dengan kebutuhan Anda!

## Langkah 6: Mengatur Batas dan Opacity

Ingin anotasi Anda menonjol? Mari beri sedikit gaya.

```csharp
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
```
Di sini, kami menambahkan batas pada anotasi dengan lebar tertentu dan mengatur opasitasnya, menjadikannya semi-transparan.

## Langkah 7: Tambahkan Anotasi ke Halaman

Sekarang anotasi Anda sudah siap, saatnya menambahkannya ke halaman PDF.

```csharp
pdfPage.Annotations.Add(ia);
```
Baris ini menambahkan anotasi tinta yang kita buat sebelumnya ke koleksi anotasi halaman. 

## Langkah 8: Simpan Dokumen

Terakhir, mari simpan dokumen kita yang sudah dimodifikasi.

```csharp
dataDir = dataDir + "AddInkAnnotation_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation added successfully.\nFile saved at " + dataDir);
```
 Kami memodifikasi`dataDir` untuk menyertakan nama berkas keluaran dan menyimpan dokumen. Pesan konfirmasi dicetak ke konsol untuk memberi tahu Anda bahwa semuanya berjalan lancar.

## Kesimpulan

Nah, itu dia! Anda telah berhasil menambahkan anotasi tinta ke dokumen PDF Anda menggunakan Aspose.PDF for .NET. Fitur sederhana namun efektif ini dapat menyempurnakan dokumen Anda dan membuatnya interaktif. Baik Anda menambahkan tanda tangan, catatan, atau coretan, anotasi tinta menyediakan cara unik untuk memperkaya konten.

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF?
Aspose.PDF adalah pustaka untuk membuat, memanipulasi, dan mengonversi dokumen PDF dalam aplikasi .NET.

### Dapatkah saya menggunakan Aspose.PDF secara gratis?
 Ya! Aspose menawarkan versi uji coba gratis untuk mengevaluasi produk mereka. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/).

### Apakah mungkin untuk menambahkan beberapa anotasi tinta?
 Tentu saja! Anda dapat membuat beberapa`InkAnnotation` objek dan menambahkannya ke halaman dokumen Anda.

### Di mana saya dapat menemukan lebih banyak contoh?
 Anda dapat memeriksa[dokumentasi](https://reference.aspose.com/pdf/net/) untuk tutorial dan contoh terperinci.

### Apa yang harus saya lakukan jika saya butuh dukungan?
 Jika Anda mengalami masalah, Anda dapat mencari bantuan di[forum dukungan](https://forum.aspose.com/c/pdf/10).