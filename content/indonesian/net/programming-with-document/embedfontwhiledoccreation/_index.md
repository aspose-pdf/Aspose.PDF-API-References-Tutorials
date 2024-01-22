---
title: Sematkan Font Saat Pembuatan Dokumen PDF
linktitle: Sematkan Font Saat Pembuatan Dokumen PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menyematkan font saat membuat dokumen PDF menggunakan Aspose.PDF untuk .NET. Pastikan tampilan yang benar pada perangkat yang berbeda.
type: docs
weight: 140
url: /id/net/programming-with-document/embedfontwhiledoccreation/
---
Pada tutorial kali ini kita akan membahas cara menyematkan font sekaligus membuat dokumen PDF menggunakan Aspose.PDF for .NET. Aspose.PDF untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang membuat, mengedit, dan memanipulasi dokumen PDF secara terprogram. Perpustakaan ini menyediakan berbagai fitur untuk bekerja dengan dokumen PDF, termasuk menambahkan teks, gambar, tabel, dan masih banyak lagi. Menyematkan font saat membuat dokumen PDF adalah persyaratan umum bagi pengembang yang ingin memastikan bahwa dokumen PDF ditampilkan dengan benar di perangkat yang berbeda, terlepas dari apakah font yang diperlukan diinstal pada perangkat tersebut atau tidak.

## Langkah 1: Buat Aplikasi Konsol C# baru
Untuk memulai, buat Aplikasi Konsol C# baru di Visual Studio. Anda dapat menamainya sesuka Anda. Setelah proyek dibuat, Anda perlu menambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Impor Namespace Aspose.PDF
Tambahkan baris kode berikut di bagian atas file C# Anda untuk mengimpor namespace Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Langkah 3: Buat Instansiasi Objek Pdf
Buat instance objek Pdf dengan memanggil konstruktor kosongnya:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Langkah 4: Buat Bagian di Objek Pdf
Buat bagian di objek Pdf:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Langkah 5: Tambahkan Teks ke Bagian
Tambahkan teks ke bagian:

```csharp
Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");
Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
```

## Langkah 6: Atur Font dan Sematkan
Atur font dan sematkan:

```csharp
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
fragment.Segments.Add(segment);
page.Paragraphs.Add(fragment);
```

## Langkah 7: Simpan Dokumen PDF
Setelah Anda menyematkan font saat membuat dokumen PDF, Anda perlu menyimpan dokumen tersebut:

```csharp
dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
// Simpan Dokumen PDF
doc.Save(dataDir);
```

### Contoh Kode Sumber untuk Menyematkan Font Saat Pembuatan Dokumen menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat instance objek Pdf dengan memanggil konstruktor kosongnya
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Buat bagian di objek Pdf
Aspose.Pdf.Page page = doc.Pages.Add();

Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");

Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
fragment.Segments.Add(segment);
page.Paragraphs.Add(fragment);

dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
// Simpan Dokumen PDF
doc.Save(dataDir);
```

## Kesimpulan
Dalam tutorial ini, kita telah membahas cara menyematkan font saat membuat dokumen PDF menggunakan Aspose.PDF untuk .NET. Aspose.PDF untuk .NET menyediakan API sederhana dan mudah digunakan untuk bekerja dengan dokumen PDF, termasuk menambahkan dan menyematkan font. Menyematkan font saat membuat dokumen PDF merupakan langkah penting untuk memastikan bahwa dokumen ditampilkan dengan benar di perangkat yang berbeda, terlepas dari apakah font yang diperlukan diinstal pada perangkat tersebut atau tidak.

### FAQ untuk menyematkan font saat pembuatan dokumen PDF

#### T: Mengapa menyematkan font saat membuat dokumen PDF itu penting?

J: Menyematkan font saat membuat dokumen PDF penting untuk memastikan bahwa dokumen ditampilkan dengan benar di perangkat yang berbeda, meskipun font yang diperlukan tidak diinstal pada perangkat tersebut. Hal ini membantu mempertahankan tampilan dokumen yang diinginkan dan mencegah masalah penggantian font.

#### T: Bagaimana cara menyematkan font saat membuat dokumen PDF menggunakan Aspose.PDF untuk .NET?

J: Anda dapat menyematkan font saat membuat dokumen PDF menggunakan Aspose.PDF untuk .NET dengan menentukan font dan mengatur`IsEmbedded` properti ke`true`. Ini memastikan bahwa data font tertanam dalam file PDF.

#### T: Dapatkah saya menentukan font khusus saat menyematkannya dalam dokumen PDF?

J: Ya, Anda dapat menentukan font khusus saat menyematkannya dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Ini memungkinkan Anda untuk menggunakan font tertentu yang sesuai dengan kebutuhan desain Anda.

#### T: Apakah Aspose.PDF untuk .NET kompatibel dengan berbagai format font?

J: Ya, Aspose.PDF untuk .NET kompatibel dengan berbagai format font, termasuk font TrueType, OpenType, dan Tipe 1. Itu dapat menyematkan font dalam dokumen PDF apa pun formatnya.

#### T: Dapatkah saya menyesuaikan proses penyematan font?

 J: Ya, Anda dapat menyesuaikan proses penyematan font menggunakan Aspose.PDF untuk .NET. Anda dapat menentukan font dan mengatur properti seperti`IsEmbedded` untuk mengontrol bagaimana font disematkan dalam dokumen PDF.
