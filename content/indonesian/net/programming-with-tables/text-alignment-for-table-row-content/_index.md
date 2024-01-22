---
title: Perataan Teks Untuk Isi Baris Tabel
linktitle: Perataan Teks Untuk Isi Baris Tabel
second_title: Aspose.PDF untuk Referensi .NET API
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
Selanjutnya, kita akan menginisialisasi tabel:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Langkah 3: Mengatur warna batas tabel
Kami akan mengkonfigurasi warna batas tabel:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Langkah 4: Mengonfigurasi batas sel tabel
Kami akan mengkonfigurasi batas sel tabel:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Langkah 5: Ulangi untuk menambahkan 10 baris ke tabel
Kita sekarang akan menggunakan loop untuk menambahkan 10 baris ke tabel:

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
Kami akan menambahkan konten ke sel baris:

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
Terakhir, kami akan menyimpan dokumen PDF:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Contoh kode sumber Perataan Teks Untuk Konten Baris Tabel menggunakan Aspose.PDF untuk .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat dokumen PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Menginisialisasi instance baru dari Tabel
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Atur warna batas tabel menjadi LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// atur batas untuk sel tabel
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// buat lingkaran untuk menambahkan 10 baris
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
// Tambahkan objek tabel ke halaman pertama dokumen masukan
tocPage.Paragraphs.Add(table);
// Simpan dokumen terbaru yang berisi objek tabel
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Kesimpulan
Selamat! Anda sekarang telah mempelajari cara menyelaraskan konten baris dalam tabel dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah ini menunjukkan kepada Anda cara membuat dokumen, menginisialisasi tabel, mengonfigurasi batas dan perataan, menambahkan konten, dan menyimpan dokumen PDF. Sekarang Anda dapat menerapkan pengetahuan ini pada proyek Anda sendiri.

### FAQ

#### T: Bagaimana cara menyelaraskan konten sel tabel secara horizontal?

 A: Anda dapat menyelaraskan isi sel tabel secara horizontal dengan mengatur`HorizontalAlign` milik sel`TextState` obyek. Misalnya, untuk meratakan tengah teks, gunakan`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . Anda juga dapat mengaturnya ke`HorizontalAlignment.Left` atau`HorizontalAlignment.Right` untuk perataan kiri dan kanan, masing-masing.

#### T: Dapatkah saya menerapkan gaya dan warna batas yang berbeda ke masing-masing sel dalam tabel?

 J: Ya, Anda bisa menerapkan gaya dan warna batas yang berbeda ke masing-masing sel dalam tabel. Untuk menyesuaikan batas sel tertentu, atur`cell.Border` properti ke yang baru`BorderInfo`objek dengan pengaturan yang diinginkan, seperti sisi tepi, lebar, dan warna.

#### T: Bagaimana cara menyesuaikan perataan vertikal isi tabel di dalam sel?

 J: Anda dapat menyesuaikan perataan vertikal isi tabel di dalam sel dengan mengatur`VerticalAlignment` properti baris ke`VerticalAlignment.Center`, `VerticalAlignment.Top` , atau`VerticalAlignment.Bottom`. Properti ini mengontrol perataan vertikal semua sel di baris tersebut.

#### T: Apakah mungkin menambahkan lebih banyak kolom atau baris ke tabel secara dinamis?

 J: Ya, Anda dapat menambahkan lebih banyak kolom dan baris ke tabel secara dinamis dengan menggunakan`table.Rows.Add()` metode untuk menambahkan baris baru dan`row.Cells.Add()` metode untuk menambahkan sel baru ke baris. Anda dapat melakukan ini di dalam loop atau berdasarkan kebutuhan spesifik Anda.

#### T: Bagaimana cara mengatur warna latar belakang untuk sel tertentu atau seluruh tabel?

 J: Untuk mengatur warna latar belakang sel tertentu atau seluruh tabel, gunakan`BackgroundColor` properti dari`Cell` atau`Table` obyek. Misalnya, untuk mengatur warna latar belakang sel, gunakan`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.