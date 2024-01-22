---
title: Tautkan Aliran Duplikat
linktitle: Tautkan Aliran Duplikat
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menggunakan fitur Aspose.PDF untuk .NET Link Duplikat Aliran untuk mengoptimalkan dokumen PDF Anda dengan panduan langkah demi langkah ini.
type: docs
weight: 230
url: /id/net/programming-with-document/linkduplicatestreams/
---
Aspose.PDF untuk .NET adalah perpustakaan komprehensif dan kuat yang menyediakan berbagai fitur untuk bekerja dengan file PDF. Salah satu fitur utamanya adalah kemampuan untuk mengoptimalkan file PDF. Pada artikel ini, kami akan menjelaskan cara menggunakan fitur Link Duplikat Aliran Aspose.PDF untuk .NET untuk mengoptimalkan file PDF. Kami akan memberikan petunjuk langkah demi langkah dan menyertakan contoh kode sumber lengkap untuk memudahkan pengembang untuk mengikutinya.

## Langkah 1: Membuka Dokumen PDF

Untuk membuka dokumen PDF menggunakan Aspose.PDF untuk .NET, ikuti langkah-langkah berikut:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

Pada kode di atas, ganti "DIREKTORI DOKUMEN ANDA" dengan jalur ke direktori proyek Anda.

## Langkah 2: Mengatur Opsi LinkDuplikatStreams

Untuk mengatur opsi LinkDuplikatStreams, ikuti langkah-langkah berikut:

```csharp
// Setel opsi LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    LinkDuplcateStreams = true
};
```

Pada kode di atas, kita membuat instance baru OptimizationOptions dan menyetel opsi LinkDuplicationStreams ke true.

## Langkah 3: Mengoptimalkan Dokumen PDF

Untuk mengoptimalkan dokumen PDF, ikuti langkah-langkah berikut:

```csharp
// Optimalkan dokumen PDF menggunakan OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

Pada kode di atas, kami menggunakan metode OptimizeResources dari objek pdfDocument untuk mengoptimalkan dokumen PDF menggunakan OptimizationOptions yang kami buat sebelumnya.

## Langkah 4: Menyimpan Dokumen yang Diperbarui

Untuk menyimpan dokumen yang diperbarui, ikuti langkah-langkah berikut:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Simpan dokumen yang diperbarui
pdfDocument.Save(dataDir);
```

Pada kode di atas, kami menggunakan metode Simpan pada objek pdfDocument untuk menyimpan dokumen yang diperbarui ke file baru bernama "OptimizeDocument_out.pdf" di direktori proyek.

### Contoh Kode Sumber untuk Aliran Duplikat Tautan menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Setel opsi LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	LinkDuplcateStreams = true
};
// Optimalkan dokumen PDF menggunakan OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Simpan dokumen yang diperbarui
pdfDocument.Save(dataDir);
```

## Kesimpulan

Fitur Link Duplikat Aliran Aspose.PDF untuk .NET menyediakan cara efektif untuk mengoptimalkan file PDF dengan mengurangi ukurannya. Dengan mengidentifikasi dan menghubungkan aliran duplikat, perpustakaan membantu membuat dokumen PDF lebih efisien tanpa mengorbankan integritas data atau kualitas visual. Pengembang dapat dengan mudah menerapkan fitur ini menggunakan langkah-langkah yang disediakan dan contoh kode sumber, sehingga meningkatkan kinerja dan efisiensi penyimpanan file PDF mereka.

### FAQ

#### T: Apa tujuan fitur Tautan Duplikat Aliran di Aspose.PDF untuk .NET?

J: Fitur Tautan Duplikat Aliran di Aspose.PDF untuk .NET digunakan untuk mengoptimalkan file PDF dengan mengidentifikasi dan menautkan aliran duplikat dalam dokumen. Dalam file PDF, mungkin ada aliran duplikat (seperti gambar atau font) yang menghabiskan ruang yang tidak diperlukan. Dengan menghubungkan aliran duplikat ini, ukuran file dapat dikurangi, sehingga menghasilkan dokumen PDF yang lebih efisien dan lebih kecil.

#### T: Bagaimana cara kerja fitur Link Duplikat Streaming?

J: Fitur Tautan Duplikat Aliran bekerja dengan menganalisis aliran konten dokumen PDF dan mengidentifikasi aliran duplikat yang memiliki konten yang sama. Alih-alih menyimpan aliran duplikat ini secara terpisah, fitur ini membuat tautan di antara aliran tersebut, yang secara efektif berbagi konten yang sama. Teknik optimasi ini mengurangi ukuran keseluruhan dokumen PDF tanpa mempengaruhi tampilan visual atau fungsinya.

#### T: Apakah fitur Link Duplikat Aliran dapat menyebabkan hilangnya data atau kualitas dokumen PDF?

J: Tidak, fitur Link Duplikat Aliran tidak menyebabkan hilangnya data atau kualitas dokumen PDF. Itu hanya mengoptimalkan ukuran file dengan menghubungkan aliran duplikat, tanpa mengubah konten atau tampilan visual dokumen. Fitur tersebut dirancang untuk memastikan dokumen PDF tetap utuh dan menjaga kualitas aslinya.