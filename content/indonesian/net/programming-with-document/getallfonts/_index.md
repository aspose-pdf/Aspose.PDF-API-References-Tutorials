---
title: Dapatkan Semua Font Dalam File PDF
linktitle: Dapatkan Semua Font Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menggunakan Aspose.PDF untuk .NET untuk mendapatkan semua font yang digunakan dalam file PDF secara terprogram dengan panduan langkah demi langkah dan kode contoh ini.
type: docs
weight: 160
url: /id/net/programming-with-document/getallfonts/
---
Aspose.PDF untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan file PDF secara terprogram. Salah satu fitur yang disediakannya adalah kemampuan untuk mendapatkan semua font yang digunakan dalam file PDF. Ini dapat berguna jika Anda perlu menganalisis atau memanipulasi font dalam file PDF secara terprogram.

Dalam tutorial ini, kita akan membahas cara menggunakan Aspose.PDF untuk .NET untuk mendapatkan semua font yang digunakan dalam dokumen PDF. Kami akan memberikan panduan langkah demi langkah tentang cara melakukan ini, bersama dengan contoh kode sumber.

## Langkah 1: Buat Aplikasi Konsol C# baru
Untuk memulai, buat Aplikasi Konsol C# baru di Visual Studio. Anda dapat menamainya sesuka Anda. Setelah proyek dibuat, Anda perlu menambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Impor Namespace Aspose.PDF
Tambahkan baris kode berikut di bagian atas file C# Anda untuk mengimpor namespace Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Langkah 3: Muat Dokumen PDF
Muat dokumen PDF tempat Anda ingin mendapatkan font:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Langkah 4: Dapatkan Semua Font
Dapatkan semua font yang digunakan dalam dokumen PDF:

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## Langkah 5: Cetak Semua Font
Cetak semua font yang digunakan dalam dokumen PDF:

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### Contoh kode sumber untuk Dapatkan Semua Font menggunakan Aspose.PDF untuk .NET
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## Kesimpulan
Dalam tutorial ini, kita telah membahas cara mendapatkan semua font yang digunakan dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Mendapatkan semua font yang digunakan dalam dokumen PDF dapat berguna jika Anda perlu menganalisis atau memanipulasi font dalam dokumen PDF secara terprogram. Aspose.PDF untuk .NET menyediakan API sederhana dan mudah digunakan untuk bekerja dengan dokumen PDF, termasuk semua font yang digunakan dalam dokumen PDF.

### FAQ

#### T: Mengapa saya harus menggunakan semua font dalam dokumen PDF?

J: Mendapatkan semua font yang digunakan dalam dokumen PDF dapat berguna jika Anda perlu menganalisis atau memanipulasi font secara terprogram untuk berbagai tujuan, seperti penggantian font atau penyesuaian font.

#### T: Bagaimana cara mendapatkan semua font yang digunakan dalam dokumen PDF menggunakan Aspose.PDF untuk .NET?

 J: Anda bisa mendapatkan semua font yang digunakan dalam dokumen PDF menggunakan Aspose.PDF untuk .NET dengan menelepon`GetAllFonts` metode`FontUtilities` kelas. Metode ini mengembalikan array`Aspose.Pdf.Text.Font` objek, yang mewakili font yang digunakan dalam dokumen PDF.

#### T: Bisakah saya memfilter font berdasarkan kriteria tertentu?

A: Ya, Anda dapat memfilter font berdasarkan kriteria tertentu menggunakan Aspose.PDF untuk .NET. Setelah mendapatkan semua font, Anda dapat menganalisis font secara terprogram dan menerapkan logika pemfilteran sesuai kebutuhan.

#### T: Apakah Aspose.PDF untuk .NET kompatibel dengan berbagai format font?

J: Ya, Aspose.PDF untuk .NET kompatibel dengan berbagai format font, termasuk font TrueType, OpenType, dan Tipe 1. Ini dapat bekerja dengan format font yang berbeda dan menanganinya selama manipulasi dokumen PDF.