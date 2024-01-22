---
title: Menempatkan Teks Di Sekitar Gambar Dalam File PDF
linktitle: Menempatkan Teks Di Sekitar Gambar Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menempatkan teks di sekitar gambar dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 260
url: /id/net/programming-with-text/placing-text-around-image/
---
Dalam tutorial ini, kami akan menjelaskan cara menempatkan teks di sekitar gambar dalam file PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Kita akan melalui proses langkah demi langkah dalam membuat tabel, menambahkan gambar, dan memposisikan teks di sekitar gambar menggunakan kode sumber C# yang disediakan.

## Persyaratan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Pustaka Aspose.PDF untuk .NET diinstal.
- Pemahaman dasar tentang pemrograman C#.

## Langkah 1: Siapkan Direktori Dokumen

 Pertama, Anda perlu mengatur jalur ke direktori tempat Anda ingin menyimpan file PDF yang dihasilkan. Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam`dataDir`variabel dengan jalur ke direktori yang Anda inginkan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen dan Halaman

 Selanjutnya, kita membuat a`Document` objek dan tambahkan halaman ke dalamnya menggunakan`Pages.Add()` metode.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Langkah 3: Buat Tabel

 Kami membuat tabel menggunakan`Table` kelas dan menambahkannya ke kumpulan paragraf halaman.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Langkah 4: Atur Lebar dan Margin Kolom Tabel

 Kami mengatur lebar kolom tabel dan membuat a`MarginInfo` objek untuk mengatur margin.

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

 Kami membuat`Image` objek, tentukan jalur file gambar, dan atur tinggi dan lebar tetap gambar. Kemudian, kami menambahkan gambar ke kumpulan paragraf di sel tabel.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Langkah 6: Tambahkan Teks di Sekitar Gambar

 Kami membuat variabel string yang berisi teks berformat HTML dan membuat`HtmlFragment`obyek. Kemudian, kami menambahkan teks HTML ke sel tabel yang berisi gambar.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Langkah 7: Tambahkan Teks Tambahan

 Kami membuat yang lain`HtmlFragment` objek yang berisi teks tambahan berformat HTML dan menambahkannya ke sel tabel terpisah.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Langkah 8: Simpan Dokumen PDF

Terakhir, kami menyimpan dokumen PDF ke file keluaran yang ditentukan.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Contoh kode sumber untuk Menempatkan Teks di Sekitar Gambar menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat instance objek dokumen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Buat halaman di Pdf
Aspose.Pdf.Page page = doc.Pages.Add();
// Buat instance objek tabel
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Tambahkan tabel dalam kumpulan paragraf dari bagian yang diinginkan
page.Paragraphs.Add(table1);
// Atur dengan lebar kolom tabel
table1.ColumnWidths = "120 270";
// Buat objek MarginInfo dan atur margin kiri, bawah, kanan dan atas
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Atur padding sel default ke objek MarginInfo
table1.DefaultCellPadding = margin;
// Buat baris dalam tabel dan kemudian sel dalam baris
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Buat objek gambar
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Tentukan jalur file gambar
logo.File = dataDir + "aspose-logo.jpg";
// Tentukan Tinggi Tetap gambar
logo.FixHeight = 120;
// Tentukan gambar Lebar Tetap
logo.FixWidth = 110;
row1.Cells.Add();
// Tambahkan gambar ke kumpulan paragraf sel tabel
row1.Cells[0].Paragraphs.Add(logo);
// Buat variabel string dengan teks yang berisi tag html
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Buat objek teks untuk ditambahkan di sebelah kanan gambar
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Tambahkan paragraf teks yang berisi teks HTML ke sel tabel
row1.Cells[1].Paragraphs.Add(TitleText);
// Atur perataan vertikal isi baris sebagai Atas
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Buat baris dalam tabel dan kemudian sel dalam baris
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Tetapkan nilai rentang baris untuk baris kedua sebagai 2
SecondRow.Cells[0].ColSpan = 2;
// Atur perataan vertikal baris kedua sebagai Atas
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Tambahkan paragraf teks yang berisi teks HTML ke sel tabel
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Simpan file Pdfnya
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara menempatkan teks di sekitar gambar dalam dokumen PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Dengan mengikuti panduan langkah demi langkah dan menjalankan kode C# yang disediakan, Anda dapat membuat tabel, menambahkan gambar, dan memposisikan teks di sekitar gambar dalam dokumen PDF.

