---
title: Tambahkan Bookmark Dalam File PDF
linktitle: Tambahkan Bookmark Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Tambahkan bookmark dengan mudah dalam file PDF untuk meningkatkan navigasi dengan Aspose.PDF untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-bookmarks/add-bookmark/
---
Menambahkan bookmark dalam file PDF memungkinkan navigasi yang mudah dan cepat. Dengan Aspose.PDF untuk .NET, Anda dapat dengan mudah menambahkan bookmark di file PDF dengan mengikuti kode sumber berikut:

## Langkah 1: Impor perpustakaan yang diperlukan

Sebelum memulai, Anda perlu mengimpor perpustakaan yang diperlukan untuk proyek C# Anda. Berikut adalah arahan impor yang diperlukan:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Langkah 2: Tetapkan jalur ke folder dokumen

 Pada langkah ini, Anda perlu menentukan jalur ke folder yang berisi file PDF yang ingin Anda tambahkan bookmark. Mengganti`"YOUR DOCUMENT DIRECTORY"`dalam kode berikut dengan jalur sebenarnya ke folder dokumen Anda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 3: Buka dokumen PDF

Sekarang kita akan membuka dokumen PDF yang ingin kita tambahkan bookmark menggunakan kode berikut:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## Langkah 4: Buat objek bookmark

 Pada langkah ini, kita akan membuat objek bookmark menggunakan`OutlineItemCollection` kelas dan atur propertinya seperti judul, atribut miring, atribut tebal, dan tindakan yang akan dilakukan saat diklik. Ini kode yang sesuai:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## Langkah 5: Tambahkan bookmark ke dokumen

 Terakhir, kami menambahkan bookmark yang dibuat ke koleksi bookmark dokumen menggunakan`Add` metode`Outlines` Properti. Ini kode yang sesuai:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Contoh kode sumber untuk Tambahkan Bookmark menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Buat objek penanda
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// Tetapkan nomor halaman tujuan
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// Tambahkan penanda di kumpulan kerangka dokumen.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// Simpan keluaran
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## Kesimpulan

Selamat! Sekarang Anda memiliki panduan langkah demi langkah untuk menambahkan bookmark menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan kode ini untuk meningkatkan navigasi dalam dokumen PDF Anda dengan menambahkan bookmark khusus.

Pastikan untuk memeriksa dokumentasi resmi Aspose.PDF untuk informasi lebih lanjut tentang fitur manipulasi bookmark tingkat lanjut.


### FAQ untuk menambahkan bookmark dalam file PDF

#### T: Apa yang dimaksud dengan bookmark dalam file PDF?

J: Bookmark, juga dikenal sebagai kerangka, adalah elemen interaktif yang menyediakan navigasi dan struktur dalam dokumen PDF. Mereka memungkinkan pengguna untuk dengan cepat melompat ke bagian atau halaman tertentu.

#### T: Mengapa saya perlu menambahkan bookmark ke file PDF?

J: Menambahkan bookmark ke file PDF meningkatkan pengalaman pengguna dan memudahkan pembaca menavigasi konten dokumen. Bookmark dapat berfungsi sebagai daftar isi atau menyediakan akses cepat ke bagian-bagian penting.

#### T: Bagaimana cara mengimpor perpustakaan yang diperlukan untuk proyek C# saya?

J: Untuk mengimpor perpustakaan yang diperlukan untuk proyek C# Anda, sertakan arahan impor berikut:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Arahan ini memungkinkan Anda mengakses kelas dan metode yang diperlukan untuk bekerja dengan dokumen dan bookmark PDF.

#### T: Bagaimana cara menentukan jalur ke folder dokumen?

 J: Ganti`"YOUR DOCUMENT DIRECTORY"` dalam kode sumber yang disediakan dengan jalur sebenarnya ke folder yang berisi file PDF yang ingin Anda tambahkan bookmark.

#### T: Bagaimana cara membuka dokumen PDF untuk menambahkan bookmark?

A: Untuk membuka dokumen PDF untuk menambahkan bookmark, gunakan kode berikut:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

 Mengganti`"AddBookmark.pdf"` dengan nama file sebenarnya.

#### T: Bagaimana cara membuat objek bookmark?

 A: Untuk membuat objek bookmark, gunakan`OutlineItemCollection` kelas. Sesuaikan propertinya seperti judul, gaya miring, gaya tebal, dan tindakan untuk dilakukan saat diklik.

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

####  T: Apa tujuan dari`Action` property in a bookmark?

 J: Itu`Action` properti menentukan tindakan yang akan dilakukan ketika bookmark diklik. Dalam contoh ini, kami menggunakan`GoToAction`kelas untuk menavigasi ke halaman tertentu (halaman 2 dalam kasus ini).

#### T: Bagaimana cara menambahkan bookmark ke dokumen?

 J: Gunakan`Add` metode`Outlines` properti untuk menambahkan bookmark yang dibuat ke koleksi bookmark dokumen.

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### T: Bisakah saya menambahkan banyak bookmark menggunakan metode ini?

J: Ya, Anda dapat mengulangi langkah 4 hingga 8 untuk menambahkan beberapa penanda ke dokumen. Sesuaikan properti dan tindakan setiap bookmark sesuai kebutuhan.

#### T: Bagaimana cara menyimpan file PDF yang diperbarui?

 A: Simpan file PDF yang diperbarui menggunakan`Save` metode`pdfDocument` obyek:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### T: Bagaimana cara mengonfirmasi bahwa bookmark telah ditambahkan?

A: Buka file PDF yang dihasilkan untuk memverifikasi bahwa penanda tertentu telah ditambahkan ke dokumen.

#### T: Apakah ada batasan jumlah bookmark yang dapat saya tambahkan?

J: Secara umum tidak ada batasan ketat mengenai jumlah bookmark yang dapat Anda tambahkan, namun pertimbangkan ukuran dan kompleksitas dokumen untuk performa optimal.

#### T: Dapatkah saya menyesuaikan tampilan bookmark?

A: Ya, Anda dapat menyesuaikan lebih lanjut tampilan bookmark, warna, gaya, dan atribut lainnya menggunakan fitur Aspose.PDF.