---
title: Gambar dan Nomor Halaman di Bagian Header dan Footer
linktitle: Gambar dan Nomor Halaman di Bagian Header dan Footer
second_title: Referensi API Aspose.PDF untuk .NET
description: Cari tahu cara menambahkan gambar dan nomor halaman di header dan footer dokumen PDF dengan Aspose.
type: docs
weight: 110
url: /id/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara menambahkan gambar dan nomor halaman di bagian header dan footer dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menunjukkan kepada Anda cara menggunakan kode sumber C# yang disediakan untuk membuat halaman, mengatur header dan footer, menambahkan gambar ke header dan teks dengan nomor halaman ke footer dokumen PDF.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal.
- Pustaka Aspose.PDF untuk .NET diunduh dan dirujuk dalam proyek Anda.

## Langkah 2: Membuat Dokumen dan Halaman PDF

Langkah pertama adalah membuat objek Dokumen baru dan halaman dalam dokumen PDF. Berikut caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat objek Dokumen baru
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Buat halaman dalam dokumen
Aspose.Pdf.Page page = doc.Pages.Add();
```

Kode di atas membuat objek Dokumen baru dan halaman kosong dalam dokumen PDF.

## Langkah 3: Menambahkan header dengan gambar

Setelah halaman dibuat, kita dapat menambahkan bagian header dengan gambar. Berikut caranya:

```csharp
// Buat bagian header
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Mengatur header halaman
page. Header = header;

// Membuat objek Gambar
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Tetapkan jalur gambar
image1.File = dataDir + "aspose-logo.jpg";

// Tambahkan gambar ke header halaman dokumen PDF
header.Paragraphs.Add(image1);
```

Kode di atas membuat bagian header, menetapkan header halaman dengan bagian ini, dan menambahkan gambar ke header.

## Langkah 4: Menambahkan footer dengan nomor halaman

Setelah header ditambahkan, kita dapat menambahkan bagian footer dengan nomor halaman. Berikut caranya:

```csharp
// Buat bagian footer
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Tentukan footer dokumen PDF
page. Footer = footer;

// Buat objek TextFragment
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// Tambahkan teks dengan nomor halaman ke footer dokumen PDF
footer.Paragraphs.Add(txt);
```

Kode di atas membuat bagian footer, mengatur footer halaman dengan bagian ini dan menambahkan TextFragment yang berisi teks "Halaman: ($p dari $P)"

  yang menampilkan nomor halaman.

## Langkah 5: Menyimpan dokumen PDF yang dimodifikasi

Setelah header dan footer ditambahkan, kita dapat menyimpan dokumen PDF yang telah dimodifikasi. Berikut caranya:

```csharp
// Simpan dokumen PDF yang dimodifikasi
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Kode di atas menyimpan dokumen PDF yang telah diedit ke direktori yang ditentukan.

### Contoh kode sumber untuk Gambar dan Nomor Halaman di bagian Header dan Footer menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Buat halaman di objek dokumen
Aspose.Pdf.Page page = doc.Pages.Add();

// Buat Bagian Header dokumen
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Mengatur header untuk file PDF
page.Header = header;

// Buat objek gambar di halaman
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Mengatur jalur file gambar
image1.File = dataDir + "aspose-logo.jpg";

// Tambahkan gambar ke halaman Header file Pdf
header.Paragraphs.Add(image1);

//Buat Bagian Footer dari dokumen
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Mengatur footer file PDF
page.Footer = footer;

// Membuat objek Teks
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Tambahkan teks ke bagian Header file Pdf
footer.Paragraphs.Add(txt);

// Simpan file Pdf
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Kesimpulan

Selamat! Anda telah mempelajari cara menambahkan gambar dan nomor halaman di bagian header dan footer dokumen PDF menggunakan Aspose.PDF for .NET. Sekarang Anda dapat menggunakan metode ini untuk menyesuaikan header dan footer di dokumen PDF Anda.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan menambahkan gambar dan nomor halaman di bagian header dan footer dokumen PDF?

