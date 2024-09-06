---
title: Cari Ekspresi Reguler Dalam File PDF
linktitle: Cari Ekspresi Reguler Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mencari dan mengambil teks menggunakan ekspresi reguler dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 440
url: /id/net/programming-with-text/search-regular-expression/
---
Tutorial ini menjelaskan cara menggunakan Aspose.PDF untuk .NET guna mencari dan mengambil teks yang cocok dengan ekspresi reguler dalam berkas PDF. Kode sumber C# yang disediakan menunjukkan proses tersebut langkah demi langkah.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Pastikan untuk mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 4: Pencarian dengan ekspresi reguler

 Membuat sebuah`TextFragmentAbsorber` objek dan atur pola ekspresi reguler untuk menemukan semua frasa yang cocok dengan pola:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Seperti tahun 1999-2000
```

 Mengganti`"\\d{4}-\\d{4}"` dengan pola ekspresi reguler yang Anda inginkan.

## Langkah 5: Tetapkan opsi pencarian teks

 Membuat sebuah`TextSearchOptions` objek dan mengaturnya ke`TextSearchOptions` milik`TextFragmentAbsorber` objek untuk mengaktifkan penggunaan ekspresi reguler:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Langkah 6: Cari di semua halaman

Terima penyerap untuk semua halaman dokumen:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Langkah 7: Ambil fragmen teks yang diekstraksi

Dapatkan fragmen teks yang diekstraksi menggunakan`TextFragments` milik`TextFragmentAbsorber` obyek:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Langkah 8: Ulangi melalui fragmen teks

Ulangi fragmen teks yang diambil dan akses propertinya:

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

### Contoh kode sumber untuk Pencarian Ekspresi Reguler menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Buat objek TextAbsorber untuk menemukan semua frasa yang cocok dengan ekspresi reguler
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Seperti tahun 1999-2000
// Tetapkan opsi pencarian teks untuk menentukan penggunaan ekspresi reguler
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

Selamat! Anda telah berhasil mempelajari cara mencari dan mengambil teks yang cocok dengan ekspresi reguler dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Tutorial ini menyediakan panduan langkah demi langkah, mulai dari memuat dokumen hingga mengakses fragmen teks yang diekstrak. Anda sekarang dapat memasukkan kode ini ke dalam proyek C# Anda sendiri untuk melakukan pencarian teks tingkat lanjut dalam file PDF.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial "Pencarian Ekspresi Reguler Dalam Berkas PDF"?

J: Tutorial "Search Regular Expression In PDF File" bertujuan untuk menunjukkan cara menggunakan pustaka Aspose.PDF untuk .NET guna mencari dan mengekstrak teks yang cocok dengan pola ekspresi reguler tertentu dalam file PDF. Tutorial ini menyediakan panduan lengkap dan contoh kode C# untuk menunjukkan prosesnya.

#### T: Bagaimana tutorial ini membantu dalam pencarian teks menggunakan ekspresi reguler dalam dokumen PDF?

J: Tutorial ini menyediakan pendekatan langkah demi langkah untuk menggunakan pustaka Aspose.PDF guna melakukan pencarian teks dalam dokumen PDF berdasarkan pola ekspresi reguler. Tutorial ini merinci cara menyiapkan proyek, memuat dokumen PDF, menentukan pola ekspresi reguler, dan mengambil fragmen teks yang cocok.

#### T: Apa saja prasyarat untuk mengikuti tutorial ini?

J: Sebelum memulai tutorial ini, Anda harus memiliki pemahaman dasar tentang bahasa pemrograman C#. Selain itu, Anda perlu menginstal pustaka Aspose.PDF for .NET. Anda dapat memperolehnya dari situs web Aspose atau menggunakan NuGet untuk mengintegrasikannya ke dalam proyek Anda.

#### T: Bagaimana cara menyiapkan proyek saya untuk mengikuti tutorial ini?

J: Untuk memulai, buat proyek C# baru di lingkungan pengembangan terpadu (IDE) pilihan Anda dan tambahkan referensi ke pustaka Aspose.PDF untuk .NET. Ini akan memungkinkan Anda memanfaatkan kemampuan pustaka dalam proyek Anda.

#### T: Dapatkah saya menggunakan ekspresi reguler untuk mencari teks dalam dokumen PDF?

 A: Ya, tutorial ini menunjukkan cara menggunakan ekspresi reguler untuk mencari dan mengekstrak teks dari dokumen PDF. Tutorial ini melibatkan penggunaan ekspresi reguler`TextFragmentAbsorber` kelas dan menentukan pola ekspresi reguler untuk menemukan frasa yang cocok dengan pola yang disediakan.

#### T: Bagaimana cara menentukan pola ekspresi reguler untuk pencarian teks?

 A: Untuk menentukan pola ekspresi reguler untuk pencarian teks, buatlah`TextFragmentAbsorber` objek dan mengatur polanya menggunakan`Text` parameter. Ganti pola default`"\\d{4}-\\d{4}"` dalam kode tutorial dengan pola ekspresi reguler yang Anda inginkan.

#### T: Bagaimana cara mengaktifkan penggunaan ekspresi reguler untuk pencarian teks?

 A: Penggunaan ekspresi reguler diaktifkan dengan membuat`TextSearchOptions` objek dan mengatur nilainya ke`true` . Tetapkan objek ini ke`TextSearchOptions` milik`TextFragmentAbsorber` contoh. Ini memastikan bahwa pola ekspresi reguler diterapkan selama pencarian teks.

#### T: Dapatkah saya mengambil fragmen teks yang cocok dengan pola ekspresi reguler?

 A: Tentu saja. Setelah menerapkan pencarian ekspresi reguler pada dokumen PDF, Anda dapat mengambil fragmen teks yang diekstrak menggunakan`TextFragments` milik`TextFragmentAbsorber` objek. Fragmen teks ini berisi segmen teks yang sesuai dengan pola ekspresi reguler yang ditentukan.

#### T: Apa yang dapat saya akses dari fragmen teks yang diambil?

A: Dari fragmen teks yang diambil, Anda dapat mengakses berbagai properti seperti konten teks yang cocok, posisi (koordinat X dan Y), informasi font (nama, ukuran, warna), dan banyak lagi. Kode contoh dalam loop tutorial menunjukkan cara mengakses dan menampilkan properti ini.

#### T: Bagaimana saya dapat menyesuaikan tindakan pada fragmen teks yang diekstraksi?

J: Setelah Anda memiliki fragmen teks yang diekstrak, Anda dapat menyesuaikan kode dalam loop untuk melakukan tindakan tambahan pada setiap fragmen teks. Ini dapat mencakup menyimpan teks yang diekstrak, menganalisis pola, atau menerapkan perubahan format berdasarkan kebutuhan Anda.