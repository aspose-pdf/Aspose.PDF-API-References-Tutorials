---
title: Tambahkan Gambar di Sel Tabel
linktitle: Tambahkan Gambar di Sel Tabel
second_title: Referensi API Aspose.PDF untuk .NET
description: Tambahkan gambar dalam sel tabel dengan Aspose.PDF untuk .NET, panduan langkah demi langkah untuk manipulasi gambar yang tepat dalam dokumen PDF.
type: docs
weight: 10
url: /id/net/programming-with-tables/add-image-in-a-table-cell/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses penambahan gambar ke sel tabel menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan cara untuk mencapai fungsi ini. Dengan mengikuti langkah-langkah yang diuraikan di bawah ini, Anda akan dapat memasukkan gambar ke dalam sel tabel secara efektif.

Sebelum kita masuk ke kode, pastikan Anda telah menginstal pustaka Aspose.PDF untuk .NET dan merujuknya dalam proyek Anda.

## Langkah 1: Menyiapkan Dokumen

 Untuk memulai, kita perlu membuat instance baru dari`Document` kelas dari namespace Aspose.Pdf. Kelas ini mewakili dokumen PDF.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Membuat instance objek Dokumen
Document pdfDocument = new Document();
```

## Langkah 2: Membuat Halaman

Selanjutnya, kita perlu menambahkan halaman ke dokumen PDF. Halaman berfungsi sebagai wadah untuk tabel dan elemen lainnya.

```csharp
// Buat halaman dalam dokumen pdf
Page sec1 = pdfDocument.Pages.Add();
```

## Langkah 3: Menambahkan Tabel

 Pada langkah ini, kita akan membuat tabel dengan membuat instance`Table` kelas dari namespace Aspose.Pdf.

```csharp
// Membuat instance objek tabel
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Langkah 4: Mengatur Batas Sel Default

 Untuk memastikan konsistensi, kita dapat mengatur batas sel default menggunakan`DefaultCellBorder`properti tabel`BorderInfo` obyek.

```csharp
// Mengatur batas sel default menggunakan objek BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Langkah 5: Mengatur Lebar Kolom

 Untuk menentukan lebar setiap kolom pada tabel, kita dapat mengatur`ColumnWidths` properti. Tentukan lebar sebagai string dengan nilai yang dipisahkan spasi.

```csharp
// Diatur dengan lebar kolom tabel
tab1.ColumnWidths = "100 100 120";
```

## Langkah 6: Menambahkan Gambar ke Sel Tabel

Sekarang tibalah bagian yang menarik, yaitu menambahkan gambar ke sel tabel. Untuk melakukannya, kita akan mengikuti langkah-langkah berikut:

## Langkah 6.1: Membuat Objek Gambar

 Buat contoh dari`Image` kelas dari namespace Aspose.Pdf. Atur`File` properti ke jalur berkas gambar yang ingin Anda tambahkan.

```csharp
// Membuat objek Gambar
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## Langkah 6.2: Membuat Baris dan Sel

Untuk menambahkan gambar ke tabel, pertama-tama kita perlu membuat baris dan sel yang diperlukan.

```csharp
// Buat baris di tabel
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// Tambahkan sel teks ke baris
row1.Cells.Add("Sample text in cell");

// Tambahkan sel yang berisi gambar
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## Langkah 6.3: Menambahkan Gambar ke Sel Tabel

Terakhir, kita dapat menambahkan gambar ke sel tabel dengan menambahkannya sebagai paragraf di dalam sel.

```csharp
// Tambahkan gambar ke sel tabel
cell2.Paragraphs.Add(img);
```

## Langkah 6.4: Menambahkan Sel Tambahan

Setelah menambahkan sel gambar, kita dapat menambahkan lebih banyak sel ke baris jika diperlukan.

```csharp
//Tambahkan sel lain ke baris
row1.Cells.Add("Previous cell with image");

// Sesuaikan perataan vertikal sel ketiga
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Langkah 7: Menyimpan Dokumen

 Terakhir, kita dapat menyimpan dokumen yang dimodifikasi ke lokasi tertentu menggunakan`Save` metode.

