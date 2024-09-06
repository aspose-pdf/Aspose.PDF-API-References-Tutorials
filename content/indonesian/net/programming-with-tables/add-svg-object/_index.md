---
title: Tambahkan Objek SVG Dalam File PDF
linktitle: Tambahkan Objek SVG Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Tambahkan objek SVG dalam berkas PDF dengan mudah menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 30
url: /id/net/programming-with-tables/add-svg-object/
---
Dalam tutorial ini, kita akan mempelajari cara menambahkan objek SVG dalam berkas PDF menggunakan pustaka Aspose.PDF for .NET. SVG (Scalable Vector Graphics) adalah format populer untuk grafik vektor yang dapat dengan mudah diskalakan tanpa kehilangan kualitas. Dengan Aspose.PDF, Anda dapat menambahkan objek SVG ke dokumen PDF Anda secara terprogram.

## Persyaratan

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

- Visual Studio terinstal
- Pustaka Aspose.PDF untuk .NET terinstal

## Langkah 1: Siapkan Lingkungan

Pertama, mari kita siapkan lingkungan dengan membuat proyek C# baru di Visual Studio. Buka Visual Studio dan ikuti langkah-langkah berikut:

1. Klik "File" > "Baru" > "Proyek" untuk membuat proyek baru.
2. Pilih templat "Aplikasi Konsol (.NET Framework)" atau "Aplikasi Konsol (.NET Core)", tergantung pada pengaturan Anda.
3. Pilih nama dan lokasi yang sesuai untuk proyek Anda, lalu klik "Buat."

## Langkah 2: Buat Objek Dokumen dan Gambar

Pada langkah ini, kita akan membuat objek yang diperlukan untuk dokumen PDF dan gambar SVG. Buka file C# proyek Anda dan tambahkan kode berikut:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Objek Dokumen Instan
Document doc = new Document();
// Buat contoh gambar
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Langkah 3: Mengatur Properti Gambar

Selanjutnya, kita akan mengatur properti untuk gambar SVG kita. Kita akan menentukan jenis file sebagai SVG, jalur ke file SVG, dan dimensi gambar. Tambahkan kode berikut setelah langkah sebelumnya:

```csharp
// Tetapkan jenis gambar sebagai SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Jalur untuk file sumber
img.File = dataDir + "SVGToPDF.svg";
// Atur lebar untuk contoh gambar
img. FixWidth = 50;
// Atur tinggi untuk contoh gambar
img.FixHeight = 50;
```

## Langkah 4: Membuat dan Mengonfigurasi Tabel

Sekarang, mari kita buat objek tabel dan atur lebar kolom. Kita akan membuat tabel dengan dua kolom, masing-masing dengan lebar 100 unit. Tambahkan kode berikut:

```csharp
// Buat tabel instance
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Mengatur lebar untuk sel tabel
table. ColumnWidths = "100 100";
```

## Langkah 5: Tambahkan Sel ke Tabel

Pada langkah ini, kita akan menambahkan baris dan sel ke dalam tabel. Setiap baris mewakili baris horizontal dalam tabel, dan sel ditambahkan ke baris tersebut. Tambahkan kode berikut:

