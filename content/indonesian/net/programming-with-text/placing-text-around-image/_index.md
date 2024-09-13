---
title: Menempatkan Teks di Sekitar Gambar dalam File PDF
linktitle: Menempatkan Teks di Sekitar Gambar dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menempatkan teks di sekitar gambar dalam berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 260
url: /id/net/programming-with-text/placing-text-around-image/
---
Dalam tutorial ini, kami akan menjelaskan cara menempatkan teks di sekitar gambar dalam file PDF menggunakan pustaka Aspose.PDF untuk .NET. Kami akan membahas proses langkah demi langkah untuk membuat tabel, menambahkan gambar, dan memposisikan teks di sekitar gambar menggunakan kode sumber C# yang disediakan.

## Persyaratan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Pustaka Aspose.PDF untuk .NET terinstal.
- Pemahaman dasar tentang pemrograman C#.

## Langkah 1: Siapkan Direktori Dokumen

 Pertama, Anda perlu mengatur jalur ke direktori tempat Anda ingin menyimpan file PDF yang dihasilkan. Ganti`"YOUR DOCUMENT DIRECTORY"` di dalam`dataDir` variabel dengan jalur ke direktori yang Anda inginkan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen dan Halaman

 Selanjutnya kita membuat`Document` objek dan menambahkan halaman ke dalamnya menggunakan`Pages.Add()` metode.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Langkah 3: Buat Tabel

 Kami membuat tabel menggunakan`Table` kelas dan menambahkannya ke koleksi paragraf halaman.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Langkah 4: Mengatur Lebar dan Margin Kolom Tabel

 Kami mengatur lebar kolom tabel dan membuat`MarginInfo` objek untuk mengatur margin.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Langkah 5: Tambahkan Gambar ke Tabel

 Kami menciptakan sebuah`Image` objek, tentukan jalur berkas gambar, dan tetapkan tinggi dan lebar gambar yang tetap. Kemudian, kita tambahkan gambar ke koleksi paragraf sel tabel.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Langkah 6: Tambahkan Teks di Sekitar Gambar

 Kami membuat variabel string yang berisi teks berformat HTML dan membuat`HtmlFragment`objek. Kemudian, kita tambahkan teks HTML ke sel tabel yang berisi gambar.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Langkah 7: Tambahkan Teks Tambahan

 Kami menciptakan yang lain`HtmlFragment` objek yang berisi teks berformat HTML tambahan dan menambahkannya ke sel tabel terpisah.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Langkah 8: Simpan Dokumen PDF

Terakhir, kami menyimpan dokumen PDF ke berkas keluaran yang ditentukan.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Contoh kode sumber untuk Menempatkan Teks di Sekitar Gambar menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Membuat instance objek dokumen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Buat halaman dalam Pdf
Aspose.Pdf.Page page = doc.Pages.Add();
// Membuat instance objek tabel
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Tambahkan tabel dalam kumpulan paragraf bagian yang diinginkan
page.Paragraphs.Add(table1);
// Diatur dengan lebar kolom tabel
table1.ColumnWidths = "120 270";
// Buat objek MarginInfo dan atur margin kiri, bawah, kanan dan atasnya
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Tetapkan bantalan sel default ke objek MarginInfo
table1.DefaultCellPadding = margin;
// Buat baris dalam tabel dan kemudian sel dalam baris
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Membuat objek gambar
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Tentukan jalur file gambar
logo.File = dataDir + "aspose-logo.jpg";
// Tentukan Tinggi Tetap gambar
logo.FixHeight = 120;
// Tentukan Lebar Tetap gambar
logo.FixWidth = 110;
row1.Cells.Add();
// Tambahkan gambar ke koleksi paragraf sel tabel
row1.Cells[0].Paragraphs.Add(logo);
// Buat variabel string dengan teks yang berisi tag html
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Buat objek teks yang akan ditambahkan di sebelah kanan gambar
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Tambahkan paragraf teks yang berisi teks HTML ke sel tabel
row1.Cells[1].Paragraphs.Add(TitleText);
// Atur perataan vertikal konten baris sebagai Atas
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
//Buat baris dalam tabel dan kemudian sel dalam baris
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Tetapkan nilai rentang baris untuk Baris kedua sebagai 2
SecondRow.Cells[0].ColSpan = 2;
// Atur perataan vertikal baris kedua sebagai Atas
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Tambahkan paragraf teks yang berisi teks HTML ke sel tabel
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Simpan file Pdf
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara menempatkan teks di sekitar gambar dalam dokumen PDF menggunakan pustaka Aspose.PDF untuk .NET. Dengan mengikuti panduan langkah demi langkah dan menjalankan kode C# yang disediakan, Anda dapat membuat tabel, menambahkan gambar, dan memposisikan teks di sekitar gambar dalam dokumen PDF.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial "Menempatkan Teks di Sekitar Gambar dalam Berkas PDF"?

