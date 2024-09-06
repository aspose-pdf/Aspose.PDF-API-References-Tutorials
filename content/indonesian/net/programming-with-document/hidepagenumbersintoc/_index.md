---
title: Sembunyikan Nomor Halaman Di Daftar Isi
linktitle: Sembunyikan Nomor Halaman Di Daftar Isi
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menyembunyikan nomor halaman dalam daftar isi menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini.
type: docs
weight: 220
url: /id/net/programming-with-document/hidepagenumbersintoc/
---
Dalam artikel ini, kita akan membahas penerapan fitur Sembunyikan Nomor Halaman di Daftar Isi Aspose.PDF untuk .NET menggunakan C#. Kita akan mulai dengan pengenalan singkat tentang Aspose.PDF untuk .NET, lalu menyelami panduan langkah demi langkah untuk menerapkan fitur ini. 

## Pengantar Aspose.PDF untuk .NET

Aspose.PDF untuk .NET adalah komponen manipulasi PDF yang canggih yang memungkinkan pengembang untuk membuat, mengedit, dan memanipulasi file PDF secara terprogram. Komponen ini menyediakan berbagai fitur dan fungsi yang memudahkan pengerjaan dokumen PDF. Aspose.PDF untuk .NET mendukung sistem operasi 32-bit dan 64-bit dan dapat digunakan dengan platform .NET Framework, .NET Core, dan Xamarin. 

## Apa itu fitur Sembunyikan Nomor Halaman di Daftar Isi?

Daftar Isi (TOC) merupakan bagian penting dari dokumen PDF yang memberikan gambaran singkat tentang konten kepada pengguna. Terkadang, pengguna mungkin ingin menyembunyikan nomor halaman di TOC agar lebih mudah digunakan. Aspose.PDF untuk .NET menyediakan fitur bawaan untuk menyembunyikan nomor halaman di TOC. Fitur ini dapat digunakan untuk membuat dokumen PDF yang lebih mudah digunakan. 

## Prasyarat

Untuk mengikuti tutorial ini, Anda memerlukan hal berikut:

- Visual Studio 2010 atau yang lebih baru
- Aspose.PDF untuk .NET terinstal di sistem Anda
- Pengetahuan dasar bahasa pemrograman C#

## Panduan langkah demi langkah untuk menerapkan fitur Sembunyikan Nomor Halaman di Daftar Isi

Ikuti langkah-langkah di bawah ini untuk menerapkan fitur Sembunyikan Nomor Halaman di Daftar Isi menggunakan Aspose.PDF untuk .NET:

## Langkah 1: Buat aplikasi konsol C# baru di Visual Studio

Buka Visual Studio dan buat aplikasi konsol C# baru.

## Langkah 2: Tambahkan referensi ke Aspose.PDF untuk .NET

Klik kanan pada folder Referensi di proyek Anda dan pilih Tambahkan Referensi. Telusuri lokasi tempat Aspose.PDF for .NET diinstal di sistem Anda dan tambahkan referensi ke sana.

## Langkah 1: Buat dokumen PDF baru

Buat dokumen PDF baru menggunakan kode berikut:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Langkah 2: Buat halaman TOC

Buat halaman baru untuk TOC dan tambahkan ke dokumen PDF menggunakan kode berikut:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Langkah 3: Tambahkan bagian daftar ke koleksi bagian dokumen PDF

Tambahkan bagian daftar ke koleksi bagian dokumen PDF menggunakan kode berikut:

```csharp
tocPage.TocInfo = tocInfo;
```

## Langkah 4: Tentukan format daftar empat level

Tentukan format daftar empat level dengan mengatur margin kiri dan pengaturan format teks setiap level menggunakan kode berikut:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## Langkah 5: Tambahkan empat judul di bagian tersebut

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### Contoh Kode Sumber untuk Menyembunyikan Nomor Halaman di Daftar Isi menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Tambahkan bagian daftar ke koleksi bagian dokumen Pdf
tocPage.TocInfo = tocInfo;
//Tentukan format daftar empat level dengan mengatur margin kiri dan
//pengaturan format teks setiap level

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//Tambahkan empat judul di bagian tersebut
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## Kesimpulan

Dalam tutorial ini, kami mengeksplorasi cara bekerja dengan metadata XMP dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Metadata XMP menyediakan informasi berharga tentang dokumen PDF, termasuk judul, penulis, tanggal pembuatan, dan banyak lagi. Aspose.PDF untuk .NET memungkinkan pengembang untuk mengakses dan memanipulasi metadata ini, menyediakan API yang fleksibel dan canggih untuk bekerja dengan dokumen PDF.

### Pertanyaan yang Sering Diajukan

#### T: Apa itu metadata XMP dalam dokumen PDF?

J: Metadata XMP (Extensible Metadata Platform) dalam dokumen PDF adalah format standar untuk menyimpan informasi metadata tentang dokumen tersebut. Metadata ini mencakup detail seperti judul dokumen, penulis, tanggal pembuatan, kata kunci, dan banyak lagi. Metadata XMP menyediakan cara terstruktur dan terstandarisasi untuk menyimpan dan berbagi informasi tentang dokumen PDF.

#### T: Dapatkah saya mengubah metadata XMP dokumen PDF menggunakan Aspose.PDF untuk .NET?

 A: Ya, Anda dapat mengubah metadata XMP dari dokumen PDF secara terprogram menggunakan Aspose.PDF untuk .NET. Anda dapat mengakses`Info` milik`Document` objek, yang memberi Anda akses ke properti metadata XMP. Anda kemudian dapat memperbarui nilai properti ini untuk mengubah metadata XMP dari dokumen PDF.

#### T: Dapatkah saya mengekstrak properti metadata XMP kustom dari dokumen PDF menggunakan Aspose.PDF untuk .NET?

 A: Ya, Anda dapat mengekstrak properti metadata XMP khusus dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan`Metadata` milik`Document`objek, yang menyediakan akses ke semua properti metadata XMP dari dokumen PDF. Anda kemudian dapat mengekstrak properti kustom dan menggunakan nilainya sesuai kebutuhan.