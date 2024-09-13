---
title: Render Tabel Dalam Dokumen PDF
linktitle: Render Tabel Dalam Dokumen PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menampilkan tabel dalam dokumen PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 170
url: /id/net/programming-with-tables/render-table/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah untuk menampilkan tabel dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya.

## Langkah 1: Membuat dokumen
Pertama, kita akan membuat dokumen PDF baru:

```csharp
// Jalur ke direktori dokumen
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat dokumen baru
Document doc = new Document();
```

## Langkah 2: Mengonfigurasi margin dan orientasi halaman
Berikutnya, kita akan mengonfigurasi margin halaman dan mengatur orientasi ke mode lanskap:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## Langkah 3: Membuat tabel dan kolom
Sekarang mari kita membuat tabel dan mengatur lebar kolom:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## Langkah 4: Tambahkan baris dan sel ke tabel
Berikutnya, kita akan menambahkan baris dan sel ke tabel menggunakan loop:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## Langkah 5: Menambahkan tabel ke halaman
Sekarang mari tambahkan tabel ke halaman dokumen:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Langkah 6: Menampilkan tabel di halaman baru
Selanjutnya, kita akan membuat tabel baru dan menyetel properti "IsInNewPage" ke "true" untuk menampilkan tabel di halaman baru:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## Langkah 7: Simpan PDF
Terakhir, kami menyimpan dokumen PDF:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Contoh kode sumber untuk Render Table menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Halaman ditambahkan.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// Saya ingin tabel 1 disimpan di halaman berikutnya ya...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Kesimpulan
Selamat! Anda sekarang telah mempelajari cara menampilkan tabel dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah ini menunjukkan kepada Anda cara membuat dokumen, mengonfigurasi margin dan orientasi halaman, menambahkan tabel, dan menampilkan tabel di halaman baru. Sekarang Anda dapat menerapkan pengetahuan ini ke proyek Anda sendiri.

### FAQ untuk membuat tabel render dalam dokumen PDF

#### T: Bagaimana cara mengubah tampilan tabel, seperti mengubah warna sel atau menambahkan batas?

 A: Untuk mengubah tampilan tabel, Anda dapat mengatur berbagai properti tabel.`Aspose.Pdf.Table` dan sel-selnya. Misalnya, Anda dapat mengatur`BackgroundColor` properti sel untuk mengubah warna latar belakangnya. Anda juga dapat mengatur`Border` properti tabel atau sel individual untuk menambahkan batas. Selain itu, Anda dapat menyesuaikan font, warna teks, dan perataan konten tabel dengan memodifikasi`TextState` dari`TextFragment` objek yang ditambahkan ke sel.

#### T: Dapatkah saya menambahkan header dan footer ke tabel?

A: Ya, Anda dapat menambahkan header atau footer ke tabel dengan membuat baris tambahan di awal atau akhir tabel dan mengatur konten yang sesuai di dalam sel. Anda dapat menyesuaikan header atau footer secara terpisah dari konten tabel lainnya dengan menambahkan gaya atau konten yang berbeda ke baris-baris tertentu ini.

#### T: Bagaimana cara mengontrol posisi tabel di halaman?

A: Untuk mengontrol posisi tabel di halaman, Anda dapat menyesuaikan`MarginInfo` dari`PageInfo` objek. Itu`MarginInfo` memungkinkan Anda untuk mengatur margin kiri, kanan, atas, dan bawah halaman, yang memengaruhi ruang yang tersedia untuk tabel. Anda juga dapat menggunakan`PositioningType` milik`Aspose.Pdf.Table` untuk mengontrol perataan horizontal dan vertikal dalam area konten halaman.

#### T: Dapatkah saya mengekspor tabel ke format file lain, seperti Excel atau CSV?

J: Aspose.PDF untuk .NET terutama dirancang untuk bekerja dengan dokumen PDF. Meskipun dapat mengekspor dokumen PDF sebagai gambar atau XPS, Aspose.PDF tidak secara langsung mendukung ekspor tabel ke format seperti Excel atau CSV. Untuk mengekspor data tabel ke format file yang berbeda, Anda mungkin perlu menggunakan pustaka atau metode tambahan untuk mengonversi konten PDF ke format yang diinginkan.

#### T: Bagaimana cara menambahkan hyperlink ke sel tabel?

 A: Untuk menambahkan hyperlink ke sel tabel, Anda dapat menggunakan`Aspose.Pdf.WebHyperlink` kelas untuk membuat hyperlink dan kemudian menambahkannya sebagai jangkar ke`TextFragment`di dalam sel. Ini memungkinkan Anda untuk mengaitkan URL atau target tautan dengan teks atau konten tertentu di dalam sel, sehingga menciptakan hyperlink yang dapat diklik.