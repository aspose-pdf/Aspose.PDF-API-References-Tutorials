---
title: Tambahkan Bookmark Dalam File PDF
linktitle: Tambahkan Bookmark Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan bookmark ke file PDF menggunakan Aspose.PDF for .NET dalam tutorial langkah demi langkah ini. Sempurnakan navigasi PDF Anda.
type: docs
weight: 10
url: /id/net/programming-with-bookmarks/add-bookmark/
---
## Perkenalan

Pernahkah Anda mendapati diri Anda menggulir dokumen PDF yang panjang, dan putus asa mencari satu bagian yang Anda butuhkan? Jika demikian, Anda tidak sendirian! Menelusuri dokumen yang panjang bisa sangat merepotkan. Namun, bagaimana jika saya memberi tahu Anda bahwa ada cara untuk membuat PDF Anda lebih mudah digunakan? Tambahkan bookmark! Dalam tutorial ini, kita akan menjelajahi cara menambahkan bookmark ke file PDF menggunakan Aspose.PDF for .NET. Pustaka canggih ini memungkinkan Anda untuk memanipulasi dokumen PDF dengan mudah, membuat hidup Anda jauh lebih mudah. Jadi, mari kita mulai!

## Prasyarat

Sebelum kita memulai, ada beberapa hal yang perlu Anda siapkan:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di komputer Anda. Ini adalah IDE yang tepat untuk pengembangan .NET.
2.  Aspose.PDF untuk .NET: Anda perlu mengunduh dan memasang pustaka Aspose.PDF. Anda dapat mengunduhnya dari[tautan unduhan](https://releases.aspose.com/pdf/net/).
3. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan membantu Anda mengikutinya dengan lancar.

## Paket Impor

Untuk mulai menambahkan bookmark, Anda perlu mengimpor paket yang diperlukan. Berikut cara melakukannya:

### buat proyek baru

Buka Visual Studio dan buat proyek C# baru. Pilih Aplikasi Konsol untuk mempermudah.

### Tambahkan Referensi Aspose.PDF

Setelah proyek Anda disiapkan, Anda perlu menambahkan referensi ke pustaka Aspose.PDF. Anda dapat melakukannya dengan:

- Klik kanan pada proyek Anda di Solution Explorer.
- Memilih "Kelola Paket NuGet."
- Mencari "Aspose.PDF" dan menginstalnya.

### Impor Namespace yang Diperlukan

 Di bagian atas Anda`Program.cs` file, impor namespace yang diperlukan:

```csharp
using System;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Sekarang setelah semuanya disiapkan, mari beralih ke kode sebenarnya untuk menambahkan penanda buku!

## Langkah 1: Tentukan Direktori Dokumen

Pertama, Anda perlu menentukan jalur ke direktori dokumen Anda. Di sinilah berkas PDF Anda akan berada. Berikut cara melakukannya:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat berkas PDF Anda disimpan.

## Langkah 2: Buka Dokumen PDF

Selanjutnya, Anda perlu membuka dokumen PDF yang ingin Anda tambahkan bookmark. Gunakan kode berikut:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

 Baris kode ini menginisialisasi yang baru`Document` objek dengan berkas PDF Anda.

## Langkah 3: Buat Objek Bookmark

Sekarang saatnya membuat objek penanda buku. Di sinilah Anda menentukan judul dan tampilan penanda buku Anda. Berikut cara melakukannya:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
```

Dalam contoh ini, kami membuat penanda berjudul "Test Outline" dan membuatnya tebal dan miring. Jangan ragu untuk menyesuaikan judul sesuai keinginan Anda!

## Langkah 4: Tetapkan Nomor Halaman Tujuan

Setiap penanda halaman memerlukan tujuan. Anda dapat mengatur nomor halaman yang akan ditautkan dengan kode berikut:

```csharp
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

Baris ini mengatur tindakan penanda untuk menavigasi ke halaman pertama PDF. Anda dapat mengubah nomor halaman sesuai kebutuhan.

## Langkah 5: Tambahkan Bookmark ke Dokumen

Sekarang setelah Anda membuat penanda buku, saatnya menambahkannya ke koleksi kerangka dokumen:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

Baris ini menambahkan penanda halaman yang baru Anda buat ke dokumen PDF.

## Langkah 6: Simpan Output

Terakhir, Anda perlu menyimpan dokumen PDF yang telah dimodifikasi. Berikut cara melakukannya:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

Kode ini menyimpan PDF dengan penanda buku tambahan sebagai "AddBookmark_out.pdf" di direktori yang Anda tentukan.

## Kesimpulan

Nah, itu dia! Anda telah berhasil menambahkan penanda ke berkas PDF menggunakan Aspose.PDF for .NET. Fitur sederhana namun hebat ini dapat meningkatkan kegunaan dokumen Anda secara signifikan, sehingga memudahkan pembaca untuk menelusurinya. Jadi, lain kali Anda bekerja dengan PDF, ingatlah untuk menambahkan penanda tersebut!

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka yang memungkinkan pengembang untuk membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram.

### Bisakah saya menambahkan beberapa penanda halaman ke PDF?
 Ya, Anda dapat membuat beberapa`OutlineItemCollection`objek dan menambahkannya ke koleksi kerangka dokumen.

### Apakah Aspose.PDF gratis untuk digunakan?
 Aspose.PDF menawarkan uji coba gratis, tetapi untuk fungsionalitas penuh, Anda perlu membeli lisensi. Lihat[tautan pembelian](https://purchase.aspose.com/buy).

### Di mana saya dapat menemukan dokumentasi lebih lanjut?
 Anda dapat menemukan dokumentasi lengkap di Aspose.PDF untuk .NET[Di Sini](https://reference.aspose.com/pdf/net/).

### Bagaimana cara mendapatkan dukungan untuk Aspose.PDF?
 Untuk dukungan, Anda dapat mengunjungi[Forum dukungan Aspose](https://forum.aspose.com/c/pdf/10).