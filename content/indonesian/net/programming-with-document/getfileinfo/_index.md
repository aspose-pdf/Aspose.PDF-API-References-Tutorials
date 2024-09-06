---
title: Dapatkan Info File dalam File PDF
linktitle: Dapatkan Info File dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menggunakan fitur GetFileInfo dalam file PDF dari Aspose.PDF untuk .NET untuk mengambil informasi metadata tentang dokumen PDF.
type: docs
weight: 180
url: /id/net/programming-with-document/getfileinfo/
---
 Aspose.PDF untuk .NET adalah pustaka manipulasi PDF populer yang memungkinkan pengembang untuk membuat, mengedit, dan mengonversi file PDF dalam aplikasi .NET mereka. Salah satu fitur yang ditawarkan oleh pustaka ini adalah kemampuan untuk mengambil informasi tentang metadata dokumen PDF. Tutorial ini akan memandu Anda melalui langkah-langkah penggunaan`GetFileInfo` fitur Aspose.PDF untuk .NET untuk mengambil informasi tentang metadata dokumen PDF.

## Langkah 1: Instal Aspose.PDF untuk .NET

 Untuk menggunakan Aspose.PDF for .NET di aplikasi .NET Anda, Anda harus menginstal pustaka terlebih dahulu. Anda dapat mengunduh versi terbaru pustaka dari[Halaman unduhan Aspose.PDF untuk .NET](https://releases.aspose.com/pdf/net).

Setelah Anda mengunduh pustaka, ekstrak isi berkas ZIP ke folder di komputer Anda. Anda kemudian perlu menambahkan referensi ke Aspose.PDF untuk .NET DLL di proyek .NET Anda.

## Langkah 2: Muat Dokumen PDF

 Setelah Anda menginstal Aspose.PDF untuk .NET dan menambahkan referensi ke DLL di proyek .NET Anda, Anda dapat mulai menggunakan`GetFileInfo` fitur untuk mengambil informasi tentang metadata dokumen PDF.

Langkah pertama dalam menggunakan fitur ini adalah memuat dokumen PDF yang ingin Anda ambil informasinya. Untuk melakukannya, Anda dapat menggunakan kode berikut:

```csharp
// Jalur menuju dokumen PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 Pada kode di atas, ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen PDF Anda berada. Kode ini akan memuat dokumen PDF ke dalam`Document` objek, yang kemudian dapat Anda gunakan untuk mengambil informasi tentang metadata dokumen.

## Langkah 3: Ambil Metadata Dokumen

Untuk mengambil informasi tentang metadata dokumen PDF, Anda dapat menggunakan kode berikut:

```csharp
// Dapatkan informasi dokumen
DocumentInfo docInfo = pdfDocument.Info;

// Tampilkan informasi dokumen
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

Pada kode di atas, setiap baris mengambil properti metadata yang berbeda dari dokumen PDF dan menampilkannya di konsol. Anda dapat menyesuaikan kode ini untuk mengambil hanya properti yang Anda minati.

### Contoh kode sumber untuk mendapatkan info file PDF menggunakan Aspose.PDF untuk .NET

 Berikut adalah kode sumber lengkap untuk mengambil metadata dokumen PDF menggunakan`GetFileInfo` fitur Aspose.PDF untuk .NET:

```csharp
// Jalur menuju dokumen PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Dapatkan informasi dokumen
DocumentInfo docInfo = pdfDocument.Info;

// Tampilkan informasi dokumen
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## Kesimpulan

Dalam tutorial ini, kami telah membahas cara menggunakan Aspose.PDF untuk .NET guna mengambil informasi tentang metadata dokumen PDF. Dengan memuat dokumen PDF dan mengakses properti metadatanya, Anda dapat mengumpulkan informasi tentang karakteristik dan properti dokumen. Aspose.PDF untuk .NET menyediakan API yang sederhana dan mudah digunakan untuk bekerja dengan dokumen PDF, termasuk mengambil informasi metadata, menjadikannya alat yang berharga untuk manipulasi PDF dalam aplikasi .NET.

### Pertanyaan yang Sering Diajukan

#### T: Apa itu metadata dalam dokumen PDF?

J: Metadata dalam dokumen PDF merujuk pada informasi yang menjelaskan properti dan karakteristik dokumen. Informasi ini biasanya mencakup judul dokumen, penulis, subjek, kata kunci, tanggal pembuatan, tanggal modifikasi, dan lain-lain.

#### T: Bagaimana cara menginstal Aspose.PDF untuk .NET di proyek .NET saya?

 A: Untuk menginstal Aspose.PDF untuk .NET, Anda perlu mengunduh pustaka dari[Halaman unduhan Aspose.PDF untuk .NET](https://releases.aspose.com/pdf/net)Setelah mengunduh, ekstrak isi file ZIP dan tambahkan referensi ke Aspose.PDF for .NET DLL di proyek .NET Anda.

#### T: Dapatkah saya menyesuaikan kode untuk mengambil properti metadata tertentu saja?

A: Ya, Anda dapat menyesuaikan kode untuk mengambil properti metadata tertentu dengan memberi komentar pada baris yang tidak Anda perlukan. Setiap baris dalam kode sesuai dengan properti metadata tertentu, sehingga Anda dapat menyertakan atau mengecualikan properti berdasarkan kebutuhan Anda.

#### T: Jenis properti metadata apa yang dapat saya ambil menggunakan Aspose.PDF untuk .NET?

A: Dengan menggunakan Aspose.PDF untuk .NET, Anda dapat mengambil berbagai properti metadata dari dokumen PDF, termasuk penulis, judul, subjek, kata kunci, tanggal pembuatan, dan tanggal modifikasi.