---
title: Cari dan Dapatkan Semua Teks
linktitle: Cari dan Dapatkan Semua Teks
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mencari dan mendapatkan teks dari semua halaman dokumen PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 420
url: /id/net/programming-with-text/search-and-get-text-all/
---
Tutorial ini menjelaskan cara menggunakan Aspose.PDF untuk .NET guna mencari dan mendapatkan teks dari semua halaman dokumen PDF. Kode sumber C# yang disediakan menunjukkan proses tersebut langkah demi langkah.

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

## Langkah 3: Muat dokumen PDF

 Atur jalur ke direktori dokumen PDF Anda dan muat dokumen menggunakan`Document` kelas:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Pastikan untuk mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 4: Cari dan ekstrak teks

 Membuat sebuah`TextFragmentAbsorber` objek untuk menemukan semua contoh frasa pencarian input:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Mengganti`"text"` dengan teks sebenarnya yang ingin Anda cari.

## Langkah 5: Cari di semua halaman

Terima penyerap untuk semua halaman dokumen:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Langkah 6: dapatkan fragmen teks yang diekstraksi

 Dapatkan fragmen teks yang diekstraksi menggunakan`TextFragments` milik`TextFragmentAbsorber` obyek:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Langkah 7: Ulangi melalui fragmen teks

Ulangi fragmen teks getd dan akses propertinya:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text: {0} ", textFragment.Text);
    Console.WriteLine("Position: {0} ", textFragment.Position);
    Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

Anda dapat memodifikasi kode dalam loop untuk melakukan tindakan lebih lanjut pada setiap fragmen teks.

### Contoh kode sumber untuk Pencarian dan Dapatkan Semua Teks menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Buat objek TextAbsorber untuk menemukan semua contoh frasa pencarian input
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Terima penyerap untuk semua halaman
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Dapatkan fragmen teks yang diekstraksi
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Ulangi melalui fragmen
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara mencari dan mendapatkan teks dari semua halaman dokumen PDF menggunakan Aspose.PDF for .NET. Tutorial ini menyediakan panduan langkah demi langkah, mulai dari memuat dokumen hingga mengakses fragmen teks yang diekstrak. Kini Anda dapat memasukkan kode ini ke dalam proyek C# Anda sendiri untuk menganalisis dan memproses konten teks dalam file PDF.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial "Cari dan Dapatkan Semua Teks"?

J: Tutorial "Cari dan Dapatkan Semua Teks" menunjukkan cara memanfaatkan pustaka Aspose.PDF untuk .NET guna mencari dan mengekstrak teks dari semua halaman dokumen PDF. Tutorial ini menyediakan petunjuk langkah demi langkah beserta contoh kode C# untuk melakukan pencarian dan pengambilan teks.

#### T: Bagaimana tutorial ini membantu dalam mengekstrak teks dari dokumen PDF?

J: Tutorial ini memandu Anda melalui proses mengekstraksi teks dari semua halaman dokumen PDF. Tutorial ini menggunakan pustaka Aspose.PDF untuk menemukan frasa teks tertentu dan mengambil informasi terkait, seperti posisi, properti font, dan warna.

#### T: Apa saja prasyarat untuk mengikuti tutorial ini?

J: Sebelum memulai tutorial ini, Anda harus memiliki pemahaman dasar tentang bahasa pemrograman C#. Selain itu, Anda perlu menginstal pustaka Aspose.PDF for .NET. Anda dapat memperolehnya dari situs web Aspose atau menggunakan NuGet untuk mengintegrasikannya ke dalam proyek Anda.

#### T: Bagaimana cara menyiapkan proyek saya untuk mengikuti tutorial ini?

J: Untuk memulai, buat proyek C# baru di lingkungan pengembangan terpadu (IDE) pilihan Anda dan tambahkan referensi ke pustaka Aspose.PDF untuk .NET. Ini akan memungkinkan Anda mengakses fungsionalitas pustaka di proyek Anda.

#### T: Bagaimana cara mencari teks tertentu dalam dokumen PDF?

 A: Kamu bisa menggunakan`TextFragmentAbsorber`kelas untuk menemukan contoh frasa pencarian tertentu dalam dokumen PDF. Dengan membuat contoh kelas ini dan menentukan teks target, Anda dapat menangkap semua kemunculan teks tersebut.

#### T: Dapatkah saya mencari teks di semua halaman dokumen PDF?

 A: Ya, tutorial ini menunjukkan cara mencari teks di semua halaman dokumen PDF.`pdfDocument.Pages.Accept(textFragmentAbsorber)` metode ini digunakan untuk menerima penyerap untuk semua halaman, sehingga Anda dapat mencari teks yang diinginkan di setiap halaman.

#### T: Bagaimana cara mengakses fragmen teks yang diekstrak?

 A: Setelah mencari teks, Anda dapat mengakses fragmen teks yang diekstraksi menggunakan`TextFragments` milik`TextFragmentAbsorber` objek. Properti ini menyediakan akses ke koleksi`TextFragment` objek yang berisi teks yang diekstraksi dan informasi terkait.

#### T: Informasi apa yang dapat saya peroleh dari fragmen teks yang diekstrak?

A: Anda dapat mengambil berbagai detail dari fragmen teks yang diekstrak, seperti konten teks sebenarnya, posisi (koordinat X dan Y), informasi font (nama, ukuran, warna, dll.), dan banyak lagi. Kode contoh tutorial menunjukkan cara mengakses dan mencetak detail ini.

#### T: Dapatkah saya melakukan tindakan lebih lanjut pada fragmen teks yang diekstraksi?

A: Tentu saja. Setelah Anda memiliki fragmen teks yang diekstrak, Anda dapat memodifikasi kode dalam loop untuk melakukan tindakan khusus pada setiap fragmen. Ini dapat mencakup menyimpan teks yang diekstrak, menganalisis pola teks, atau menerapkan perubahan format.