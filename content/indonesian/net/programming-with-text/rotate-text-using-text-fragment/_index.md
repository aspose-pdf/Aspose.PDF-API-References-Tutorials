---
title: Memutar Teks Menggunakan Fragmen Teks Dalam File PDF
linktitle: Memutar Teks Menggunakan Fragmen Teks Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara memutar teks menggunakan fragmen teks dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 390
url: /id/net/programming-with-text/rotate-text-using-text-fragment/
---
Tutorial ini menjelaskan cara menggunakan Aspose.PDF untuk .NET guna memutar teks menggunakan fragmen teks dalam berkas PDF. Kode sumber C# yang disediakan menunjukkan proses tersebut langkah demi langkah.

## Prasyarat

Sebelum melanjutkan tutorial, pastikan Anda memiliki hal berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET telah terinstal. Anda dapat memperolehnya dari situs web Aspose atau menggunakan NuGet untuk menginstalnya di proyek Anda.

## Langkah 1: Siapkan proyek

Mulailah dengan membuat proyek C# baru di lingkungan pengembangan terintegrasi (IDE) pilihan Anda dan tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan

Tambahkan perintah berikut di awal file C# Anda untuk mengimpor namespace yang diperlukan:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## Langkah 3: Buat dokumen PDF

 Inisialisasi`Document` objek untuk membuat dokumen PDF baru:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Pastikan untuk mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 4: Tambahkan halaman

 Dapatkan halaman tertentu dari dokumen menggunakan`Pages.Add()` metode:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Langkah 5: Buat fragmen teks

 Buat beberapa`TextFragment` objek, mengatur teks dan propertinya, dan menentukan posisinya di halaman:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Sesuaikan teks, posisi, dan properti lainnya sesuai keinginan.

## Langkah 6: Buat TextBuilder dan tambahkan fragmen teks

 Membuat sebuah`TextBuilder` objek menggunakan`pdfPage` dan menambahkan fragmen teks ke halaman PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Langkah 7: Simpan dokumen PDF

 Simpan dokumen PDF yang dimodifikasi ke file menggunakan`Save` metode:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Pastikan untuk mengganti`"TextFragmentTests_Rotated1_out.pdf"` dengan nama file keluaran yang diinginkan.

### Contoh kode sumber untuk Memutar Teks Menggunakan Fragmen Teks menggunakan Aspose.PDF untuk .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inisialisasi objek dokumen
Document pdfDocument = new Document();
// Dapatkan halaman tertentu
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Buat fragmen teks
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Mengatur properti teks
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Buat fragmen teks yang diputar
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Mengatur properti teks
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Buat fragmen teks yang diputar
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Mengatur properti teks
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// membuat objek TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Tambahkan fragmen teks ke halaman PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Simpan dokumen
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara memutar teks menggunakan fragmen teks dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Tutorial ini menyediakan panduan langkah demi langkah, mulai dari membuat dokumen hingga menyimpan versi yang dimodifikasi. Anda sekarang dapat memasukkan kode ini ke dalam proyek C# Anda sendiri untuk memanipulasi rotasi teks dalam file PDF.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial "Memutar Teks Menggunakan Fragmen Teks"?

J: Tutorial "Putar Teks Menggunakan Fragmen Teks" bertujuan untuk memandu Anda melalui proses penggunaan pustaka Aspose.PDF untuk .NET guna memutar teks menggunakan fragmen teks dalam dokumen PDF. Tutorial ini menyediakan petunjuk langkah demi langkah dan contoh kode untuk mencapai fungsi ini.

#### T: Apa yang dimaksud dengan "memutar teks menggunakan fragmen teks"?

A: Memutar teks menggunakan fragmen teks mengacu pada kemampuan untuk menerapkan rotasi pada fragmen teks individual dalam dokumen PDF menggunakan pustaka Aspose.PDF. Teknik ini memungkinkan Anda untuk mengontrol orientasi teks pada berbagai sudut atau posisi dalam konten PDF.

#### T: Mengapa saya ingin memutar fragmen teks dalam dokumen PDF?

A: Memutar fragmen teks dalam dokumen PDF dapat berguna untuk berbagai tujuan, seperti menekankan konten tertentu, membuat desain artistik, atau meningkatkan tata letak dan keterbacaan.

#### T: Bagaimana cara menyiapkan proyek untuk tutorial?

A: Untuk menyiapkan proyek:

1. Buat proyek C# baru di lingkungan pengembangan terintegrasi (IDE) pilihan Anda.
2. Tambahkan referensi ke pustaka Aspose.PDF untuk .NET.
3. Tambahkan direktif penggunaan yang diperlukan ke berkas C# Anda.

#### T: Bagaimana cara membuat dokumen PDF baru?

 A: Untuk membuat dokumen PDF baru, inisialisasi`Document`objek dari pustaka Aspose.PDF. Anda dapat menggunakan objek ini untuk menambahkan halaman dan konten ke PDF.

#### T: Bagaimana cara memutar fragmen teks menggunakan fragmen teks?

A: Untuk memutar fragmen teks menggunakan fragmen teks:

1.  Membuat`TextFragment` objek.
2. Mengatur teks dan properti fragmen teks.
3. Tentukan posisi fragmen teks pada halaman.
4.  Atur sudut rotasi menggunakan`TextState.Rotation` properti dari fragmen teks.
5.  Membuat sebuah`TextBuilder`objek dan menambahkan fragmen teks ke halaman PDF.

#### T: Dapatkah saya menerapkan sudut rotasi yang berbeda pada fragmen teks yang berbeda?

 A: Ya, Anda dapat menerapkan sudut rotasi yang berbeda ke berbagai`TextFragment` objek. Setiap fragmen teks dapat memiliki sudut rotasinya sendiri yang ditentukan menggunakan`TextState.Rotation` milik.

#### T: Bagaimana cara menyimpan dokumen PDF dengan fragmen teks yang diputar?

 A: Untuk menyimpan dokumen PDF dengan fragmen teks yang diputar, gunakan`Save` metode dari`Document` objek dan menyediakan jalur dan nama file keluaran yang diinginkan.