### FAQ

#### Q: Apa tujuan dari tutorial "Menempatkan Teks di Sekitar Gambar Dalam File PDF"?

J: Tutorial "Menempatkan Teks di Sekitar Gambar Dalam File PDF" menunjukkan cara menggunakan perpustakaan Aspose.PDF untuk .NET untuk menempatkan teks di sekitar gambar dalam dokumen PDF. Tutorial ini memberikan panduan langkah demi langkah dan kode sumber C# untuk membantu Anda membuat tabel, menambahkan gambar, dan memposisikan teks di sekitar gambar.

#### T: Mengapa saya ingin menempatkan teks di sekitar gambar dalam dokumen PDF?

J: Menempatkan teks di sekitar gambar akan meningkatkan presentasi visual dokumen PDF Anda, menjadikannya lebih menarik dan informatif. Teknik ini sering digunakan dalam dokumen, brosur, laporan, dan materi lain di mana Anda ingin menggabungkan gambar dan teks dengan cara yang estetis.

#### T: Bagaimana cara mengatur direktori dokumen?

A: Untuk mengatur direktori dokumen:

1.  Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam`dataDir` variabel dengan jalur ke direktori tempat Anda ingin menyimpan file PDF yang dihasilkan.

#### T: Bagaimana cara membuat tabel dan menambahkan gambar ke dalamnya?

 A: Tutorial ini memandu Anda melalui proses pembuatan tabel menggunakan`Table` kelas dan menambahkan gambar ke tabel menggunakan`Image` kelas. Anda akan menentukan jalur, tinggi, dan lebar file gambar sebelum menambahkannya ke sel tabel.

#### T: Bagaimana cara memposisikan teks di sekitar gambar?

 J: Untuk memposisikan teks di sekitar gambar, Anda akan membuat teks berformat HTML menggunakan`HtmlFragment` kelas. Teks ini akan berisi judul dan teks isi. Anda kemudian akan menambahkan teks HTML ini ke sel tabel yang bersebelahan dengan sel gambar.

#### Q: Dapatkah saya menyesuaikan tampilan teks dan gambar?

A: Ya, Anda dapat menyesuaikan tampilan teks dan gambar menggunakan tag dan properti HTML. Misalnya, Anda dapat mengatur ukuran font, warna, gaya, dan perataan teks. Selain itu, Anda dapat menyesuaikan ukuran dan dimensi gambar.

#### Q: Bagaimana cara menyimpan dokumen PDF?

 A: Setelah menambahkan gambar dan teks ke tabel, Anda dapat menyimpan dokumen PDF menggunakan`Save` metode`Document` kelas. Berikan jalur file keluaran yang diinginkan sebagai argumen ke`Save` metode.

#### Q: Apa hasil yang diharapkan dari tutorial ini?

J: Dengan mengikuti tutorial dan menjalankan kode C# yang disediakan, Anda akan menghasilkan dokumen PDF yang menunjukkan cara menempatkan teks di sekitar gambar. Dokumen keluaran akan berisi tabel dengan gambar dan teks yang ditempatkan di sekitarnya.

#### T: Dapatkah saya menggunakan format gambar lain selain JPG?

 J: Ya, Anda dapat menggunakan format gambar berbeda yang didukung oleh pustaka Aspose.PDF, seperti PNG, BMP, GIF, dan lainnya. Saat membuat`Image` objek, tentukan jalur file format gambar yang diinginkan.

#### T: Apakah Lisensi Aspose yang valid diperlukan untuk tutorial ini?

A: Ya, Lisensi Aspose yang valid diperlukan agar tutorial ini dapat berfungsi dengan benar. Anda dapat membeli lisensi penuh atau mendapatkan lisensi sementara selama 30 hari dari situs web Aspose.