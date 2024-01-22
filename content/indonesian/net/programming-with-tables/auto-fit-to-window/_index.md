---
title: Pas Otomatis Ke Jendela
linktitle: Pas Otomatis Ke Jendela
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk menggunakan Aspose.PDF untuk .NET dan mencapai penyesuaian otomatis ke jendela dalam pembuatan PDF.
type: docs
weight: 50
url: /id/net/programming-with-tables/auto-fit-to-window/
---
Artikel berikut adalah panduan langkah demi langkah tentang cara menggunakan kode sumber C# yang disediakan untuk mencapai fungsionalitas Auto Fit To Window menggunakan pustaka Aspose.PDF untuk .NET. Fungsi Auto Fit To Window memungkinkan Anda menghasilkan file PDF dengan tata letak yang disesuaikan dengan jendela tampilan. Fitur ini sangat berguna ketika Anda ingin dokumen PDF Anda secara otomatis menyesuaikan dengan ukuran jendela pembaca PDF yang digunakan oleh pengguna.

## Langkah 1: Menyiapkan Lingkungan

Sebelum memulai, Anda perlu menginstal perpustakaan Aspose.PDF untuk .NET di mesin Anda. Pastikan juga untuk mengimpor namespace yang diperlukan ke dalam proyek Anda.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Membuat Dokumen PDF

 Untuk memulai, Anda perlu membuat`Document` objek dengan memanggil konstruktor defaultnya.

```csharp
Document doc = new Document();
```

 Selanjutnya, buat bagian di`Pdf` obyek.

```csharp
Page sec1 = doc.Pages.Add();
```

## Langkah 3: Menambahkan Tabel ke Dokumen

 Pada langkah ini, kita akan menambahkan tabel ke dokumen PDF kita. Pertama buat a`Table` obyek.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Selanjutnya, tambahkan tabel ke kumpulan paragraf bagian tersebut.

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

### Contoh kode sumber untuk Auto Fit To Window menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat instance objek Pdf dengan memanggil konstruktor kosongnya
Document doc = new Document();
// Buat bagian di objek Pdf
Page sec1 = doc.Pages.Add();

// Buat instance objek tabel
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Tambahkan tabel dalam kumpulan paragraf dari bagian yang diinginkan
sec1.Paragraphs.Add(tab1);

// Atur dengan lebar kolom tabel
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// Tetapkan batas sel default menggunakan objek BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Tetapkan batas tabel menggunakan objek BorderInfo khusus lainnya
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Buat objek MarginInfo dan atur margin kiri, bawah, kanan dan atas
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Atur padding sel default ke objek MarginInfo
tab1.DefaultCellPadding = margin;

// Buat baris dalam tabel dan kemudian sel dalam baris
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Simpan dokumen terbaru yang berisi objek tabel
doc.Save(dataDir);
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menggunakan Aspose.PDF untuk .NET untuk menghasilkan file PDF dengan fitur Auto Fit To Window. Fitur ini sangat berguna ketika Anda ingin dokumen PDF Anda secara otomatis menyesuaikan dengan ukuran jendela tampilan. Aspose.PDF untuk .NET menawarkan banyak fitur canggih lainnya untuk menghasilkan dan memanipulasi file PDF. Saya mendorong Anda untuk menjelajahi perpustakaan ini lebih jauh untuk menemukan semua kemampuannya.

### FAQ

#### Q: Apa tujuan fitur Auto Fit To Window dalam pembuatan PDF?

A: Fitur Auto Fit To Window pada pembuatan PDF memastikan tata letak dokumen PDF secara otomatis menyesuaikan dengan ukuran jendela pembaca PDF yang digunakan pengguna. Hal ini memungkinkan tampilan yang lebih baik dan memastikan konten pas dengan area tampilan yang tersedia.

#### T: Dapatkah saya menyesuaikan tampilan tabel, seperti ukuran font dan warna?

A: Ya, Anda dapat menyesuaikan tampilan tabel di dokumen PDF menggunakan Aspose.PDF untuk .NET. Cuplikan kode yang disediakan menunjukkan cara mengatur properti seperti batas sel, margin, dan lebar kolom. Anda dapat menyesuaikan lebih lanjut ukuran font, warna, dan aspek gaya lainnya pada tabel dan kontennya.

#### T: Bagaimana cara mengintegrasikan Aspose.PDF untuk .NET ke dalam proyek C# saya?

J: Untuk menggunakan Aspose.PDF untuk .NET di proyek C# Anda, Anda harus terlebih dahulu menginstal perpustakaan Aspose.PDF untuk .NET di mesin Anda. Kemudian, Anda dapat menambahkan referensi ke perpustakaan di proyek C# Anda. Terakhir, impor namespace yang diperlukan untuk mengakses kelas dan metode yang disediakan oleh Aspose.PDF untuk .NET.

#### T: Apakah Aspose.PDF untuk .NET kompatibel dengan aplikasi .NET Core?

J: Ya, Aspose.PDF untuk .NET kompatibel dengan aplikasi .NET Core. Ini mendukung berbagai platform .NET, termasuk .NET Framework, .NET Core, dan .NET 5.0+.

#### T: Dapatkah saya menambahkan lebih banyak tabel ke dokumen PDF?

J: Ya, Anda dapat menambahkan beberapa tabel ke dokumen PDF dengan mengikuti langkah serupa seperti yang ditunjukkan dalam cuplikan kode. Cukup buat instance baru dari`Aspose.Pdf.Table` kelas dan menambahkannya ke bagian atau halaman berbeda dari dokumen PDF.