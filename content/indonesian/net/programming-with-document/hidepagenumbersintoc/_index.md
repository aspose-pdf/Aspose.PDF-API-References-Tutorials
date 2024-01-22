---
title: Sembunyikan Nomor Halaman Di TOC
linktitle: Sembunyikan Nomor Halaman Di TOC
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menyembunyikan nomor halaman di daftar isi menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini.
type: docs
weight: 220
url: /id/net/programming-with-document/hidepagenumbersintoc/
---
Pada artikel ini, kita akan membahas implementasi fitur Sembunyikan Nomor Halaman Dalam TOC Aspose.PDF untuk .NET menggunakan C#. Kami akan mulai dengan pengenalan singkat tentang Aspose.PDF untuk .NET dan kemudian mendalami panduan langkah demi langkah untuk mengimplementasikan fitur ini. 

## Pengantar Aspose.PDF untuk .NET

Aspose.PDF untuk .NET adalah komponen manipulasi PDF yang kuat yang memungkinkan pengembang membuat, mengedit, dan memanipulasi file PDF secara terprogram. Ini menyediakan berbagai fitur dan fungsi yang memudahkan bekerja dengan dokumen PDF. Aspose.PDF untuk .NET mendukung sistem operasi 32-bit dan 64-bit dan dapat digunakan dengan platform .NET Framework, .NET Core, dan Xamarin. 

## Apa itu fitur Sembunyikan Nomor Halaman di TOC?

Daftar Isi (TOC) adalah bagian penting dari dokumen PDF yang memberikan gambaran singkat tentang konten kepada pengguna. Terkadang, pengguna mungkin ingin menyembunyikan nomor halaman di TOC agar lebih ramah pengguna. Aspose.PDF untuk .NET menyediakan fitur bawaan untuk menyembunyikan nomor halaman di TOC. Fitur ini dapat digunakan untuk membuat dokumen PDF yang lebih ramah pengguna. 

## Prasyarat

Untuk mengikuti tutorial ini, Anda memerlukan yang berikut ini:

- Visual Studio 2010 atau lebih baru
- Aspose.PDF untuk .NET diinstal pada sistem Anda
- Pengetahuan dasar bahasa pemrograman C#

## Panduan langkah demi langkah untuk menerapkan fitur Sembunyikan Nomor Halaman Dalam TOC

Ikuti langkah-langkah di bawah ini untuk mengimplementasikan fitur Sembunyikan Nomor Halaman Dalam TOC menggunakan Aspose.PDF untuk .NET:

## Langkah 1: Buat aplikasi konsol C# baru di Visual Studio

Buka Visual Studio dan buat aplikasi konsol C# baru.

## Langkah 2: Tambahkan referensi ke Aspose.PDF untuk .NET

Klik kanan pada folder Referensi di proyek Anda dan pilih Tambahkan Referensi. Telusuri ke lokasi tempat Aspose.PDF untuk .NET diinstal pada sistem Anda dan tambahkan referensi ke sana.

## Langkah 1: Buat dokumen PDF baru

Buat dokumen PDF baru menggunakan kode berikut:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Langkah 2: Buat halaman Daftar Isi

Buat halaman baru untuk TOC dan tambahkan ke dokumen PDF menggunakan kode berikut:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Langkah 3: Tambahkan bagian daftar ke kumpulan bagian dokumen PDF

Tambahkan bagian daftar ke kumpulan bagian dokumen PDF menggunakan kode berikut:

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

### Contoh Kode Sumber untuk Menyembunyikan Nomor Halaman Di TOC menggunakan Aspose.PDF untuk .NET

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
//Tambahkan bagian daftar ke kumpulan bagian dokumen Pdf
tocPage.TocInfo = tocInfo;
//Tentukan format daftar empat tingkat dengan mengatur margin kiri dan
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

Dalam tutorial ini, kita menjelajahi cara bekerja dengan metadata XMP dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Metadata XMP memberikan informasi berharga tentang dokumen PDF, termasuk judul, penulis, tanggal pembuatan, dan banyak lagi. Aspose.PDF untuk .NET memungkinkan pengembang mengakses dan memanipulasi metadata ini, menyediakan API yang fleksibel dan kuat untuk bekerja dengan dokumen PDF.

### FAQ

#### T: Apa yang dimaksud dengan metadata XMP dalam dokumen PDF?

J: Metadata XMP (Extensible Metadata Platform) dalam dokumen PDF adalah format standar untuk menyimpan informasi metadata tentang dokumen tersebut. Ini mencakup detail seperti judul dokumen, penulis, tanggal pembuatan, kata kunci, dan banyak lagi. Metadata XMP menyediakan cara terstruktur dan terstandar untuk menyimpan dan berbagi informasi tentang dokumen PDF.

#### T: Bisakah saya mengubah metadata XMP dokumen PDF menggunakan Aspose.PDF untuk .NET?

 J: Ya, Anda dapat mengubah metadata XMP dokumen PDF secara terprogram menggunakan Aspose.PDF untuk .NET. Anda dapat mengakses`Info` properti dari`Document` objek, yang memberi Anda akses ke properti metadata XMP. Anda kemudian dapat memperbarui nilai properti ini untuk mengubah metadata XMP dokumen PDF.

#### T: Bisakah saya mengekstrak properti metadata XMP khusus dari dokumen PDF menggunakan Aspose.PDF untuk .NET?

 J: Ya, Anda dapat mengekstrak properti metadata XMP khusus dari dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan`Metadata` properti dari`Document`objek, yang menyediakan akses ke semua properti metadata XMP dari dokumen PDF. Anda kemudian dapat mengekstrak properti khusus dan menggunakan nilainya sesuai kebutuhan.