---
title: Tambahkan Objek SVG Dalam File PDF
linktitle: Tambahkan Objek SVG Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Tambahkan objek SVG dengan mudah dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 30
url: /id/net/programming-with-tables/add-svg-object/
---
Dalam tutorial ini, kita akan mempelajari cara menambahkan objek SVG dalam file PDF menggunakan perpustakaan Aspose.PDF untuk .NET. SVG (Scalable Vector Graphics) adalah format populer untuk grafik vektor yang dapat dengan mudah diskalakan tanpa kehilangan kualitas. Dengan Aspose.PDF, Anda dapat menambahkan objek SVG ke dokumen PDF Anda secara terprogram.

## Persyaratan

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

- Visual Studio diinstal
- Aspose.PDF untuk perpustakaan .NET diinstal

## Langkah 1: Siapkan Lingkungan

Pertama, mari kita siapkan lingkungan dengan membuat proyek C# baru di Visual Studio. Buka Visual Studio dan ikuti langkah-langkah berikut:

1. Klik "File" > "Baru" > "Proyek" untuk membuat proyek baru.
2. Pilih template "Aplikasi Konsol (.NET Framework)" atau "Aplikasi Konsol (.NET Core)", bergantung pada pengaturan Anda.
3. Pilih nama dan lokasi yang sesuai untuk proyek Anda, lalu klik "Buat".

## Langkah 2: Buat Objek Dokumen dan Gambar

Pada langkah ini, kita akan membuat objek yang diperlukan untuk dokumen PDF dan gambar SVG kita. Buka file C# proyek Anda dan tambahkan kode berikut:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Objek Dokumen Instan
Document doc = new Document();
// Buat contoh gambar
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Langkah 3: Atur Properti Gambar

Selanjutnya, kita akan mengatur properti untuk gambar SVG kita. Kami akan menentukan jenis file sebagai SVG, jalur ke file SVG, dan dimensi gambar. Tambahkan kode berikut setelah langkah sebelumnya:

```csharp
// Tetapkan jenis gambar sebagai SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Jalur untuk file sumber
img.File = dataDir + "SVGToPDF.svg";
// Tetapkan lebar untuk contoh gambar
img. FixWidth = 50;
// Tetapkan ketinggian untuk contoh gambar
img.FixHeight = 50;
```

## Langkah 4: Buat dan Konfigurasikan Tabel

Sekarang, mari buat objek tabel dan atur lebar kolomnya. Kita akan membuat tabel dengan dua kolom yang masing-masing lebarnya 100 satuan. Tambahkan kode berikut:

```csharp
// Buat tabel contoh
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Tetapkan lebar untuk sel tabel
table. ColumnWidths = "100 100";
```

## Langkah 5: Tambahkan Sel ke Tabel

Pada langkah ini, kita akan menambahkan baris dan sel ke tabel. Setiap baris mewakili baris horizontal dalam tabel, dan sel ditambahkan ke baris tersebut. Tambahkan kode berikut:

