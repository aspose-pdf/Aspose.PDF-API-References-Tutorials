---
title: Tentukan Table Break Dalam File PDF
linktitle: Tentukan Table Break Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menentukan hentian tabel dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 60
url: /id/net/programming-with-tables/determine-table-break/
---
Dalam tutorial ini, kita akan mempelajari cara menentukan hentian tabel dalam file PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber dalam C# langkah demi langkah. Di akhir tutorial ini, Anda akan mengetahui cara menentukan apakah suatu tabel melebihi margin halaman. Ayo mulai!

## Langkah 1: Menyiapkan lingkungan
Pertama, pastikan Anda telah menyiapkan lingkungan pengembangan C# dengan Aspose.PDF untuk .NET. Tambahkan referensi ke perpustakaan dan impor namespace yang diperlukan.

## Langkah 2: Membuat dokumen PDF
 Pada langkah ini, kami membuat yang baru`Document` objek untuk mewakili dokumen PDF.

```csharp
pdf-Document = new Document();
```

Dokumen ini akan digunakan untuk menambahkan bagian dan tabel.

## Langkah 3: Menambahkan bagian dan tabel
Sekarang kita akan menambahkan bagian ke dokumen PDF kita dan membuat tabel di dalam bagian ini.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Kami juga menentukan margin atas 300 poin untuk tabel tersebut. Anda dapat menyesuaikan nilai ini sesuai dengan kebutuhan Anda.

## Langkah 4: Pengaturan Tabel
Pada langkah ini, kami mengonfigurasi properti tabel, seperti lebar kolom dan batas.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Di sini kita menentukan lebar kolom tabel dan batas sel. Anda dapat menyesuaikan nilai-nilai ini sesuai dengan preferensi Anda.

## Langkah 5: Tambahkan baris dan sel ke tabel
Sekarang kita akan membuat baris dan sel dalam tabel menggunakan loop.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Di sini kita membuat 17 baris dalam tabel dan menambahkan tiga sel ke setiap baris. Anda dapat menyesuaikan gesper sesuai kebutuhan Anda.

## Langkah 6: Menentukan Table Breaks
Sekarang kita akan menentukan apakah tabel melebihi margin halaman dengan membandingkan tinggi halaman dengan tinggi total objek dalam tabel.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Kami menghitung tinggi halaman dan tinggi total objek dengan mempertimbangkan margin. Jika selisihnya 10 atau kurang, tabel melebihi margin halaman.

## Langkah 7: Menyimpan dokumen PDF
Terakhir kita simpan dokumen PDF beserta hasilnya.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Pastikan untuk menentukan direktori dokumen yang benar. File PDF yang dihasilkan akan disimpan dengan jeda tabel yang ditentukan.

### Contoh kode sumber untuk Menentukan Table Break menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat instance kelas objek PDF
Document pdf = new Document();
// Tambahkan bagian tersebut ke koleksi bagian dokumen PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// Buat instance objek tabel
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Tambahkan tabel dalam kumpulan paragraf dari bagian yang diinginkan
page.Paragraphs.Add(table1);
// Atur dengan lebar kolom tabel
table1.ColumnWidths = "100 100 100";
// Tetapkan batas sel default menggunakan objek BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Tetapkan batas tabel menggunakan objek BorderInfo khusus lainnya
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Buat objek MarginInfo dan atur margin kiri, bawah, kanan dan atas
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Atur padding sel default ke objek MarginInfo
table1.DefaultCellPadding = margin;
// Jika Anda menambah penghitung menjadi 17, tabel akan rusak
// Karena tidak dapat ditampung lagi di halaman ini
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// Buat baris dalam tabel dan kemudian sel dalam baris
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Dapatkan informasi Tinggi Halaman
float PageHeight = (float)pdf.PageInfo.Height;
// Dapatkan informasi tinggi total margin Atas & Bawah Halaman,
// Margin atas tabel dan tinggi tabel.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Tampilkan Tinggi Halaman, Tinggi Tabel, Margin atas tabel, dan Atas Halaman
// Dan informasi margin bawah
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Periksa apakah kita mengurangi jumlah margin atas Halaman + margin Bawah Halaman
// + Margin Atas Tabel dan tinggi tabel dari tinggi Halaman dan kurang dari itu
// Dari 10 (rata-rata baris bisa lebih besar dari 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Jika nilainya kurang dari 10, maka tampilkan pesannya.
	//Yang menunjukkan bahwa baris lain tidak dapat ditempatkan dan jika kita menambahkan yang baru
	// Baris, meja akan pecah. Itu tergantung pada nilai tinggi baris.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Simpan dokumen pdf
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menentukan hentian tabel dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan panduan langkah demi langkah ini untuk memeriksa apakah tabel melebihi margin halaman di proyek C# Anda sendiri.

### FAQ untuk menentukan table break dalam file PDF

#### Q: Apa tujuan menentukan table break dalam dokumen PDF?

J: Tujuan menentukan hentian tabel dalam dokumen PDF adalah untuk memeriksa apakah tabel melebihi margin halaman. Hal ini memastikan bahwa isi tabel ditampilkan dengan benar dalam ruang halaman yang tersedia. Dengan mendeteksi jeda tabel, Anda dapat menangani luapan konten dan menyesuaikan tata letak tabel.

#### T: Bagaimana cara menyesuaikan margin atas tabel?

 J: Dalam kode sumber C# yang disediakan, Anda dapat menyesuaikan margin atas tabel dengan mengubah nilainya`table1.Margin.Top`Properti. Menambah atau mengurangi nilai sesuai kebutuhan untuk mengatur margin atas tabel yang diinginkan.

#### T: Dapatkah saya menyesuaikan tampilan tabel, seperti warna sel dan ukuran font?

J: Ya, Anda dapat menyesuaikan tampilan tabel dan selnya menggunakan berbagai properti dan metode yang disediakan oleh Aspose.PDF untuk .NET. Misalnya, Anda dapat mengubah warna latar belakang sel, ukuran font, jenis font, perataan teks, dan banyak lagi. Lihat dokumentasi resmi untuk informasi lebih lanjut tentang cara menyesuaikan tampilan tabel.

#### T: Apa yang terjadi jika tabel melebihi margin halaman?

J: Jika tabel melebihi margin halaman, hal ini dapat mengakibatkan konten terpotong atau tumpang tindih, sehingga membuat dokumen PDF menjadi kurang mudah dibaca dan terorganisir. Dengan mendeteksi jeda tabel dan menangani luapan, Anda dapat memastikan bahwa konten tetap ditampilkan dengan benar dalam area halaman yang tersedia.

#### T: Dapatkah saya menentukan hentian tabel untuk beberapa tabel dalam dokumen PDF yang sama?

J: Ya, Anda dapat menentukan pemisah tabel untuk beberapa tabel dalam dokumen PDF yang sama. Cukup ulangi langkah-langkah untuk setiap tabel yang ingin Anda analisis dan sesuaikan tata letak tabel seperlunya untuk mencegah konten meluap.