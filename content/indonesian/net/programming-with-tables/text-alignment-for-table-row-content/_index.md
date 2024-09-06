---
title: Penyelarasan Teks Untuk Konten Baris Tabel
linktitle: Penyelarasan Teks Untuk Konten Baris Tabel
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menyelaraskan konten baris dalam tabel PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 210
url: /id/net/programming-with-tables/text-alignment-for-table-row-content/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah untuk menyelaraskan konten baris dalam tabel dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya.

## Langkah 1: Membuat dokumen PDF
Pertama, kita akan membuat dokumen PDF:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Langkah 2: Inisialisasi tabel
Berikutnya, kita akan menginisialisasi tabel:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Langkah 3: Mengatur warna batas tabel
Kita akan mengonfigurasi warna batas tabel:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Langkah 4: Mengonfigurasi batas sel tabel
Kita akan mengonfigurasi batas sel tabel:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Langkah 5: Lakukan pengulangan untuk menambahkan 10 baris ke dalam tabel
Sekarang kita akan menggunakan loop untuk menambahkan 10 baris ke tabel:

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## Langkah 6: Mengonfigurasi perataan garis vertikal
Kita akan mengonfigurasi perataan vertikal baris tabel:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## Langkah 7: Menambahkan konten ke sel baris
Kita akan menambahkan konten ke sel baris:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## Langkah 8: Menambahkan tabel ke halaman dokumen
Sekarang mari tambahkan tabel ke halaman dokumen:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## Langkah 9: Menyimpan dokumen PDF
Terakhir, kita akan menyimpan dokumen PDF:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Contoh kode sumber untuk Penyelarasan Teks untuk Konten Baris Tabel menggunakan Aspose.PDF untuk .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat dokumen PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Menginisialisasi contoh baru Tabel
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Atur warna batas tabel menjadi LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// mengatur batas untuk sel tabel
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// buat loop untuk menambahkan 10 baris
for (int row_count = 0; row_count < 10; row_count++)
{
	// tambahkan baris ke tabel
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// Tambahkan objek tabel ke halaman pertama dokumen input
tocPage.Paragraphs.Add(table);
// Simpan dokumen yang diperbarui yang berisi objek tabel
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Kesimpulan
Selamat! Anda sekarang telah mempelajari cara menyelaraskan konten baris dalam tabel dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah ini menunjukkan kepada Anda cara membuat dokumen, menginisialisasi tabel, mengonfigurasi batas dan penyelarasan, menambahkan konten, dan menyimpan dokumen PDF. Sekarang Anda dapat menerapkan pengetahuan ini ke proyek Anda sendiri.

### Pertanyaan yang Sering Diajukan

#### T: Bagaimana cara menyelaraskan isi sel tabel secara horizontal?

 A: Anda dapat menyelaraskan isi sel tabel secara horizontal dengan mengatur`HorizontalAlign` properti sel`TextState` objek. Misalnya, untuk meratakan teks ke tengah, gunakan`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` Anda juga dapat mengaturnya ke`HorizontalAlignment.Left` atau`HorizontalAlignment.Right` untuk perataan kiri dan kanan.

#### T: Dapatkah saya menerapkan gaya dan warna batas yang berbeda pada sel individual dalam tabel?

 A: Ya, Anda dapat menerapkan gaya dan warna border yang berbeda pada sel-sel individual dalam tabel. Untuk menyesuaikan border pada sel tertentu, atur`cell.Border` properti ke yang baru`BorderInfo`objek dengan pengaturan yang diinginkan, seperti sisi batas, lebar, dan warna.

#### T: Bagaimana cara menyesuaikan perataan vertikal konten tabel dalam sel?

 A: Anda dapat menyesuaikan perataan vertikal konten tabel di dalam sel dengan mengatur`VerticalAlignment` properti baris ke`VerticalAlignment.Center`, `VerticalAlignment.Top` , atau`VerticalAlignment.Bottom`Properti ini mengontrol perataan vertikal semua sel dalam baris tersebut.

#### T: Apakah mungkin untuk menambahkan lebih banyak kolom atau baris ke tabel secara dinamis?

 A: Ya, Anda dapat menambahkan lebih banyak kolom dan baris ke tabel secara dinamis dengan menggunakan`table.Rows.Add()` metode untuk menambahkan baris baru dan`row.Cells.Add()` metode untuk menambahkan sel baru ke baris. Anda dapat melakukannya di dalam loop atau berdasarkan kebutuhan spesifik Anda.

#### T: Bagaimana cara mengatur warna latar belakang untuk sel tertentu atau seluruh tabel?

 A: Untuk mengatur warna latar belakang untuk sel tertentu atau seluruh tabel, gunakan`BackgroundColor` milik`Cell` atau`Table` objek. Misalnya, untuk mengatur warna latar belakang sel, gunakan`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.