```csharp
//Buat objek baris dan tambahkan ke instance tabel
Aspose.Pdf.Row row = table.Rows.Add();
// Buat objek sel dan tambahkan ke instance baris
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Langkah 6: Tambahkan Teks dan Gambar ke Sel

Selanjutnya, mari tambahkan teks dan gambar SVG ke sel tabel. Kami akan menambahkan teks "Sel pertama" ke sel pertama dan gambar SVG ke sel kedua. Tambahkan kode berikut:

```csharp
// Tambahkan fragmen teks ke kumpulan paragraf objek sel
cell.Paragraphs.Add(new TextFragment("First cell"));
// Tambahkan sel lain ke objek baris
cell = row. Cells. Add();
// Tambahkan gambar SVG ke kumpulan paragraf dari contoh sel yang baru ditambahkan
cell.Paragraphs.Add(img);
```

## Langkah 7: Buat dan Tambahkan Halaman ke Dokumen

Sekarang, mari buat objek halaman dan tambahkan ke dokumen. Tabel akan ditambahkan ke kumpulan paragraf halaman. Tambahkan kode berikut:

```csharp
// Buat objek halaman dan tambahkan ke kumpulan halaman contoh dokumen
Page page = doc.Pages.Add();
// Tambahkan tabel ke kumpulan paragraf objek halaman
page.Paragraphs.Add(table);
```

## Langkah 8: Simpan File PDF

Terakhir, kami akan menyimpan file PDF ke lokasi yang ditentukan. Tambahkan kode berikut:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// Simpan berkas PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Contoh kode sumber untuk menambahkan objek SVG menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat instance objek Dokumen
Document doc = new Document();
// Buat contoh gambar
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Tetapkan jenis gambar sebagai SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Jalur untuk file sumber
img.File = dataDir + "SVGToPDF.svg";
// Tetapkan lebar untuk contoh gambar
img.FixWidth = 50;
// Tetapkan ketinggian untuk contoh gambar
img.FixHeight = 50;
// Buat contoh tabel
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Tetapkan lebar untuk sel tabel
table.ColumnWidths = "100 100";
//Buat objek baris dan tambahkan ke instance tabel
Aspose.Pdf.Row row = table.Rows.Add();
// Buat objek sel dan tambahkan ke instance baris
Aspose.Pdf.Cell cell = row.Cells.Add();
// Tambahkan fragmen teks ke kumpulan paragraf objek sel
cell.Paragraphs.Add(new TextFragment("First cell"));
// Tambahkan sel lain ke objek baris
cell = row.Cells.Add();
// Tambahkan gambar SVG ke kumpulan paragraf dari contoh sel yang baru ditambahkan
cell.Paragraphs.Add(img);
// Buat objek halaman dan tambahkan ke kumpulan halaman contoh dokumen
Page page = doc.Pages.Add();
// Tambahkan tabel ke kumpulan paragraf objek halaman
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// Simpan berkas PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara menambahkan objek SVG ke file PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Kami membahas proses langkah demi langkah dalam membuat dokumen, menyiapkan lingkungan, menambahkan gambar SVG ke sel tabel, dan menyimpan file PDF. Sekarang Anda dapat memasukkan objek SVG ke dalam dokumen PDF Anda secara terprogram.

### FAQ untuk menambahkan objek SVG dalam file PDF

#### T: Dapatkah saya menambahkan beberapa objek SVG ke dokumen PDF?

 J: Ya, Anda dapat menambahkan beberapa objek SVG ke dokumen PDF. Cukup buat dan konfigurasikan tambahan`Aspose.Pdf.Image` contoh untuk setiap gambar SVG yang ingin Anda tambahkan dan kemudian tambahkan ke sel tabel atau paragraf yang diinginkan dalam dokumen PDF.

#### T: Bagaimana cara menyesuaikan ukuran dan posisi gambar SVG di sel tabel?

 A: Untuk mengatur ukuran dan posisi gambar SVG di sel tabel, Anda dapat memodifikasi`FixWidth` Dan`FixHeight` properti dari`Aspose.Pdf.Image`contoh. Anda juga dapat menggunakan properti lain seperti`HorizontalAlignment` Dan`VerticalAlignment` sel tabel untuk mengontrol posisi.

#### T: Apakah mungkin menambahkan teks di samping gambar SVG di sel tabel yang sama?

 J: Ya, dimungkinkan untuk menambahkan teks di samping gambar SVG di sel tabel yang sama. Anda dapat menggunakan`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` metode untuk menambahkan teks ke sel bersama dengan gambar SVG.

#### T: Dapatkah saya menambahkan hyperlink ke gambar SVG?

 J: Ya, Anda dapat menambahkan hyperlink ke gambar SVG dengan menggunakan`Hyperlink` properti dari`Aspose.Pdf.Image` contoh. Tetapkan URL hyperlink atau tindakan agar gambar dapat diklik.

#### T: Apakah Aspose.PDF untuk .NET kompatibel dengan .NET Core 3.1 atau versi yang lebih baru?

J: Ya, Aspose.PDF untuk .NET kompatibel dengan .NET Core 3.1 dan versi yang lebih baru. Anda dapat menggunakannya di aplikasi .NET Framework dan .NET Core.