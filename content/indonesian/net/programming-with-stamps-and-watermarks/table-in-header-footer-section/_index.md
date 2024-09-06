---
title: Tabel Di Bagian Header Footer
linktitle: Tabel Di Bagian Header Footer
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menambahkan tabel di bagian header/footer dokumen PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 170
url: /id/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara menambahkan tabel di bagian header atau footer dokumen PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan kepada Anda cara membuat dokumen PDF kosong, menambahkan halaman, mengonfigurasi bagian header, membuat tabel, menambahkan baris dan sel ke tabel, dan akhirnya menyimpan dokumen PDF.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal.
- Pustaka Aspose.PDF untuk .NET diunduh dan dirujuk dalam proyek Anda.

## Langkah 2: Membuat Dokumen dan Halaman PDF

 Langkah pertama adalah membuat instance dari`Document` kelas dan menambahkan halaman ke dokumen. Berikut caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Membuat instance objek Dokumen
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Buat halaman dalam dokumen PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat Anda ingin menyimpan dokumen PDF.

## Langkah 3: Mengonfigurasi bagian header

 Sekarang kita akan mengkonfigurasi bagian header dokumen PDF dengan membuat instance dari`HeaderFooter` kelas. Begini caranya:

```csharp
// Buat bagian header untuk file PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Tentukan bagian header untuk halaman
page. Header = header;

// Mengatur margin atas bagian header
header. Margin. Top = 20;
```

## Langkah 4: Membuat tabel

 Sekarang kita akan membuat tabel menggunakan`Table` kelas dan menambahkannya ke koleksi paragraf bagian judul. Berikut caranya:

```csharp
// Membuat instance objek Tabel
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Tambahkan tabel ke koleksi paragraf di bagian header
header.Paragraphs.Add(tab1);

// Tentukan lebar kolom tabel
tab1.ColumnWidths = "60,300";
```

Kode di atas membuat tabel dengan dua kolom dengan lebar tertentu.

## Langkah 5: Tambahkan baris dan sel ke tabel

 Sekarang kita akan menambahkan baris dan sel ke tabel menggunakan`Row` kelas dan`Cell` kelas. Begini caranya:

```csharp
// Buat baris di tabel dan tambahkan sel
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// Gabungkan sel pertama dari baris pertama
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Buat baris lain di tabel dan tambahkan sel dengan gambar
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Langkah 6: Menyimpan Dokumen PDF

Setelah tabel ditambahkan ke bagian header, kita dapat menyimpan dokumen PDF. Berikut caranya:

```csharp
// Simpan file PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat Anda ingin menyimpan dokumen PDF.

### Contoh kode sumber untuk Tabel di Bagian Header dan Footer menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat instance Dokumen dengan memanggil konstruktor kosong
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Buat halaman dalam dokumen pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

//Buat Bagian Header dari file PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Mengatur Header Ganjil untuk file PDF
page.Header = header;

// Mengatur margin atas untuk bagian header
header.Margin.Top = 20;

// Membuat instance objek tabel
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Tambahkan tabel dalam kumpulan paragraf bagian yang diinginkan
header.Paragraphs.Add(tab1);

// Mengatur batas sel default menggunakan objek BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Diatur dengan lebar kolom tabel
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Buat baris dalam tabel dan kemudian sel dalam baris
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Tetapkan nilai rentang baris untuk baris pertama sebagai 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Buat baris dalam tabel dan kemudian sel dalam baris
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Mengatur warna latar belakang untuk Baris2
row2.BackgroundColor = Color.White;

// Tambahkan sel yang berisi gambar
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Atur lebar gambar menjadi 60
img.FixWidth = 60;

// Tambahkan gambar ke sel tabel
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Mengatur perataan vertikal teks menjadi rata tengah
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Simpan file Pdf
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Kesimpulan

Selamat! Anda telah mempelajari cara menambahkan tabel di bagian header atau footer dokumen PDF menggunakan Aspose.PDF untuk .NET. Kini Anda dapat menyesuaikan header dan footer dengan menambahkan tabel untuk menampilkan informasi tambahan di dokumen PDF Anda.

### FAQ untuk tabel di bagian header dan footer

#### T: Apa tujuan menambahkan tabel di bagian header atau footer dokumen PDF?

A: Menambahkan tabel di bagian header atau footer dokumen PDF memungkinkan Anda menampilkan informasi terstruktur dan terorganisir seperti judul, subjudul, logo, atau konten lainnya yang ingin Anda tampilkan secara konsisten di setiap halaman dokumen.

#### T: Bagaimana kode sumber C# yang disediakan mencapai penambahan tabel di bagian header atau footer dokumen PDF?

A: Kode tersebut menunjukkan proses pembuatan dokumen PDF kosong, penambahan halaman, konfigurasi bagian header, pembuatan tabel dengan baris dan sel, dan terakhir penyimpanan dokumen PDF. Hasilnya adalah tabel yang ditampilkan di bagian header dokumen PDF.

#### T: Dapatkah saya menyesuaikan tampilan sel tabel, seperti batas, warna latar belakang, dan gaya teks?

A: Ya, Anda dapat menyesuaikan tampilan sel tabel dengan mengatur properti seperti batas sel, warna latar belakang, gaya teks, font, ukuran font, dan banyak lagi.

#### T: Bagaimana tabel ditambahkan ke bagian header dokumen PDF?

A: Kode menambahkan tabel ke koleksi paragraf di bagian header, yang memastikan bahwa tabel ditampilkan di header setiap halaman.

#### T: Dapatkah saya menambahkan lebih banyak baris dan sel ke tabel sesuai kebutuhan?

 A: Tentu saja, Anda dapat menambahkan lebih banyak baris dan sel ke tabel dengan menggunakan`Rows.Add()` Dan`Cells.Add()` metode. Ini memungkinkan Anda untuk menyusun konten tabel sesuai keinginan.

#### T: Apakah mungkin untuk menyesuaikan lebar kolom tabel?
 A: Ya, Anda dapat menyesuaikan lebar kolom tabel menggunakan`ColumnWidths` properti. Ini memungkinkan Anda untuk mengontrol tata letak tabel.

#### T: Bagaimana cara merentangkan sel di beberapa kolom atau baris dalam tabel?
 A: Untuk membentangkan sel di beberapa kolom, Anda dapat menggunakan`ColSpan`properti sel yang sesuai. Demikian pula, Anda dapat menggunakan`RowSpan` properti untuk membentangkan sel di beberapa baris.

#### T: Apa yang terjadi jika saya ingin menambahkan tabel ke bagian header dan footer dokumen PDF?

 A: Anda dapat mengikuti pendekatan serupa untuk bagian header dan footer. Cukup buat`HeaderFooter` misalnya untuk footer, konfigurasikan, dan tambahkan tabel ke koleksi paragrafnya.

#### T: Dapatkah saya menggunakan gambar dalam sel tabel, dan bagaimana cara melakukannya?

 A: Ya, Anda dapat menambahkan gambar di dalam sel tabel. Contoh kode menunjukkan penambahan gambar ke dalam sel dengan membuat`Image` objek, mengatur jalur file dan dimensinya, lalu menambahkannya ke paragraf sel.

#### T: Bagaimana cara memastikan tabel muncul secara konsisten di semua halaman dalam dokumen PDF?

 A: Saat Anda menambahkan tabel ke bagian header atau footer menggunakan`HeaderFooter` Misalnya, Aspose.PDF memastikan bahwa tabel muncul secara konsisten di setiap halaman, menyediakan tata letak yang seragam.