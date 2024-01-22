---
title: Cari Dan Dapatkan Halaman Teks Dalam File PDF
linktitle: Cari Dan Dapatkan Halaman Teks Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mencari dan mendapatkan teks dari halaman tertentu dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 430
url: /id/net/programming-with-text/search-and-get-text-page/
---
Tutorial ini menjelaskan cara menggunakan Aspose.PDF untuk .NET untuk mencari dan mendapatkan teks dari halaman tertentu dalam file PDF. Kode sumber C# yang disediakan menunjukkan proses langkah demi langkah.

## Prasyarat

Sebelum melanjutkan tutorial, pastikan Anda memiliki hal berikut:

- Pengetahuan dasar bahasa pemrograman C#.
- Aspose.PDF untuk perpustakaan .NET diinstal. Anda dapat memperolehnya dari situs Aspose atau menggunakan NuGet untuk menginstalnya di proyek Anda.

## Langkah 1: Siapkan proyek

Mulailah dengan membuat proyek C# baru di lingkungan pengembangan terintegrasi (IDE) pilihan Anda dan tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan

Tambahkan arahan penggunaan berikut di awal file C# Anda untuk mengimpor namespace yang diperlukan:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Langkah 3: Muat dokumen PDF

 Tetapkan jalur ke direktori dokumen PDF Anda dan muat dokumen menggunakan`Document` kelas:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Pastikan untuk mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 4: Cari dan ekstrak teks dari halaman

 Membuat`TextFragmentAbsorber`objek untuk menemukan semua contoh frasa pencarian masukan pada halaman tertentu:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Mengganti`"Figure"` dengan teks sebenarnya yang ingin Anda cari.

## Langkah 5: Cari di halaman tertentu

Terima penyerap untuk halaman tertentu dari dokumen:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Langkah 6: dapatkan fragmen teks yang diekstraksi

Dapatkan fragmen teks yang diekstraksi menggunakan`TextFragments` properti dari`TextFragmentAbsorber` obyek:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Langkah 7: Ulangi fragmen dan segmen teks

Ulangi fragmen teks yang diperoleh dan segmennya, lalu akses propertinya:

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

Anda dapat mengubah kode dalam loop untuk melakukan tindakan lebih lanjut pada setiap segmen teks.

### Contoh kode sumber untuk Cari Dan Dapatkan Halaman Teks menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Buat objek TextAbsorber untuk menemukan semua contoh frasa pencarian masukan
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Terima penyerap untuk semua halaman
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Dapatkan fragmen teks yang diekstraksi
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Ulangi fragmennya
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara mencari dan mendapatkan teks dari halaman tertentu dokumen PDF menggunakan Aspose.PDF untuk .NET. Tutorial ini memberikan panduan langkah demi langkah, mulai dari memuat dokumen hingga mengakses segmen teks yang diekstrak. Anda sekarang dapat menggabungkannya

### FAQ

#### Q: Apa tujuan dari tutorial "Cari Dan Dapatkan Halaman Teks"?

J: Tutorial "Cari Dan Dapatkan Halaman Teks" dirancang untuk mengilustrasikan cara menggunakan perpustakaan Aspose.PDF untuk .NET untuk mencari dan mengambil teks dari halaman tertentu dalam file PDF. Tutorial ini memberikan instruksi rinci dan contoh kode C# untuk mendemonstrasikan prosesnya.

#### T: Bagaimana tutorial ini membantu mengekstraksi teks dari halaman tertentu dalam dokumen PDF?

J: Tutorial ini memandu Anda melalui proses mengekstraksi teks dari halaman tertentu dokumen PDF menggunakan perpustakaan Aspose.PDF. Ini menguraikan langkah-langkah yang diperlukan dan menyediakan kode C# untuk mencari frasa teks tertentu pada halaman yang dipilih dan mengambil segmen teks terkait.

#### Q: Apa saja prasyarat untuk mengikuti tutorial ini?

A: Sebelum memulai tutorial ini, Anda harus memiliki pemahaman dasar tentang bahasa pemrograman C#. Selain itu, Anda perlu menginstal perpustakaan Aspose.PDF untuk .NET. Anda dapat memperolehnya dari situs Aspose atau menggunakan NuGet untuk mengintegrasikannya ke dalam proyek Anda.

#### T: Bagaimana cara menyiapkan proyek saya untuk mengikuti tutorial ini?

J: Untuk memulai, buat proyek C# baru di lingkungan pengembangan terintegrasi (IDE) pilihan Anda dan tambahkan referensi ke pustaka Aspose.PDF untuk .NET. Ini akan memungkinkan Anda untuk memanfaatkan kemampuan perpustakaan dalam proyek Anda.

#### T: Bisakah saya mencari teks pada halaman tertentu di dokumen PDF?

J: Ya, tutorial ini menunjukkan cara mencari teks pada halaman tertentu dokumen PDF. Ini melibatkan penggunaan`TextFragmentAbsorber` kelas untuk menemukan contoh frasa teks tertentu pada halaman yang dipilih.

#### T: Bagaimana cara mengakses segmen teks yang diekstraksi dari halaman tertentu?

 J: Setelah mencari teks pada halaman yang ditentukan, Anda dapat mengakses segmen teks yang diekstrak menggunakan`TextSegments` properti dari`TextFragment` obyek. Properti ini menyediakan akses ke koleksi`TextSegment` objek yang berisi teks yang diekstraksi dan informasi terkait.

#### T: Informasi apa yang dapat saya ambil dari segmen teks yang diekstraksi?

J: Anda dapat mengambil berbagai detail dari segmen teks yang diekstrak, termasuk konten teks, posisi (koordinat X dan Y), informasi font (nama, ukuran, warna, dll.), dan banyak lagi. Kode contoh tutorial menunjukkan cara mengakses dan mencetak detail ini untuk setiap segmen teks.

#### T: Dapatkah saya melakukan tindakan khusus pada segmen teks yang diekstraksi?

J: Tentu saja. Setelah Anda mengekstrak segmen teks, Anda dapat menyesuaikan kode dalam loop untuk melakukan tindakan tambahan pada setiap segmen. Hal ini dapat mencakup menyimpan teks yang diekstraksi, menganalisis pola teks, atau menerapkan perubahan pemformatan.