J: Tutorial "Menempatkan Teks di Sekitar Gambar dalam Berkas PDF" menunjukkan cara menggunakan pustaka Aspose.PDF untuk .NET guna menempatkan teks di sekitar gambar dalam dokumen PDF. Tutorial ini menyediakan panduan langkah demi langkah dan kode sumber C# untuk membantu Anda membuat tabel, menambahkan gambar, dan memosisikan teks di sekitar gambar.

#### T: Mengapa saya ingin menempatkan teks di sekitar gambar dalam dokumen PDF?

J: Menempatkan teks di sekitar gambar akan meningkatkan tampilan visual dokumen PDF Anda, membuatnya lebih menarik dan informatif. Teknik ini sering digunakan dalam dokumen, brosur, laporan, dan materi lain yang ingin Anda padukan dengan gambar dan teks dengan cara yang menarik secara estetika.

#### T: Bagaimana cara mengatur direktori dokumen?

A: Untuk mengatur direktori dokumen:

1.  Mengganti`"YOUR DOCUMENT DIRECTORY"` di dalam`dataDir` variabel dengan jalur ke direktori tempat Anda ingin menyimpan berkas PDF yang dihasilkan.

#### T: Bagaimana cara membuat tabel dan menambahkan gambar ke dalamnya?

 A: Tutorial ini memandu Anda melalui proses pembuatan tabel menggunakan`Table` kelas dan menambahkan gambar ke tabel menggunakan`Image` kelas. Anda akan menentukan jalur, tinggi, dan lebar berkas gambar sebelum menambahkannya ke sel tabel.

#### T: Bagaimana cara memposisikan teks di sekitar gambar?

 A: Untuk memposisikan teks di sekitar gambar, Anda akan membuat teks berformat HTML menggunakan`HtmlFragment` kelas. Teks ini akan berisi judul dan teks isi. Anda kemudian akan menambahkan teks HTML ini ke sel tabel yang berdekatan dengan sel gambar.

#### T: Dapatkah saya menyesuaikan tampilan teks dan gambar?

A: Ya, Anda dapat menyesuaikan tampilan teks dan gambar menggunakan tag dan properti HTML. Misalnya, Anda dapat mengatur ukuran font, warna, gaya, dan perataan teks. Selain itu, Anda dapat menyesuaikan ukuran dan dimensi gambar.

#### T: Bagaimana cara menyimpan dokumen PDF?

 A: Setelah menambahkan gambar dan teks ke tabel, Anda dapat menyimpan dokumen PDF menggunakan`Save` metode dari`Document` kelas. Berikan jalur file keluaran yang diinginkan sebagai argumen ke`Save` metode.

#### T: Apa hasil yang diharapkan dari tutorial ini?

A: Dengan mengikuti tutorial dan menjalankan kode C# yang disediakan, Anda akan menghasilkan dokumen PDF yang menunjukkan cara menempatkan teks di sekitar gambar. Dokumen keluaran akan berisi tabel dengan gambar dan teks yang diposisikan di sekitarnya.

#### T: Dapatkah saya menggunakan format gambar lain selain JPG?

 A: Ya, Anda dapat menggunakan berbagai format gambar yang didukung oleh pustaka Aspose.PDF, seperti PNG, BMP, GIF, dan lainnya. Saat membuat`Image` objek, tentukan jalur file format gambar yang diinginkan.

#### T: Apakah Lisensi Aspose yang valid diperlukan untuk tutorial ini?

A: Ya, Lisensi Aspose yang valid diperlukan agar tutorial ini dapat berfungsi dengan benar. Anda dapat membeli lisensi penuh atau memperoleh lisensi sementara selama 30 hari dari situs web Aspose.