---
title: Cari Halaman Segmen Teks Dalam File PDF
linktitle: Cari Halaman Segmen Teks Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mencari segmen teks pada halaman dalam berkas PDF dan mengambil propertinya menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 470
url: /id/net/programming-with-text/search-text-segments-page/
---
Tutorial ini menjelaskan cara menggunakan Aspose.PDF untuk .NET guna mencari segmen teks tertentu pada halaman file PDF dan mengambil propertinya. Kode sumber C# yang disediakan menunjukkan proses tersebut langkah demi langkah.

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
```

## Langkah 3: Tetapkan jalur ke direktori dokumen

 Atur jalur ke direktori dokumen Anda menggunakan`dataDir` variabel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 4: Muat dokumen PDF

 Muat dokumen PDF menggunakan`Document` kelas:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Mengganti`"SearchTextSegmentsPage.pdf"` dengan nama sebenarnya berkas PDF Anda.

## Langkah 5: Buat TextFragmentAbsorber

 Membuat sebuah`TextFragmentAbsorber` objek untuk menemukan semua contoh frasa pencarian input:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Mengganti`"text"` dengan frasa pencarian yang Anda inginkan.

## Langkah 6: Terima penyerap untuk halaman tertentu

Terima penyerap untuk halaman dokumen yang diinginkan:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Mengganti`2` dengan nomor halaman yang diinginkan (indeks berbasis 1).

## Langkah 7: Ambil segmen teks yang diekstraksi

 Dapatkan segmen teks yang diekstraksi menggunakan`TextFragments` milik`TextFragmentAbsorber` obyek:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Langkah 8: Ulangi melalui segmen teks

Ulangi segmen teks yang diambil dan akses propertinya:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

Ubah kode dalam loop untuk melakukan tindakan lebih lanjut pada setiap segmen teks jika diperlukan.

### Contoh kode sumber untuk Halaman Pencarian Segmen Teks menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Buat objek TextAbsorber untuk menemukan semua contoh frasa pencarian input
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Terima penyerap untuk semua halaman
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Dapatkan fragmen teks yang diekstraksi
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Ulangi melalui fragmen
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara mencari segmen teks tertentu pada halaman dokumen PDF menggunakan Aspose.PDF untuk .NET. Tutorial ini menyediakan panduan langkah demi langkah, mulai dari memuat dokumen hingga mengakses segmen teks yang diekstrak. Kini Anda dapat memasukkan kode ini ke dalam proyek C# Anda sendiri untuk melakukan pencarian segmen teks tingkat lanjut dalam file PDF.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial "Cari Halaman Segmen Teks dalam Berkas PDF"?

J: Tutorial "Halaman Pencarian Segmen Teks dalam Berkas PDF" menyediakan panduan lengkap tentang cara memanfaatkan pustaka Aspose.PDF untuk .NET guna mencari segmen teks tertentu pada halaman tertentu dari dokumen PDF. Panduan ini mencakup proses menyiapkan proyek, memuat dokumen PDF, mencari segmen teks, dan mengambil propertinya menggunakan kode C#.

#### T: Bagaimana tutorial ini membantu dalam pencarian segmen teks tertentu dalam dokumen PDF?

J: Tutorial ini menunjukkan proses menemukan dan mengekstrak segmen teks tertentu pada halaman tertentu dari dokumen PDF. Dengan mengikuti langkah-langkah dan contoh kode yang diberikan, pengguna dapat secara efektif mencari segmen teks yang diinginkan dan mengambil informasi tentang propertinya.

#### T: Prasyarat apa yang diperlukan untuk mengikuti tutorial ini?

J: Sebelum memulai tutorial ini, Anda harus memiliki pemahaman dasar tentang bahasa pemrograman C#. Selain itu, Anda perlu menginstal pustaka Aspose.PDF for .NET. Anda dapat memperolehnya dari situs web Aspose atau menginstalnya di proyek Anda menggunakan NuGet.

#### T: Bagaimana cara menyiapkan proyek saya untuk mengikuti tutorial ini?

J: Untuk memulai, buat proyek C# baru di lingkungan pengembangan terpadu (IDE) pilihan Anda dan tambahkan referensi ke pustaka Aspose.PDF untuk .NET. Ini akan memungkinkan Anda memanfaatkan fitur pustaka untuk mencari dan bekerja dengan dokumen PDF.

#### T: Dapatkah saya menggunakan tutorial ini untuk mencari segmen teks tertentu pada halaman mana pun di PDF?

J: Ya, tutorial ini menyediakan petunjuk tentang cara mencari segmen teks tertentu pada halaman tertentu dari dokumen PDF. Tutorial ini memandu pengguna dalam menyiapkan proyek, memuat PDF, dan menggunakan pustaka Aspose.PDF untuk menemukan dan mengambil properti segmen teks yang diinginkan.

#### T: Bagaimana cara menentukan teks yang ingin saya cari dalam tutorial ini?

 A: Untuk menentukan teks yang ingin Anda cari, buatlah`TextFragmentAbsorber` objek dan mengatur parameter pencariannya menggunakan`Text` properti. Ganti default`"text"` dalam kode tutorial dengan frasa pencarian yang Anda inginkan.

#### T: Bagaimana cara mengambil properti segmen teks yang diekstrak?

Setelah menerima`TextFragmentAbsorber` untuk halaman tertentu dari PDF, Anda dapat mengambil segmen teks yang diekstraksi menggunakan`TextFragments` properti objek penyerap. Ini menyediakan akses ke kumpulan fragmen teks, yang masing-masing berisi beberapa segmen teks.

#### T: Dapatkah saya menyesuaikan kode untuk melakukan tindakan tambahan pada setiap segmen teks?

A: Tentu saja. Contoh kode tutorial menyediakan loop untuk mengulang segmen teks yang diambil. Anda dapat menyesuaikan kode dalam loop ini untuk melakukan tindakan tambahan pada setiap segmen teks, berdasarkan persyaratan proyek Anda.

#### T: Bagaimana cara menyimpan dokumen PDF yang dimodifikasi setelah mengekstrak segmen teks?

J: Tutorial ini terutama berfokus pada pencarian segmen teks dan pengambilan propertinya. Jika Anda ingin melakukan modifikasi pada PDF, Anda dapat merujuk ke dokumentasi Aspose.PDF lainnya untuk mempelajari cara memanipulasi dan menyimpan dokumen berdasarkan kebutuhan spesifik Anda.