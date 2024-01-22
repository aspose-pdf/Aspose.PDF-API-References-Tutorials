---
title: Tambahkan Bookmark Anak Dalam File PDF
linktitle: Tambahkan Bookmark Anak Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Tambahkan bookmark anak dengan mudah dalam file PDF untuk penelusuran yang lebih terorganisir dengan Aspose.PDF untuk .NET.
type: docs
weight: 20
url: /id/net/programming-with-bookmarks/add-child-bookmark/
---
Menambahkan bookmark anak dalam file PDF memungkinkan organisasi dan navigasi yang lebih terstruktur. Dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah menambahkan sub-bookmark dengan mengikuti kode sumber berikut:

## Langkah 1: Impor perpustakaan yang diperlukan

Sebelum memulai, Anda perlu mengimpor perpustakaan yang diperlukan untuk proyek C# Anda. Berikut adalah arahan impor yang diperlukan:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Langkah 2: Tetapkan jalur ke folder dokumen

 Pada langkah ini, Anda perlu menentukan jalur ke folder yang berisi file PDF yang ingin Anda tambahkan sub-bookmark. Mengganti`"YOUR DOCUMENT DIRECTORY"`dalam kode berikut dengan jalur sebenarnya ke folder dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 3: Buka dokumen PDF

Sekarang kita akan membuka dokumen PDF yang ingin kita tambahkan sub-bookmark menggunakan kode berikut:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Langkah 4: Buat objek bookmark induk

 Pada langkah ini, kita akan membuat objek bookmark induk menggunakan`OutlineItemCollection` kelas dan atur propertinya seperti judul, atribut miring, dan atribut tebal. Ini kode yang sesuai:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Langkah 5: Buat Objek Bookmark Anak

Pada langkah ini, kita akan membuat objek sub-bookmark lagi menggunakan`OutlineItemCollection` kelas dan mengatur propertinya. Ini kode yang sesuai:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## Langkah 6: Tambahkan sub-bookmark ke bookmark induk

 Terakhir, kami menambahkan subbookmark yang dibuat ke koleksi subbookmark induk menggunakan`Add` metode objek induk. Ini kode yang sesuai:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Langkah 7: Tambahkan penanda induk ke koleksi penanda dokumen

 Terakhir, kita menambahkan penanda induk ke koleksi penanda dokumen menggunakan`Add` metode`Outlines` Properti. Ini kode yang sesuai:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Contoh kode sumber untuk Tambahkan Bookmark Anak menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Buat objek bookmark induk
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Buat objek bookmark anak
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Tambahkan bookmark anak di koleksi bookmark induk
pdfOutline.Add(pdfChildOutline);
// Tambahkan penanda induk di kumpulan kerangka dokumen.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Simpan keluaran
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Kesimpulan

Selamat! Sekarang Anda memiliki panduan langkah demi langkah untuk menambahkan sub-bookmark dengan Aspose.PDF untuk .NET. Anda dapat menggunakan kode ini untuk mengatur dan menyusun bookmark di dokumen PDF Anda.

Pastikan untuk memeriksa dokumentasi resmi Aspose.PDF untuk informasi lebih lanjut tentang fitur manipulasi bookmark tingkat lanjut.

### FAQ untuk menambahkan bookmark anak dalam file PDF

#### T: Apa yang dimaksud dengan penanda anak dalam file PDF?

J: Bookmark anak, juga dikenal sebagai sub-bookmark, adalah elemen navigasi dalam dokumen PDF yang terstruktur secara hierarki di bawah bookmark induk. Mereka menyediakan cara untuk membuat daftar isi dokumen yang lebih terorganisir dan rinci.

#### T: Bagaimana cara mengimpor perpustakaan yang diperlukan untuk proyek C# saya?

J: Untuk mengimpor perpustakaan yang diperlukan untuk proyek C# Anda, Anda dapat menggunakan arahan impor berikut:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Perpustakaan ini menyediakan kelas dan fungsi yang diperlukan untuk bekerja dengan dokumen PDF dan fitur interaktif.

#### T: Bagaimana cara menentukan jalur ke folder dokumen?

 A: Pada kode sumber yang disediakan, Anda perlu menggantinya`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke folder yang berisi file PDF yang ingin Anda kerjakan. Ini memastikan bahwa kode menemukan file PDF target dengan benar.

#### T: Dapatkah saya membuat beberapa tingkat penanda anak?

J: Ya, Anda dapat membuat beberapa tingkat penanda anak dengan memperluas proses yang dijelaskan dalam tutorial. Dengan membuat bookmark induk dengan sub-bookmark dan menyusunnya lebih lanjut, Anda dapat membuat struktur hierarki bookmark untuk dokumen PDF yang kompleks.

####  T: Apa tujuan dari`OutlineItemCollection` class?

 J: Itu`OutlineItemCollection` kelas di Aspose.PDF untuk .NET digunakan untuk membuat dan mengelola kerangka, yang pada dasarnya merupakan penanda dalam dokumen PDF. Kelas ini memungkinkan Anda mengatur properti seperti judul, gaya font, dan tindakan untuk bookmark.

#### T: Bagaimana cara menambahkan sub-bookmark ke bookmark induk?

 J: Untuk menambahkan sub-bookmark ke bookmark induk, Anda membuat yang baru`OutlineItemCollection` objek untuk sub-bookmark dan mengatur propertinya. Kemudian, Anda menggunakan`Add` metode bookmark induk`OutlineItemCollection` untuk menambahkan sub-bookmark ke koleksi induk.

#### T: Dapatkah saya menyesuaikan tampilan bookmark anak?

J: Ya, mirip dengan bookmark induk, Anda dapat menyesuaikan tampilan bookmark anak dengan mengatur properti seperti judul, gaya font, dan atribut lainnya. Hal ini memungkinkan Anda membuat penanda visual yang khas dan informatif.

#### T: Apakah Aspose.PDF untuk .NET kompatibel dengan bahasa pemrograman lain?

J: Aspose.PDF untuk .NET dirancang khusus untuk lingkungan C# dan .NET. Namun Aspose menawarkan perpustakaan serupa untuk bahasa pemrograman lain seperti Java dan Android, masing-masing disesuaikan dengan platformnya masing-masing.

#### T: Bagaimana bookmark anak meningkatkan navigasi PDF?

J: Bookmark anak meningkatkan navigasi PDF dengan menyediakan daftar isi yang lebih terstruktur dan terorganisir. Pengguna dapat dengan cepat mengakses bagian tertentu dari dokumen melalui struktur penanda hierarki.