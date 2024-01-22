---
title: Margin Atau Padding
linktitle: Margin Atau Padding
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengatur margin atau padding dalam tabel menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 140
url: /id/net/programming-with-tables/margins-or-padding/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah menggunakan Aspose.PDF untuk .NET untuk mengatur margin atau padding dalam sebuah tabel. Kami akan memberikan penjelasan dan cuplikan kode untuk membantu Anda memahami dan menerapkan fungsi ini dalam kode sumber C# Anda.

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
Selanjutnya, kita akan membuat objek tabel menggunakan kelas Aspose.Pdf.Table:

```csharp
// Buat instance objek tabel
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Tambahkan tabel ke kumpulan paragraf di bagian yang diinginkan
page.Paragraphs.Add(tab1);
```

## Langkah 3: Mengatur Lebar Kolom dan Batas Sel Default
Untuk mengatur lebar kolom dan batas sel default tabel, gunakan kode berikut:

```csharp
// Atur lebar kolom tabel
tab1. ColumnWidths = "50 50 50";
// Atur batas sel default menggunakan objek BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Langkah 4: Mengatur Batas Tabel dan Bantalan Sel
Untuk mengatur batas tabel dan padding sel, buat objek MarginInfo dan atur propertinya:

```csharp
// Buat objek MarginInfo dan atur margin kiri, bawah, kanan, dan atas
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Atur padding sel default ke objek MarginInfo
tab1. DefaultCellPadding = margin;

// Atur batas tabel menggunakan objek BorderInfo kustom lainnya
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Langkah 5: Menambahkan Baris dan Sel
Sekarang, mari tambahkan baris dan sel ke tabel. Kami akan membuat baris baru dan menambahkan sel ke dalamnya:

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
// Simpan PDFnya
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Contoh kode sumber untuk Margin atau Padding menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat instance objek Dokumen dengan memanggil konstruktor kosongnya
Document doc = new Document();
Page page = doc.Pages.Add();
// Buat instance objek tabel
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Tambahkan tabel dalam kumpulan paragraf dari bagian yang diinginkan
page.Paragraphs.Add(tab1);
// Atur dengan lebar kolom tabel
tab1.ColumnWidths = "50 50 50";
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
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 dengan string teks besar untuk ditempatkan di dalam sel");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Baris1.Sel[2].Paragraf[0].Lebar Tetap= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Simpan Pdfnya
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengatur margin atau padding dalam tabel menggunakan Aspose.PDF untuk .NET. Pengetahuan ini akan membantu Anda meningkatkan kemampuan pemformatan dokumen dan membuat tabel Anda menarik secara visual.

### FAQ

#### T: Bisakah saya mengatur margin atau padding yang berbeda untuk masing-masing sel dalam tabel?

J: Ya, Anda dapat mengatur margin atau padding yang berbeda untuk masing-masing sel dalam tabel menggunakan Aspose.PDF untuk .NET. Dalam contoh yang diberikan, kami menetapkan padding sel default untuk seluruh tabel menggunakan`DefaultCellPadding` Properti. Untuk mengatur padding berbeda untuk sel tertentu, Anda dapat mengakses`MarginInfo` setiap sel satu per satu dan ubah marginnya.

#### T: Bagaimana cara mengubah warna atau gaya tepi tabel?

 A: Untuk mengubah warna atau gaya tepi tabel, Anda dapat memodifikasinya`Color` Dan`Width` properti dari`BorderInfo` obyek. Dalam contoh yang diberikan, kita mengatur warna batas menjadi hitam dan lebar 1F (satu titik) menggunakan`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. Anda dapat menyesuaikan warna dan lebar sesuai kebutuhan Anda.

#### T: Apakah mungkin menambahkan header atau footer ke tabel?

J: Ya, Anda dapat menambahkan header atau footer ke tabel menggunakan Aspose.PDF untuk .NET. Header dan footer biasanya merupakan baris terpisah yang berisi informasi tambahan seperti label kolom, judul tabel, atau data ringkasan. Anda dapat membuat baris tambahan, menatanya secara berbeda, dan menambahkannya di atas atau di bawah konten tabel.

#### T: Bagaimana cara menyesuaikan perataan teks dalam sel tabel?

 A: Untuk mengatur perataan teks dalam sel tabel, Anda bisa menggunakan`HorizontalAlignment` Dan`VerticalAlignment` properti dari`TextFragment` obyek. Misalnya, untuk meratakan tengah teks secara horizontal, Anda dapat mengaturnya`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . Demikian pula, Anda dapat mengaturnya`mytext.VerticalAlignment` untuk mengontrol perataan vertikal.

#### T: Dapatkah saya menambahkan gambar ke sel tabel, bukan teks?

 A: Ya, Anda dapat menambahkan gambar ke sel tabel menggunakan Aspose.PDF untuk .NET. Daripada membuat a`TextFragment` objek, Anda dapat membuat`Image` objek, muat file gambar, dan tambahkan ke sel yang diinginkan menggunakan`cell.Paragraphs.Add(image);` metode. Ini memungkinkan Anda memasukkan gambar ke dalam tabel di samping konten teks.