---
title: Tautan Duplikat Aliran
linktitle: Tautan Duplikat Aliran
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menggunakan fitur Aspose.PDF untuk .NET Link Duplicate Streams untuk mengoptimalkan dokumen PDF Anda dengan panduan langkah demi langkah ini.
type: docs
weight: 230
url: /id/net/programming-with-document/linkduplicatestreams/
---
Aspose.PDF untuk .NET adalah pustaka yang lengkap dan canggih yang menyediakan berbagai fitur untuk bekerja dengan file PDF. Salah satu fitur utamanya adalah kemampuan untuk mengoptimalkan file PDF. Dalam artikel ini, kami akan menjelaskan cara menggunakan fitur Link Duplicate Streams dari Aspose.PDF untuk .NET untuk mengoptimalkan file PDF. Kami akan memberikan petunjuk langkah demi langkah dan menyertakan contoh kode sumber lengkap agar mudah diikuti oleh pengembang.

## Langkah 1: Membuka Dokumen PDF

Untuk membuka dokumen PDF menggunakan Aspose.PDF untuk .NET, ikuti langkah-langkah berikut:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

Pada kode di atas, ganti "DIREKTORI DOKUMEN ANDA" dengan jalur ke direktori proyek Anda.

## Langkah 2: Mengatur Opsi LinkDuplicateStreams

Untuk mengatur opsi LinkDuplicateStreams, ikuti langkah-langkah berikut:

```csharp
// Tetapkan opsi LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    LinkDuplcateStreams = true
};
```

Dalam kode di atas, kami membuat contoh baru OptimizationOptions dan menetapkan opsi LinkDuplicateStreams ke true.

## Langkah 3: Mengoptimalkan Dokumen PDF

Untuk mengoptimalkan dokumen PDF, ikuti langkah-langkah berikut:

```csharp
// Optimalkan dokumen PDF menggunakan OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

Dalam kode di atas, kami menggunakan metode OptimizeResources dari objek pdfDocument untuk mengoptimalkan dokumen PDF menggunakan OptimizationOptions yang kami buat sebelumnya.

## Langkah 4: Menyimpan Dokumen yang Diperbarui

Untuk menyimpan dokumen yang diperbarui, ikuti langkah-langkah berikut:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Simpan dokumen yang diperbarui
pdfDocument.Save(dataDir);
```

Dalam kode di atas, kami menggunakan metode Save dari objek pdfDocument untuk menyimpan dokumen yang diperbarui ke file baru bernama "OptimizeDocument_out.pdf" di direktori proyek.

### Contoh Kode Sumber untuk Aliran Duplikat Tautan menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Tetapkan opsi LinkDuplcateStreams
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

Fitur Link Duplicate Streams dari Aspose.PDF untuk .NET menyediakan cara yang efektif untuk mengoptimalkan file PDF dengan mengurangi ukurannya. Dengan mengidentifikasi dan menautkan aliran duplikat, pustaka ini membantu membuat dokumen PDF yang lebih efisien tanpa mengorbankan integritas data atau kualitas visual. Pengembang dapat dengan mudah menerapkan fitur ini menggunakan langkah-langkah yang disediakan dan contoh kode sumber, yang meningkatkan kinerja dan efisiensi penyimpanan file PDF mereka.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan fitur Link Duplicate Streams di Aspose.PDF untuk .NET?

J: Fitur Link Duplicate Streams di Aspose.PDF untuk .NET digunakan untuk mengoptimalkan file PDF dengan mengidentifikasi dan menautkan aliran duplikat dalam dokumen. Dalam file PDF, mungkin ada aliran duplikat (seperti gambar atau font) yang menghabiskan ruang yang tidak perlu. Dengan menautkan aliran duplikat ini, ukuran file dapat dikurangi, sehingga menghasilkan dokumen PDF yang lebih efisien dan lebih kecil.

#### T: Bagaimana cara kerja fitur Link Duplicate Streams?

A: Fitur Link Duplicate Streams bekerja dengan menganalisis aliran konten dokumen PDF dan mengidentifikasi aliran duplikat yang memiliki konten yang sama. Alih-alih menyimpan aliran duplikat ini secara terpisah, fitur ini membuat tautan di antara aliran tersebut, sehingga secara efektif berbagi konten yang sama. Teknik pengoptimalan ini mengurangi ukuran keseluruhan dokumen PDF tanpa memengaruhi tampilan visual atau fungsinya.

#### T: Apakah fitur Link Duplicate Streams dapat menyebabkan hilangnya data atau kualitas pada dokumen PDF?

J: Tidak, fitur Link Duplicate Streams tidak menyebabkan hilangnya data atau kualitas dokumen PDF. Fitur ini hanya mengoptimalkan ukuran file dengan menautkan aliran duplikat, tanpa mengubah konten atau tampilan visual dokumen. Fitur ini dirancang untuk memastikan bahwa dokumen PDF tetap utuh dan mempertahankan kualitas aslinya.