J: Menambahkan gambar dan nomor halaman di bagian header dan footer dokumen PDF dapat meningkatkan daya tarik visual, pencitraan merek, dan elemen navigasinya. Gambar dapat mewakili logo, tanda air, atau elemen grafis apa pun, sementara nomor halaman membantu pengguna melacak kemajuan mereka dan menemukan halaman tertentu.

#### T: Bagaimana kode sumber C# yang disediakan membantu dalam menambahkan gambar dan nomor halaman ke header dan footer dokumen PDF?

A: Kode yang diberikan menunjukkan cara membuat dokumen PDF, menambahkan halaman, lalu menyesuaikan bagian header dan footer. Kode ini menunjukkan cara menambahkan gambar ke header dan fragmen teks dengan penomoran halaman ke footer.

#### T: Dapatkah saya menggunakan format gambar apa pun untuk header, dan bagaimana cara menentukan jalurnya?

 A: Ya, Anda dapat menggunakan berbagai format gambar (seperti JPEG, PNG, GIF, dll.) untuk gambar header. Jalur gambar ditentukan menggunakan`File` milik`Aspose.Pdf.Image` obyek.

#### T: Bagaimana cara menyesuaikan tampilan dan posisi gambar di bagian header?

 A: Anda dapat menyesuaikan tampilan dan posisi gambar dengan menyesuaikan properti`Aspose.Pdf.Image` objek sebelum menambahkannya ke bagian header. Misalnya, Anda dapat mengatur dimensi gambar, perataan, rotasi, opasitas, dll.

####  T: Apa tujuan dari`TextFragment` object used for the footer?

 Sebuah:`TextFragment` Objek digunakan untuk membuat dan memformat teks yang akan ditampilkan di bagian footer. Dalam kode yang diberikan, objek ini digunakan untuk menampilkan nomor halaman dan jumlah total halaman.

#### T: Dapatkah saya mengubah teks footer untuk menyertakan informasi atau format tambahan?

 A: Ya, Anda dapat mengubah teks footer dengan mengubah konten`TextFragment` objek. Anda dapat menambahkan teks tambahan, mengubah font, warna, dan format sesuai kebutuhan Anda.

#### T: Dapatkah saya menerapkan konten header dan footer yang berbeda pada halaman yang berbeda dalam dokumen PDF?

 A: Ya, Anda dapat menerapkan konten header dan footer yang berbeda ke halaman yang berbeda dengan membuat`HeaderFooter` objek dan menugaskannya ke halaman tertentu menggunakan`Header` Dan`Footer` properti dari`Aspose.Pdf.Page` obyek.

#### T: Bagaimana saya dapat menyesuaikan header dan footer lebih lanjut, seperti mengubah gaya font atau menambahkan elemen tambahan?

J: Anda dapat menyesuaikan header dan footer dengan menggunakan berbagai kelas dan properti yang disediakan oleh Aspose.PDF untuk .NET. Misalnya, Anda dapat menggunakan berbagai opsi pemformatan teks, menambahkan lebih banyak paragraf, gambar, atau bahkan tabel ke bagian header dan footer.

#### T: Dapatkah saya menghapus atau mengosongkan bagian header dan footer jika diperlukan?

A: Ya, Anda dapat menghapus atau membersihkan bagian header dan footer dengan mengatur`Header` Dan`Footer` properti dari`Aspose.Pdf.Page` keberatan terhadap`null`.

#### T: Bagaimana saya dapat memastikan bahwa gambar yang ditambahkan dan nomor halaman tetap konsisten di berbagai perangkat dan pemirsa?

A: Aspose.PDF untuk .NET menyediakan fungsionalitas untuk membuat dokumen PDF yang terstandarisasi dan konsisten, memastikan bahwa gambar yang ditambahkan dan nomor halaman akan muncul secara konsisten di berbagai perangkat dan penampil PDF.