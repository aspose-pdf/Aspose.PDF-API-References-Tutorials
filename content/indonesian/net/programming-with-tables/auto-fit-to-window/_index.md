---
title: Sesuaikan Otomatis ke Jendela
linktitle: Sesuaikan Otomatis ke Jendela
second_title: Referensi API Aspose.PDF untuk .NET
description: Panduan langkah demi langkah untuk menggunakan Aspose.PDF untuk .NET dan mencapai kesesuaian otomatis dengan jendela dalam pembuatan PDF.
type: docs
weight: 50
url: /id/net/programming-with-tables/auto-fit-to-window/
---
Artikel berikut adalah panduan langkah demi langkah tentang cara menggunakan kode sumber C# yang disediakan untuk mencapai fungsi Penyesuaian Otomatis ke Jendela menggunakan pustaka Aspose.PDF untuk .NET. Fungsi Penyesuaian Otomatis ke Jendela memungkinkan Anda membuat berkas PDF dengan tata letak yang disesuaikan dengan jendela tampilan. Fitur ini khususnya berguna ketika Anda ingin dokumen PDF Anda secara otomatis menyesuaikan dengan ukuran jendela pembaca PDF yang digunakan oleh pengguna.

## Langkah 1: Menyiapkan Lingkungan

Sebelum memulai, Anda perlu menginstal pustaka Aspose.PDF untuk .NET di komputer Anda. Pastikan juga untuk mengimpor namespace yang diperlukan ke dalam proyek Anda.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Membuat Dokumen PDF

 Untuk memulai, Anda perlu membuat`Document` objek dengan memanggil konstruktor default-nya.

```csharp
Document doc = new Document();
```

 Selanjutnya, buat bagian di`Pdf` obyek.

```csharp
Page sec1 = doc.Pages.Add();
```

## Langkah 3: Menambahkan Tabel ke Dokumen

 Pada langkah ini, kita akan menambahkan tabel ke dokumen PDF kita. Pertama buat tabel`Table` obyek.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Berikutnya, tambahkan tabel ke kumpulan paragraf bagian tersebut.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Langkah 4: Menyesuaikan Tampilan Tabel

Anda dapat menyesuaikan tampilan tabel dengan mengatur properti seperti batas sel dan margin.

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  Langkah 4: Menambahkan Baris dan Sel ke Tabel

Sekarang mari tambahkan baris dan sel ke tabel kita. Mulailah dengan membuat baris dan menambahkan sel ke baris tersebut.

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## Langkah 5: Menyimpan Dokumen

Terakhir, tentukan jalur file keluaran dan simpan dokumen.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Contoh kode sumber untuk Penyesuaian Otomatis ke Jendela menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat objek Pdf dengan memanggil konstruktor kosongnya
Document doc = new Document();
// Buat bagian dalam objek Pdf
Page sec1 = doc.Pages.Add();

// Membuat instance objek tabel
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Tambahkan tabel dalam kumpulan paragraf bagian yang diinginkan
sec1.Paragraphs.Add(tab1);

// Diatur dengan lebar kolom tabel
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// Mengatur batas sel default menggunakan objek BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Tetapkan batas tabel menggunakan objek BorderInfo lain yang disesuaikan
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Buat objek MarginInfo dan atur margin kiri, bawah, kanan dan atasnya
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Tetapkan bantalan sel default ke objek MarginInfo
tab1.DefaultCellPadding = margin;

//Buat baris dalam tabel dan kemudian sel dalam baris
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Simpan dokumen yang diperbarui yang berisi objek tabel
doc.Save(dataDir);
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menggunakan Aspose.PDF for .NET untuk membuat file PDF dengan fitur Auto Fit To Window. Fitur ini sangat berguna ketika Anda ingin dokumen PDF Anda secara otomatis menyesuaikan dengan ukuran jendela tampilan. Aspose.PDF for .NET menawarkan banyak fitur hebat lainnya untuk membuat dan memanipulasi file PDF. Saya menganjurkan Anda untuk menjelajahi pustaka ini lebih lanjut untuk menemukan semua kemampuannya.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan fitur Sesuaikan Otomatis ke Jendela dalam pembuatan PDF?

A: Fitur Auto Fit To Window dalam pembuatan PDF memastikan bahwa tata letak dokumen PDF secara otomatis menyesuaikan dengan ukuran jendela pembaca PDF yang digunakan oleh pengguna. Hal ini memungkinkan tampilan yang lebih baik dan memastikan bahwa kontennya pas dengan area tampilan yang tersedia.

#### T: Dapatkah saya menyesuaikan tampilan tabel, seperti ukuran font dan warna?

A: Ya, Anda dapat menyesuaikan tampilan tabel dalam dokumen PDF menggunakan Aspose.PDF for .NET. Cuplikan kode yang diberikan menunjukkan cara mengatur properti seperti batas sel, margin, dan lebar kolom. Anda dapat menyesuaikan lebih lanjut ukuran font, warna, dan aspek gaya lainnya pada tabel dan kontennya.

#### T: Bagaimana cara mengintegrasikan Aspose.PDF untuk .NET ke dalam proyek C# saya?

J: Untuk menggunakan Aspose.PDF for .NET dalam proyek C# Anda, pertama-tama Anda perlu menginstal pustaka Aspose.PDF for .NET pada komputer Anda. Kemudian, Anda dapat menambahkan referensi ke pustaka tersebut dalam proyek C# Anda. Terakhir, impor namespace yang diperlukan untuk mengakses kelas dan metode yang disediakan oleh Aspose.PDF for .NET.

#### T: Apakah Aspose.PDF untuk .NET kompatibel dengan aplikasi .NET Core?

A: Ya, Aspose.PDF untuk .NET kompatibel dengan aplikasi .NET Core. Aplikasi ini mendukung berbagai platform .NET, termasuk .NET Framework, .NET Core, dan .NET 5.0+.

#### T: Dapatkah saya menambahkan lebih banyak tabel ke dokumen PDF?

A: Ya, Anda dapat menambahkan beberapa tabel ke dokumen PDF dengan mengikuti langkah-langkah serupa seperti yang ditunjukkan dalam cuplikan kode. Cukup buat contoh baru dari`Aspose.Pdf.Table` kelas dan menambahkannya ke bagian atau halaman berbeda dari dokumen PDF.