```csharp
//Buat objek baris dan tambahkan ke instance tabel
Aspose.Pdf.Row row = table.Rows.Add();
// Buat objek sel dan tambahkan ke instance baris
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Langkah 6: Tambahkan Teks dan Gambar ke Sel

Selanjutnya, mari tambahkan teks dan gambar SVG ke sel-sel tabel. Kita akan menambahkan teks "Sel pertama" ke sel pertama dan gambar SVG ke sel kedua. Tambahkan kode berikut:

```csharp
// Tambahkan fragmen teks ke kumpulan paragraf objek sel
cell.Paragraphs.Add(new TextFragment("First cell"));
// Tambahkan sel lain ke objek baris
cell = row. Cells. Add();
// Tambahkan gambar SVG ke koleksi paragraf dari instans sel yang baru ditambahkan
cell.Paragraphs.Add(img);
```

## Langkah 7: Membuat dan Menambahkan Halaman ke Dokumen

Sekarang, mari kita buat objek halaman dan tambahkan ke dokumen. Tabel akan ditambahkan ke koleksi paragraf halaman. Tambahkan kode berikut:

```csharp
// Buat objek halaman dan tambahkan ke koleksi halaman dari instans dokumen
Page page = doc.Pages.Add();
// Tambahkan tabel ke kumpulan paragraf objek halaman
page.Paragraphs.Add(table);
```

## Langkah 8: Simpan File PDF

Terakhir, kita akan menyimpan berkas PDF ke lokasi yang ditentukan. Tambahkan kode berikut:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// Simpan file PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Contoh kode sumber untuk menambahkan objek SVG menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Membuat instance objek Dokumen
Document doc = new Document();
// Buat contoh gambar
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Tetapkan jenis gambar sebagai SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Jalur untuk file sumber
img.File = dataDir + "SVGToPDF.svg";
// Atur lebar untuk contoh gambar
img.FixWidth = 50;
// Atur tinggi untuk contoh gambar
img.FixHeight = 50;
// Buat contoh tabel
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Mengatur lebar untuk sel tabel
table.ColumnWidths = "100 100";
//Buat objek baris dan tambahkan ke instance tabel
Aspose.Pdf.Row row = table.Rows.Add();
// Buat objek sel dan tambahkan ke instance baris
Aspose.Pdf.Cell cell = row.Cells.Add();
// Tambahkan fragmen teks ke kumpulan paragraf objek sel
cell.Paragraphs.Add(new TextFragment("First cell"));
// Tambahkan sel lain ke objek baris
cell = row.Cells.Add();
// Tambahkan gambar SVG ke koleksi paragraf dari instans sel yang baru ditambahkan
cell.Paragraphs.Add(img);
// Buat objek halaman dan tambahkan ke koleksi halaman dari instans dokumen
Page page = doc.Pages.Add();
// Tambahkan tabel ke kumpulan paragraf objek halaman
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// Simpan file PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara menambahkan objek SVG ke berkas PDF menggunakan pustaka Aspose.PDF for .NET. Kita membahas proses langkah demi langkah untuk membuat dokumen, menyiapkan lingkungan, menambahkan gambar SVG ke sel tabel, dan menyimpan berkas PDF. Sekarang Anda dapat memasukkan objek SVG ke dalam dokumen PDF Anda secara terprogram.

### FAQ untuk menambahkan objek SVG dalam file PDF

#### T: Dapatkah saya menambahkan beberapa objek SVG ke dokumen PDF?

 A: Ya, Anda dapat menambahkan beberapa objek SVG ke dokumen PDF. Cukup buat dan konfigurasikan objek tambahan`Aspose.Pdf.Image` contoh untuk setiap gambar SVG yang ingin Anda tambahkan, lalu tambahkan ke sel tabel atau paragraf yang diinginkan dalam dokumen PDF.

#### T: Bagaimana cara menyesuaikan ukuran dan posisi gambar SVG di sel tabel?

 A: Untuk menyesuaikan ukuran dan posisi gambar SVG di sel tabel, Anda dapat memodifikasi`FixWidth` Dan`FixHeight` properti dari`Aspose.Pdf.Image`contohnya. Anda juga dapat menggunakan properti lain seperti`HorizontalAlignment` Dan`VerticalAlignment` sel tabel untuk mengontrol pemosisian.

#### T: Apakah mungkin untuk menambahkan teks di samping gambar SVG di sel tabel yang sama?

 A: Ya, Anda dapat menambahkan teks di samping gambar SVG di sel tabel yang sama. Anda dapat menggunakan`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` metode untuk menambahkan teks ke sel bersama dengan gambar SVG.

#### T: Dapatkah saya menambahkan hyperlink ke gambar SVG?

 A: Ya, Anda dapat menambahkan hyperlink ke gambar SVG dengan menggunakan`Hyperlink` milik`Aspose.Pdf.Image` Misalnya. Tetapkan URL hyperlink atau tindakan untuk membuat gambar dapat diklik.

#### T: Apakah Aspose.PDF untuk .NET kompatibel dengan .NET Core 3.1 atau versi yang lebih baru?

A: Ya, Aspose.PDF untuk .NET kompatibel dengan .NET Core 3.1 dan versi yang lebih baru. Anda dapat menggunakannya di aplikasi .NET Framework dan .NET Core.