---
title: Isi Teks Goresan Dalam File PDF
linktitle: Isi Teks Goresan Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mudah mengisi dan menguraikan teks dalam berkas PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 90
url: /id/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara mengisi dan menguraikan teks dalam berkas PDF menggunakan Aspose.PDF untuk .NET. Kami akan menunjukkan kepada Anda cara menggunakan kode sumber C# yang disediakan untuk menerapkan warna isian dan garis luar pada teks dalam berkas PDF.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal.
- Pustaka Aspose.PDF untuk .NET diunduh dan dirujuk dalam proyek Anda.

## Langkah 2: Membuat Objek TextState

Langkah pertama adalah membuat objek TextState untuk meneruskan properti lanjutan. Berikut caranya:

```csharp
// Buat objek TextState untuk mentransfer properti lanjutan
TextState ts = new TextState();

// Mengatur warna garis besar
ts.StrokingColor = Color.Gray;

// Tentukan mode rendering teks
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Kode di atas membuat objek TextState baru dan mengatur warna garis serta bagaimana teks ditampilkan.

## Langkah 3: Memuat dokumen PDF

Sekarang objek TextState sudah siap, kita dapat memuat dokumen PDF tempat kita ingin menerapkan isian dan garis teks. Berikut caranya:

```csharp
// Muat dokumen PDF sebagai input
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Kode di atas memuat dokumen PDF yang ada menggunakan kelas PdfFileStamp dari pustaka Aspose.PDF.Facades.

## Langkah 4: Tambahkan Isian dan Goresan ke Teks

Sekarang setelah dokumen PDF dimuat, kita dapat menambahkan isian dan garis luar ke teks. Berikut caranya:

```csharp
// Buat prangko (Stempel) dengan teks dan properti yang ditentukan
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Ikat objek TextState
stamp.BindTextState(ts);

// Tetapkan asal X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Tambahkan prangko ke dokumen
fileStamp.AddStamp(stamp);
```

Kode di atas membuat Stamp dengan teks tertentu dan properti Fill dan Stroke yang ditentukan.

## Langkah 5: Simpan dokumen keluaran

Setelah stempel teks ditambahkan, kita dapat menyimpan dokumen PDF yang dimodifikasi. Berikut caranya:

```csharp
// Simpan dokumen yang dimodifikasi
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Kode di atas menyimpan dokumen PDF yang telah diedit ke direktori yang ditentukan.

### Contoh kode sumber untuk Fill Stroke Text menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat objek TextState untuk mentransfer properti lanjutan
TextState ts = new TextState();

// Atur warna untuk goresan
ts.StrokingColor = Color.Gray;

// Mengatur mode rendering teks
ts.RenderingMode = TextRenderingMode.StrokeText;

// Memuat dokumen PDF masukan
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Mengikat TextState
stamp.BindTextState(ts);

// Tetapkan asal X,Y
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Tambahkan Prangko
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Kesimpulan

Selamat! Anda telah mempelajari cara mengisi dan menguraikan teks dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Sekarang Anda dapat menerapkan pengetahuan ini untuk menyesuaikan warna isian dan garis luar dalam dokumen PDF Anda.

### FAQ untuk mengisi teks goresan pada file PDF

#### T: Apa artinya mengisi dan menguraikan teks dalam dokumen PDF, dan kapan saya perlu melakukannya?

A: Mengisi dan menguraikan teks dalam dokumen PDF melibatkan penerapan warna pada bagian dalam karakter teks (isi) dan pada batas di sekitar teks (garis besar). Ini dapat digunakan untuk meningkatkan tampilan visual teks, memberi penekanan, atau menyorot konten tertentu dalam PDF.

#### T: Bagaimana kode sumber C# yang disediakan menyelesaikan pengisian dan penguraian teks dalam berkas PDF?

 A: Kode sumber yang diberikan menunjukkan cara membuat`TextState` objek untuk menentukan properti teks tingkat lanjut, seperti warna garis luar dan mode render. Kemudian menggunakan Aspose.PDF.Facades untuk memuat dokumen PDF yang ada, membuat stempel yang berisi teks dengan properti isian dan goresan yang ditentukan, dan menambahkan stempel ke dokumen.

####  T: Apa tujuan dari`TextState` object in the code?

 Sebuah:`TextState`Objek digunakan untuk menentukan properti teks tingkat lanjut, termasuk warna garis luar teks (goresan) dan mode render. Objek ini memungkinkan Anda untuk menyesuaikan tampilan teks dalam hal goresan dan isian.

#### T: Dapatkah saya menerapkan warna isian dan garis luar yang berbeda pada bagian yang berbeda dalam teks yang sama?

 A: Ya, Anda dapat mengubah kode untuk membuat yang berbeda`TextState` objek dengan warna isian dan garis luar yang berbeda dan menerapkannya ke bagian teks tertentu menggunakan`Stamp` objek.

#### T: Dapatkah saya menerapkan warna isian dan garis luar pada teks yang sudah ada dalam dokumen PDF?

 A: Ya, Anda dapat menggunakan prinsip serupa untuk menerapkan warna isian dan garis luar pada teks yang ada dalam dokumen PDF dengan memilih objek teks yang sesuai dan menambahkannya sebagai stempel dengan warna yang diinginkan.`TextState` properti.

#### T: Bagaimana cara menyesuaikan opasitas dan pencampuran teks yang diisi dan digaris?

 A: Kode yang diberikan memungkinkan Anda untuk mengatur opacity dan properti pencampuran prangko menggunakan`Opacity` Dan`BlendingSpace`properti, masing-masing. Anda dapat menyesuaikan nilai-nilai ini untuk mencapai efek visual yang diinginkan.

#### T: Bagaimana cara menerapkan warna isian dan garis luar yang berbeda pada beberapa prangko dalam dokumen PDF yang sama?

 A: Anda dapat membuat beberapa`TextState` objek dengan warna isian dan garis luar yang berbeda, lalu buat yang terpisah`Stamp` objek untuk setiap set teks dengan warna yang berbeda. Tambahkan prangko ini ke dokumen PDF yang sama menggunakan`PdfFileStamp` kelas.

#### T: Dapatkah saya menggunakan jenis huruf selain Arial untuk teks yang digaris bawahi dan diisi?

 A: Ya, Anda dapat mengubah font dengan mengubah parameter nama font di`FormattedText` konstruktor saat membuat prangko. Anda dapat menggunakan font apa pun yang tersedia di sistem Anda.

#### T: Bagaimana cara mengubah sudut rotasi teks yang digaris dan diisi?

 A: Kode yang diberikan memungkinkan Anda untuk mengatur sudut rotasi prangko menggunakan`Rotation` properti. Anda dapat menyesuaikan properti ini untuk menentukan sudut rotasi yang diinginkan untuk teks.

#### T: Bagaimana cara mengontrol posisi dan ukuran teks yang digaris bawahi dan diisi pada halaman?

 A: Kamu bisa menggunakan`SetOrigin` metode dari`Stamp` objek untuk mengatur koordinat X dan Y posisi prangko di halaman. Selain itu, Anda dapat menyesuaikan ukuran font di`FormattedText` konstruktor untuk mengontrol ukuran teks.