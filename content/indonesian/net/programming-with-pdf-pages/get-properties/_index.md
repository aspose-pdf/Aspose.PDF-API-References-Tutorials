---
title: Dapatkan Properti PDF
linktitle: Dapatkan Properti PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Panduan langkah demi langkah untuk mendapatkan properti PDF seperti dimensi kotak dan rotasi menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 100
url: /id/net/programming-with-pdf-pages/get-properties/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk mendapatkan properti PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# yang disertakan dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan mengetahui cara mengakses berbagai properti halaman PDF seperti kotak seni, kotak potong, kotak potong, dll., menggunakan Aspose.PDF untuk .NET.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#
- Aspose.PDF untuk .NET terinstal di lingkungan pengembangan Anda

## Langkah 1: Atur direktori dokumen
Pertama, Anda perlu mengatur jalur ke direktori dokumen Anda. Ini adalah lokasi berkas PDF yang propertinya ingin Anda dapatkan. Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Buka dokumen PDF
 Selanjutnya, Anda perlu membuka dokumen PDF menggunakan`Document` kelas Aspose.PDF. Pastikan untuk menentukan jalur yang benar ke berkas PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Langkah 3: Akses Koleksi Halaman
 Sekarang Anda dapat mengakses koleksi halaman dokumen menggunakan`Pages` milik`pdfDocument` obyek.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Langkah 4: Buka halaman tertentu
Kemudian Anda dapat melompat ke halaman tertentu menggunakan indeks halaman dalam koleksi. Dalam contoh di bawah ini, kita mengakses halaman kedua (indeks 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Langkah 5: Dapatkan properti halaman
 Sekarang Anda bisa mendapatkan properti yang berbeda dari halaman PDF, seperti kotak seni, kotak potong, kotak potong, dll., dengan menggunakan properti yang sesuai dari`pdfPage` obyek.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### Contoh kode sumber untuk Mendapatkan Properti menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Dapatkan koleksi halaman
PageCollection pageCollection = pdfDocument.Pages;
// Dapatkan halaman tertentu
Page pdfPage = pageCollection[1];
// Dapatkan properti halaman
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## Kesimpulan
Selamat! Anda telah berhasil memperoleh properti PDF menggunakan Aspose.PDF untuk .NET. Anda telah mempelajari cara membuka dokumen PDF, menavigasi ke halaman tertentu, dan memperoleh berbagai properti halaman, seperti kotak dimensi dan rotasi. Kini Anda dapat menggunakan informasi ini untuk menyesuaikan penanganan berkas PDF berdasarkan propertinya.

Pastikan untuk memeriksa dokumentasi resmi Aspose.PDF untuk .NET untuk informasi lebih lanjut tentang fitur lanjutan dan kemungkinan penyesuaian.

### Pertanyaan yang Sering Diajukan

#### T: Bagaimana cara mendapatkan properti PDF menggunakan Aspose.PDF untuk .NET?

A: Untuk mendapatkan properti PDF menggunakan Aspose.PDF untuk .NET, Anda dapat mengikuti langkah-langkah berikut:

1. Tetapkan direktori dokumen dengan menentukan jalur ke file PDF yang propertinya ingin Anda ambil.
2.  Buka dokumen PDF menggunakan`Document` kelas Aspose.PDF, menyediakan jalur yang benar ke berkas PDF.
3.  Akses koleksi halaman dokumen menggunakan`Pages` milik`pdfDocument` obyek.
4. Lompat ke halaman tertentu menggunakan indeks halaman dalam koleksi (pengindeksan dimulai dari 1).
5.  Dapatkan properti yang berbeda dari halaman PDF, seperti ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number, dan Rotation, dengan menggunakan properti yang sesuai dari`pdfPage` obyek.

#### T: Apa saja properti berbeda dari halaman PDF yang dapat saya ambil menggunakan Aspose.PDF untuk .NET?

A: Anda dapat mengambil berbagai properti halaman PDF menggunakan Aspose.PDF untuk .NET, seperti:

- ArtBox: Mewakili dimensi karya seni halaman.
- BleedBox: Mewakili dimensi bleed halaman.
- CropBox: Mewakili dimensi konten halaman yang terlihat setelah pemotongan.
- MediaBox: Mewakili dimensi media fisik halaman.
- TrimBox: Mewakili dimensi konten halaman yang dipangkas.
- Persegi Panjang: Mewakili dimensi kotak pembatas halaman.
- Nomor Halaman: Mewakili nomor halaman dalam dokumen.
- Putar: Mewakili sudut rotasi halaman.

#### T: Bagaimana cara mengakses halaman tertentu dalam dokumen PDF untuk mengambil propertinya?

 A: Untuk mengakses halaman tertentu dalam dokumen PDF dan mengambil propertinya, Anda dapat menggunakan`Pages` milik`pdfDocument` objek untuk mengakses koleksi halaman dokumen. Kemudian, Anda dapat menggunakan indeks halaman dalam koleksi untuk melompat ke halaman yang diinginkan. Misalnya, untuk mengakses halaman kedua, Anda dapat menggunakan`pdfDocument.Pages[1]` (pengindeksan dimulai dari 1).

#### T: Dapatkah saya melakukan operasi pada properti yang diambil, seperti memodifikasi atau mengubah ukuran kotak halaman?

A: Ya, setelah Anda mengambil properti halaman PDF menggunakan Aspose.PDF for .NET, Anda dapat melakukan berbagai operasi pada properti tersebut. Misalnya, Anda dapat mengubah dimensi kotak halaman, memutar halaman, atau menggunakan informasi yang diambil untuk pemrosesan dan manipulasi dokumen PDF secara khusus.

#### T: Apakah Aspose.PDF untuk .NET mendukung ekstraksi properti dari file PDF yang dienkripsi atau dilindungi kata sandi?

A: Ya, Aspose.PDF untuk .NET mendukung ekstraksi properti dari file PDF yang dienkripsi atau dilindungi kata sandi. Selama Anda memberikan kata sandi yang benar untuk membuka dokumen PDF, Anda dapat mengakses dan mengambil propertinya menggunakan pendekatan yang sama yang ditunjukkan dalam tutorial.