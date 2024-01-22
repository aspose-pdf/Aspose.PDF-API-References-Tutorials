---
title: Gambar dan Nomor Halaman pada Bagian Header Footer Sebaris
linktitle: Gambar dan Nomor Halaman pada Bagian Header Footer Sebaris
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan gambar dan nomor halaman di header dan footer menggunakan paragraf sebaris dengan Aspose.PDF untuk .NET.
type: docs
weight: 120
url: /id/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara menambahkan gambar dan nomor halaman di bagian header dan footer dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menggunakan kode sumber C# yang disediakan untuk membuat halaman, mengatur header dan footer, menambahkan gambar dan teks menggunakan paragraf sebaris di header dokumen PDF.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal.
- Pustaka Aspose.PDF untuk .NET diunduh dan direferensikan dalam proyek Anda.

## Langkah 2: Membuat Dokumen dan Halaman PDF

Langkah pertama adalah membuat objek Dokumen baru dan halaman di dokumen PDF. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat objek Dokumen baru
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Buat halaman di dokumen
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Kode di atas membuat objek Dokumen baru dan halaman kosong di dokumen PDF.

## Langkah 3: Menambahkan header dengan gambar dan teks sebaris

Sekarang halaman telah dibuat, kita dapat menambahkan bagian header dengan gambar dan teks menggunakan paragraf sebaris. Begini caranya:

```csharp
// Buat bagian header
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Atur tajuk halaman
page. Header = header;

// Buat objek TextFragment untuk teks sebaris pertama
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Tentukan warna teks
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Buat objek Gambar untuk gambar tersebut
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Tetapkan jalur gambar
image1.File = dataDir + "aspose-logo.jpg";

// Tentukan dimensi gambar
image1.FixWidth = 50;
image1.FixHeight = 20;

// Tunjukkan bahwa teks sebaris pertama adalah gambar
image1.IsInLineParagraph = true;

// Buat teks sebaris kedua
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Tambahkan item ke header
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

Kode di atas membuat bagian header, menyetel header halaman dengan bagian ini, menambahkan TextFragment dengan teks sebaris dan objek Gambar sebaris.

## Langkah 4: Menyimpan dokumen PDF yang dimodifikasi

Setelah header dengan gambar dan teks sebaris ditambahkan, kita dapat menyimpan dokumen PDF yang dimodifikasi. Begini caranya:

```csharp
// Simpan dokumen PDF yang dimodifikasi
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Kode di atas menyimpan dokumen PDF yang diedit ke direktori yang ditentukan.

### Contoh kode sumber untuk Gambar dan Nomor Halaman di Header Footersection Inline menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat instance objek Dokumen dengan memanggil konstruktor kosongnya
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Buat halaman di objek Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Buat Bagian Header dokumen
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Atur header untuk file PDF
page.Header = header;

// Buat objek Teks
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Tentukan warnanya
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Buat objek gambar di bagian tersebut
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Tetapkan jalur file gambar
image1.File = dataDir + "aspose-logo.jpg";

// Atur informasi lebar gambar
image1.FixWidth = 50;
image1.FixHeight = 20;

// Tunjukkan InlineParagraph seg1 adalah sebuah gambar.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Simpan Pdfnya
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Kesimpulan

Selamat! Anda telah mempelajari cara menambahkan gambar dan nomor halaman di bagian header dan footer dokumen PDF menggunakan paragraf sebaris dengan Aspose.PDF untuk .NET. Anda sekarang dapat menyesuaikan header dan footer dokumen PDF Anda secara fleksibel.

### FAQ

#### T: Apa keuntungan menggunakan paragraf sebaris untuk menambahkan gambar dan teks ke header dokumen PDF?

J: Menggunakan paragraf sebaris memungkinkan Anda mengintegrasikan gambar dan teks dengan mulus dalam paragraf yang sama, memberikan kontrol yang tepat atas penempatan dan pemformatannya. Metode ini sangat berguna untuk membuat header khusus dengan elemen visual.

#### T: Bagaimana kode sumber C# yang disediakan menghasilkan paragraf sebaris untuk header dalam dokumen PDF?

J: Kode yang diberikan menunjukkan cara membuat dokumen PDF, menambahkan halaman, dan menyesuaikan header menggunakan paragraf sebaris. Ia menambahkan TextFragment dengan teks sebaris, gambar sebaris, dan TextFragment sebaris lainnya.

#### T: Bagaimana cara menentukan warna teks sebaris di header?

 A: Warna teks sebaris ditentukan menggunakan`ForegroundColor` properti dari`TextState` dari`TextFragment` obyek.

#### T: Dapatkah saya menyesuaikan dimensi gambar sebaris di header?

 A: Ya, Anda dapat mengatur dimensi gambar sebaris menggunakan`FixWidth` Dan`FixHeight` properti dari`Image` obyek. Ini memungkinkan Anda mengontrol lebar dan tinggi gambar di dalam header.

#### T: Bisakah saya menyertakan elemen sebaris tambahan, seperti hyperlink atau gaya font berbeda, di header?

 J: Ya, Anda dapat menyertakan elemen inline tambahan di header dengan membuat lebih banyak`TextFragment` atau`Image` objek dengan properti yang diinginkan. Ini memungkinkan Anda untuk menyesuaikan header lebih lanjut, termasuk hyperlink, gaya font yang berbeda, atau elemen visual lainnya.

#### T: Bagaimana cara memastikan bahwa gambar dan teks sebaris tetap selaras dan diformat dengan benar di berbagai perangkat dan pemirsa?

J: Aspose.PDF untuk .NET memastikan bahwa gambar dan teks sebaris disejajarkan dan diformat dengan benar, sehingga menghasilkan tampilan yang konsisten di berbagai perangkat dan penampil PDF.

#### T: Dapatkah saya menerapkan paragraf sebaris ke bagian footer juga?

 A: Ya, Anda dapat menerapkan teknik yang sama yaitu menggunakan paragraf sebaris pada bagian footer dengan membuat a`Footer` objek dan menambahkan elemen sebaris seperti teks dan gambar ke dalamnya.

#### T: Apakah mungkin untuk menggabungkan paragraf sebaris dengan metode penyesuaian header atau footer lainnya?

J: Ya, Anda dapat menggabungkan paragraf sebaris dengan metode penyesuaian header atau footer lain yang disediakan oleh Aspose.PDF untuk .NET untuk membuat desain header atau footer yang lebih kompleks dan disesuaikan.

#### T: Dapatkah saya menghapus atau menghapus elemen sebaris dari header jika diperlukan?

 J: Ya, Anda dapat menghapus atau menghapus elemen sebaris dengan memodifikasi kontennya`HeaderFooter` keberatan dan menghapus masing-masing paragraf sebaris.

#### T: Bagaimana cara menerapkan paragraf sebaris ke halaman tertentu di dokumen PDF?

 A: Untuk menerapkan paragraf sebaris pada halaman tertentu, Anda dapat membuatnya terpisah`HeaderFooter` objek untuk setiap halaman dan menugaskannya menggunakan`Header` milik masing-masing`Aspose.Pdf.Page` objek.