```csharp
// Simpan Dokumen
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Selamat! Anda telah berhasil mempelajari cara menambahkan gambar ke sel tabel menggunakan Aspose.PDF untuk .NET. Jangan ragu untuk menjelajahi opsi penyesuaian lebih lanjut dan mengintegrasikan fungsionalitas ini ke dalam proyek Anda.

### Contoh kode sumber untuk menambahkan gambar dalam sel tabel menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Membuat instance objek Dokumen
Document pdfDocument = new Document();
// Buat halaman dalam dokumen pdf
Page sec1 = pdfDocument.Pages.Add();
// Membuat instance objek tabel
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Tambahkan tabel dalam kumpulan paragraf halaman yang diinginkan
sec1.Paragraphs.Add(tab1);
// Mengatur batas sel default menggunakan objek BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Diatur dengan lebar kolom tabel
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Buat baris dalam tabel dan kemudian sel dalam baris
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Tambahkan sel yang berisi gambar
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// Tambahkan gambar ke sel tabel
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// Simpan Dokumen
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Kesimpulan

Dalam tutorial ini, kami membahas panduan langkah demi langkah tentang cara menambahkan gambar ke sel tabel menggunakan Aspose.PDF untuk .NET. Kami mulai dengan menyiapkan dokumen, membuat halaman, dan menambahkan tabel. Kemudian, kami mengatur batas sel dan lebar kolom default. Kami menunjukkan cara menambahkan gambar ke sel tabel dan menyesuaikan perataan vertikal sel. Terakhir, kami menyimpan dokumen yang dimodifikasi. Dengan mengikuti langkah-langkah ini, Anda dapat menyempurnakan dokumen PDF Anda dengan gambar di sel tabel secara efisien.

### Pertanyaan yang Sering Diajukan

#### T: Dapatkah saya menambahkan beberapa gambar ke sel yang berbeda dalam tabel yang sama menggunakan Aspose.PDF untuk .NET?

A: Ya, Anda dapat menambahkan beberapa gambar ke sel yang berbeda dalam tabel yang sama menggunakan Aspose.PDF for .NET. Cukup ikuti proses yang sama yang ditunjukkan dalam tutorial untuk setiap gambar yang ingin Anda tambahkan ke tabel.

#### T: Dapatkah saya menyesuaikan ukuran dan posisi gambar dalam sel tabel?

 A: Ya, Anda dapat menyesuaikan ukuran dan posisi gambar di dalam sel tabel dengan menyesuaikan properti`Image`objek. Anda dapat mengatur lebar dan tinggi gambar, serta perataan dalam sel.

#### T: Dapatkah saya menambahkan gambar ke tabel dengan jumlah baris dan kolom yang dinamis?

A: Ya, Anda dapat menambahkan gambar ke tabel dengan jumlah baris dan kolom yang dinamis. Aspose.PDF untuk .NET memberikan fleksibilitas dalam membuat tabel dengan dimensi yang bervariasi. Anda dapat menambahkan baris dan sel sesuai kebutuhan, lalu menambahkan gambar ke sel tertentu sesuai kebutuhan.

#### T: Format gambar apa yang didukung oleh Aspose.PDF untuk .NET untuk menambahkan gambar ke sel tabel?

J: Aspose.PDF untuk .NET mendukung berbagai format gambar, termasuk JPEG, PNG, GIF, BMP, dan TIFF. Anda dapat menggunakan gambar dalam format apa pun untuk menambahkannya ke sel tabel.

#### T: Dapatkah saya menambahkan gambar ke tabel dalam dokumen PDF yang ada?

A: Ya, Anda dapat menambahkan gambar ke tabel dalam dokumen PDF yang sudah ada menggunakan Aspose.PDF for .NET. Cukup muat dokumen yang sudah ada dan ikuti langkah yang sama untuk menambahkan gambar ke tabel seperti yang ditunjukkan dalam tutorial.