---
title: Tambahkan Kolom Berulang Dalam Dokumen PDF
linktitle: Tambahkan Kolom Berulang Dalam Dokumen PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan kolom berulang dalam dokumen PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 20
url: /id/net/programming-with-tables/add-repeating-column/
---
Dalam tutorial ini, kita akan mempelajari cara menambahkan kolom berulang dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber dalam C# langkah demi langkah. Di akhir tutorial ini, Anda akan mengetahui cara membuat tabel dengan kolom berulang dalam dokumen PDF. Mari kita mulai!

## Langkah 1: Menyiapkan lingkungan
Pertama, pastikan Anda telah menyiapkan lingkungan pengembangan C# dengan Aspose.PDF untuk .NET. Tambahkan referensi ke pustaka dan impor namespace yang diperlukan.

## Langkah 2: Membuat dokumen PDF
Pada langkah ini, kita membuat dokumen PDF baru.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

Kami telah membuat dokumen PDF kosong tempat kami dapat menambahkan konten.

## Langkah 3: Membuat tabel
Pada langkah ini kita membuat tabel utama (`outerTable`) dan tabel bersarang (`mytable`) yang akan diulang di kolom.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Kami menentukan properti tabel, seperti lebar kolom dan mode pemisah tabel bersarang.

## Langkah 4: Menambahkan tabel ke dokumen
Sekarang kita tambahkan tabel yang dibuat ke dokumen PDF.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

Pertama kita tambahkan tabel utama (`outerTable`) ke dokumen PDF. Selanjutnya, kita tambahkan tabel bersarang (`mytable` ) sebagai paragraf dalam sel di tabel utama. Kami juga menentukan jumlah kolom berulang untuk`mytable` (dalam contoh ini, 5 kolom).

## Langkah 5: Menambahkan header dan baris
Sekarang kita tambahkan header dan baris ke tabel.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
// Tambahkan header lainnya di sini

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // Tambahkan kolom lainnya di sini
}
```

Pertama kita tambahkan header pada baris pertama tabel (`headerRow`). Kemudian kita tambahkan baris data dari loop. Dalam contoh ini, kita tambahkan 6 baris data.

## Langkah 6: Menyimpan dokumen PDF
Terakhir, kami menyimpan dokumen PDF ke file yang ditentukan.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Pastikan untuk menentukan direktori dan nama file yang benar untuk menyimpan berkas PDF keluaran.

### Contoh kode sumber untuk menambahkan kolom berulang menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Buat dokumen baru
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Buat instance tabel luar yang menempati seluruh halaman
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//Buat instance objek tabel yang akan disarangkan di dalam outerTable yang akan dipisahkan di dalam halaman yang sama
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// Tambahkan outerTable ke paragraf halaman
// Tambahkan mytable ke outerTable
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Tambahkan Baris Header
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// Buat baris dalam tabel dan kemudian sel dalam baris
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menambahkan kolom berulang dalam dokumen PDF menggunakan Aspose.PDF for .NET. Anda dapat menggunakan panduan langkah demi langkah ini untuk membuat tabel dengan kolom berulang dalam proyek C# Anda sendiri.

### FAQ untuk menambahkan kolom berulang dalam dokumen PDF

#### T: Dapatkah saya menyesuaikan jumlah kolom yang berulang pada tabel bersarang?

 A: Ya, Anda dapat menyesuaikan jumlah kolom berulang dalam tabel bersarang. Dalam contoh yang diberikan, kami mengatur`mytable.RepeatingColumnsCount = 5;`, yang berarti akan ada 5 kolom yang berulang. Anda dapat mengubah nilai ini ke angka yang diinginkan.

#### T: Apakah mungkin untuk menambahkan lebih banyak baris ke tabel bersarang secara dinamis?

A: Ya, Anda dapat menambahkan lebih banyak baris ke tabel bersarang secara dinamis dengan cara yang sama seperti yang ditunjukkan dalam tutorial. Anda dapat menggunakan loop atau logika lainnya untuk menambahkan baris berdasarkan data Anda.

#### T: Dapatkah saya menerapkan gaya dan pemformatan ke tabel dan selnya?

A: Ya, Anda dapat menerapkan gaya dan pemformatan ke tabel dan sel-selnya menggunakan Aspose.PDF untuk .NET. Pustaka tersebut menyediakan berbagai properti dan metode untuk menyesuaikan tampilan tabel dan isinya.

#### T: Apakah Aspose.PDF untuk .NET kompatibel dengan .NET Core?

A: Ya, Aspose.PDF untuk .NET kompatibel dengan .NET Core. Anda dapat menggunakannya di aplikasi .NET Framework dan .NET Core.

#### T: Dapatkah saya menggunakan pendekatan ini untuk menambahkan kolom berulang dalam dokumen PDF yang ada?

A: Ya, Anda dapat menggunakan pendekatan ini untuk menambahkan kolom berulang dalam dokumen PDF yang sudah ada. Cukup muat dokumen yang sudah ada menggunakan Aspose.PDF for .NET dan ikuti langkah yang sama untuk membuat dan menambahkan kolom berulang.