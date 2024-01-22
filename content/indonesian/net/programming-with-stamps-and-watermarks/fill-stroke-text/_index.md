---
title: Isi Teks Stroke Dalam File PDF
linktitle: Isi Teks Stroke Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mudah mengisi dan menguraikan teks dalam file PDF dengan Aspose.PDF untuk .NET.
type: docs
weight: 90
url: /id/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
Dalam tutorial ini, kami akan memandu Anda langkah demi langkah tentang cara mengisi dan menguraikan teks dalam file PDF menggunakan Aspose.PDF untuk .NET. Kami akan menunjukkan cara menggunakan kode sumber C# yang disediakan untuk menerapkan warna isian dan kerangka pada teks dalam file PDF.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Lingkungan pengembangan .NET yang terinstal.
- Pustaka Aspose.PDF untuk .NET diunduh dan direferensikan dalam proyek Anda.

## Langkah 2: Membuat Objek TextState

Langkah pertama adalah membuat objek TextState untuk meneruskan properti tingkat lanjut. Begini caranya:

```csharp
// Buat objek TextState untuk mentransfer properti tingkat lanjut
TextState ts = new TextState();

// Tetapkan warna kerangka
ts.StrokingColor = Color.Gray;

// Tentukan mode rendering teks
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Kode di atas membuat objek TextState baru dan mengatur warna kerangka serta cara teks dirender.

## Langkah 3: Memuat dokumen PDF

Sekarang objek TextState sudah siap, kita dapat memuat dokumen PDF di mana kita ingin menerapkan isian dan kerangka teks. Begini caranya:

```csharp
// Muat dokumen PDF sebagai masukan
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Kode di atas memuat dokumen PDF yang ada menggunakan kelas PdfFileStamp dari perpustakaan Aspose.PDF.Facades.

## Langkah 4: Tambahkan Isian dan Goresan ke Teks

Sekarang setelah dokumen PDF dimuat, kita dapat menambahkan isian dan kerangka ke teks. Begini caranya:

```csharp
// Buat stempel (Stamp) dengan teks dan properti yang ditentukan
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

// Tambahkan stempel ke dokumen
fileStamp.AddStamp(stamp);
```

Kode di atas membuat Stempel dengan teks tertentu dan properti Isian dan Goresan yang ditentukan.

## Langkah 5: Simpan dokumen keluaran

Setelah stempel teks ditambahkan, kita dapat menyimpan dokumen PDF yang dimodifikasi. Begini caranya:

```csharp
// Simpan dokumen yang diubah
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Kode di atas menyimpan dokumen PDF yang diedit ke direktori yang ditentukan.

### Contoh kode sumber untuk Isi Teks Stroke menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat objek TextState untuk mentransfer properti tingkat lanjut
TextState ts = new TextState();

// Atur warna untuk goresan
ts.StrokingColor = Color.Gray;

// Setel mode rendering teks
ts.RenderingMode = TextRenderingMode.StrokeText;

// Muat dokumen PDF masukan
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Ikat TextState
stamp.BindTextState(ts);

// Tetapkan X,Y asal
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Tambahkan Stempel
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Kesimpulan

Selamat! Anda telah mempelajari cara mengisi dan menguraikan teks dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Sekarang Anda dapat menerapkan pengetahuan ini untuk menyesuaikan warna isian dan kerangka dalam dokumen PDF Anda.

### FAQ untuk mengisi teks guratan dalam file PDF

#### T: Apa yang dimaksud dengan mengisi dan menguraikan teks dalam dokumen PDF, dan kapan saya perlu melakukannya?

J: Mengisi dan menguraikan teks dalam dokumen PDF melibatkan penerapan warna pada bagian dalam karakter teks (isian) dan pada batas di sekitar teks (garis besar). Ini dapat digunakan untuk menyempurnakan tampilan visual teks, membuat penekanan, atau menyorot konten tertentu dalam PDF.

#### T: Bagaimana kode sumber C# yang disediakan menyelesaikan pengisian dan kerangka teks dalam file PDF?

 J: Kode sumber yang disediakan menunjukkan cara membuat a`TextState` objek untuk menentukan properti teks tingkat lanjut, seperti warna garis dan mode rendering. Kemudian menggunakan Aspose.PDF.Facades untuk memuat dokumen PDF yang ada, membuat stempel berisi teks dengan properti isian dan guratan tertentu, dan menambahkan stempel ke dokumen.

####  T: Apa tujuan dari`TextState` object in the code?

 J: Itu`TextState`objek digunakan untuk menentukan properti teks tingkat lanjut, termasuk warna garis teks (guratan) dan mode rendering. Ini memungkinkan Anda untuk menyesuaikan bagaimana teks muncul dalam hal guratan dan isian.

#### T: Dapatkah saya menerapkan warna isian dan kerangka yang berbeda pada bagian berbeda pada teks yang sama?

 A: Ya, Anda dapat memodifikasi kode untuk membuat kode yang berbeda`TextState` objek dengan warna isian dan garis luar yang berbeda dan menerapkannya ke bagian teks tertentu menggunakan yang terpisah`Stamp` objek.

#### T: Bisakah saya menerapkan warna isian dan kerangka pada teks yang sudah ada di dokumen PDF?

 J: Ya, Anda dapat menggunakan prinsip serupa untuk menerapkan warna isian dan kerangka pada teks yang ada di dokumen PDF dengan memilih objek teks yang sesuai dan menambahkannya sebagai stempel dengan teks yang diinginkan.`TextState` properti.

#### T: Bagaimana cara menyesuaikan opacity dan pencampuran teks yang diisi dan digariskan?

 J: Kode yang diberikan memungkinkan Anda mengatur opasitas dan sifat pencampuran stempel menggunakan`Opacity` Dan`BlendingSpace`properti, masing-masing. Anda dapat menyesuaikan nilai-nilai ini untuk mencapai efek visual yang diinginkan.

#### T: Bagaimana cara menerapkan warna isian dan kerangka yang berbeda pada beberapa stempel dalam dokumen PDF yang sama?

 A: Anda dapat membuat banyak`TextState` objek dengan warna isi dan garis luar yang berbeda, lalu buat terpisah`Stamp` objek untuk setiap kumpulan teks dengan warna berbeda. Tambahkan prangko ini ke dokumen PDF yang sama menggunakan`PdfFileStamp` kelas.

#### T: Bisakah saya menggunakan font selain Arial untuk teks yang digariskan dan diisi?

 A: Ya, Anda dapat mengubah font dengan memodifikasi parameter nama font di`FormattedText` konstruktor saat membuat stempel. Anda dapat menggunakan font apa pun yang tersedia di sistem Anda.

#### T: Bagaimana cara mengubah sudut rotasi teks yang digariskan dan diisi?

 A: Kode yang diberikan memungkinkan Anda mengatur sudut putaran stempel menggunakan`Rotation` Properti. Anda dapat menyesuaikan properti ini untuk menentukan sudut rotasi teks yang diinginkan.

#### T: Bagaimana cara mengontrol posisi dan ukuran teks yang digariskan dan diisi pada halaman?

J: Anda dapat menggunakan`SetOrigin` metode`Stamp` objek untuk mengatur koordinat X dan Y posisi prangko pada halaman. Selain itu, Anda dapat menyesuaikan ukuran font di`FormattedText` konstruktor untuk mengontrol ukuran teks.