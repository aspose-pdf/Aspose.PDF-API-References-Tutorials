---
title: Margin atau Padding
linktitle: Margin atau Padding
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengatur margin atau padding dalam tabel menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 140
url: /id/net/programming-with-tables/margins-or-padding/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah penggunaan Aspose.PDF for .NET untuk mengatur margin atau padding dalam tabel. Kami akan memberikan penjelasan dan cuplikan kode untuk membantu Anda memahami dan menerapkan fungsi ini dalam kode sumber C# Anda.

## Langkah 1: Menyiapkan Dokumen dan Halaman
Untuk memulai, Anda perlu menyiapkan dokumen dan halaman menggunakan kode berikut:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat instance objek Dokumen dengan memanggil konstruktor kosongnya
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Langkah 2: Membuat Tabel
Berikutnya, kita akan membuat objek tabel menggunakan kelas Aspose.Pdf.Table:

```csharp
// Membuat instance objek tabel
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Tambahkan tabel ke koleksi paragraf bagian yang diinginkan
page.Paragraphs.Add(tab1);
```

## Langkah 3: Mengatur Lebar Kolom dan Batas Sel Default
Untuk mengatur lebar kolom dan batas sel default tabel, gunakan kode berikut:

```csharp
// Mengatur lebar kolom tabel
tab1. ColumnWidths = "50 50 50";
// Tetapkan batas sel default menggunakan objek BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Langkah 4: Mengatur Batas Tabel dan Pengisi Sel
Untuk mengatur batas tabel dan pengisi sel, buat objek MarginInfo dan atur propertinya:

```csharp
// Buat objek MarginInfo dan atur margin kiri, bawah, kanan, dan atasnya
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Tetapkan bantalan sel default ke objek MarginInfo
tab1. DefaultCellPadding = margin;

// Tetapkan batas tabel menggunakan objek BorderInfo lain yang disesuaikan
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Langkah 5: Menambahkan Baris dan Sel
Sekarang, mari tambahkan baris dan sel ke tabel. Kita akan membuat baris baru dan menambahkan sel ke dalamnya:

```csharp
// Buat baris dalam tabel dan kemudian sel dalam baris
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## Langkah 6: Menambahkan Teks ke Sel
Untuk menambahkan teks ke sel, buat objek TextFragment dan tambahkan ke sel yang diinginkan:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## Langkah 7: Menyimpan PDF
Untuk menyimpan dokumen PDF, gunakan kode berikut:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Simpan PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Contoh kode sumber untuk Margin atau Padding menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat objek Dokumen dengan memanggil konstruktor kosongnya
Document doc = new Document();
Page page = doc.Pages.Add();
// Membuat instance objek tabel
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Tambahkan tabel dalam kumpulan paragraf bagian yang diinginkan
page.Paragraphs.Add(tab1);
// Diatur dengan lebar kolom tabel
tab1.ColumnWidths = "50 50 50";
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
// Buat baris dalam tabel dan kemudian sel dalam baris
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 dengan string teks besar yang akan ditempatkan di dalam sel");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Baris1.Sel[2].Paragraf[0].LebarTetap= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Simpan PDFnya
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengatur margin atau padding dalam tabel menggunakan Aspose.PDF untuk .NET. Pengetahuan ini akan membantu Anda meningkatkan kemampuan pemformatan dokumen dan membuat tabel Anda menarik secara visual.

### Pertanyaan yang Sering Diajukan

#### T: Dapatkah saya mengatur margin atau padding yang berbeda untuk sel individual dalam sebuah tabel?

A: Ya, Anda dapat mengatur margin atau padding yang berbeda untuk sel-sel individual dalam tabel menggunakan Aspose.PDF untuk .NET. Dalam contoh yang diberikan, kami mengatur padding sel default untuk seluruh tabel menggunakan`DefaultCellPadding` properti. Untuk mengatur bantalan yang berbeda untuk sel tertentu, Anda dapat mengakses`MarginInfo` setiap sel secara individual dan memodifikasi marginnya.

#### T: Bagaimana cara mengubah warna atau gaya batas tabel?

 A: Untuk mengubah warna atau gaya batas tabel, Anda dapat memodifikasi`Color` Dan`Width` properti dari`BorderInfo` objek. Dalam contoh yang diberikan, kami mengatur warna perbatasan menjadi hitam dan lebar 1F (satu titik) menggunakan`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`Anda dapat menyesuaikan warna dan lebar sesuai kebutuhan Anda.

#### T: Apakah mungkin untuk menambahkan header atau footer ke tabel?

J: Ya, Anda dapat menambahkan header atau footer ke tabel menggunakan Aspose.PDF untuk .NET. Header dan footer biasanya berupa baris terpisah yang berisi informasi tambahan seperti label kolom, judul tabel, atau data ringkasan. Anda dapat membuat baris tambahan, menatanya secara berbeda, dan menambahkannya di atas atau di bawah konten tabel.

#### T: Bagaimana cara menyesuaikan perataan teks dalam sel tabel?

 A: Untuk menyesuaikan perataan teks dalam sel tabel, Anda dapat menggunakan`HorizontalAlignment` Dan`VerticalAlignment` properti dari`TextFragment` objek. Misalnya, untuk meratakan teks secara horizontal di tengah, Anda dapat mengatur`mytext.HorizontalAlignment = HorizontalAlignment.Center;` Demikian pula, Anda dapat mengatur`mytext.VerticalAlignment` untuk mengontrol penyelarasan vertikal.

#### T: Bisakah saya menambahkan gambar ke sel tabel, bukan teks?

 A: Ya, Anda dapat menambahkan gambar ke sel tabel menggunakan Aspose.PDF untuk .NET. Daripada membuat`TextFragment` objek, Anda dapat membuat`Image` objek, memuat file gambar, dan menambahkannya ke sel yang diinginkan menggunakan`cell.Paragraphs.Add(image);` metode ini. Ini memungkinkan Anda untuk memasukkan gambar ke dalam tabel di samping konten teks.