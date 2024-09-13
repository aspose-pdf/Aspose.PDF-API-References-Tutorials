---
title: Terapkan Gaya Angka Dalam File PDF
linktitle: Terapkan Gaya Angka Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menerapkan gaya angka yang berbeda (angka Romawi, alfabet) ke judul dalam PDF menggunakan Aspose.PDF untuk .NET dengan panduan langkah demi langkah ini.
type: docs
weight: 10
url: /id/net/programming-with-headings/apply-number-style/
---
## Perkenalan

Pernahkah Anda merasa perlu menambahkan daftar bernomor cantik ke dokumen PDF Anda? Baik Anda sedang memformat dokumen hukum, laporan, atau presentasi, gaya penomoran yang tepat sangat penting untuk mengatur informasi. Dengan Aspose.PDF untuk .NET, Anda dapat menerapkan berbagai gaya penomoran ke judul berkas PDF Anda, sehingga menghasilkan dokumen yang terstruktur dengan baik dan profesional. 

## Prasyarat

Sebelum menyelami pengkodean, mari kita bahas apa saja yang Anda perlukan:

1. Aspose.PDF untuk .NET: Unduh versi terbaru Aspose.PDF dari[Di Sini](https://releases.aspose.com/pdf/net/).
2. Lingkungan Pengembangan: Pastikan Anda memiliki Visual Studio atau IDE lain yang kompatibel dengan .NET.
3. .NET Framework: Pastikan Anda telah menginstal .NET Framework 4.0 atau yang lebih tinggi.
4.  Lisensi: Anda dapat menggunakan lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/) atau jelajahi[uji coba gratis](https://releases.aspose.com/) pilihan.

## Paket Impor

Untuk memulai, pastikan Anda telah mengimpor namespace berikut ke proyek Anda:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Langkah 1: Menyiapkan Dokumen

Mari kita mulai dengan membuat dokumen PDF baru dan mengonfigurasi pengaturan halamannya. Kita akan mengatur ukuran halaman dan margin untuk mengontrol tata letak konten kita.

Penjelasan: Pada langkah ini, kami menyiapkan struktur dasar PDF, yang mencakup penentuan ukuran halaman, tinggi, dan margin untuk pemformatan yang konsisten.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// Mengatur dimensi dan margin halaman
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

Dengan melakukan ini, dokumen Anda akan memiliki ukuran halaman standar, setara dengan halaman 8,5 x 11 inci, dan margin 72 poin (atau 1 inci) di semua sisi.

## Langkah 2: Menambahkan Halaman ke PDF

Berikutnya, kita akan menambahkan halaman baru ke dokumen PDF di mana nantinya kita akan menerapkan gaya penomoran.

Penjelasan: Setiap PDF memerlukan halaman! Langkah ini menambahkan halaman kosong ke PDF dan mengatur marginnya agar sesuai dengan pengaturan tingkat dokumen.

```csharp
// Tambahkan halaman baru ke dokumen PDF
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
```

## Langkah 3: Buat Kotak Mengambang

FloatingBox memungkinkan Anda menempatkan konten (seperti teks atau judul) di dalam kotak yang berperilaku secara independen dari alur halaman. Ini berguna saat Anda menginginkan kontrol penuh atas tata letak konten Anda.

Penjelasan: Di sini, kita menyiapkan FloatingBox untuk menampung judul-judul yang akan menerapkan gaya angka.

```csharp
// Buat FloatingBox untuk konten terstruktur
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

## Langkah 4: Tambahkan Judul Pertama dengan Angka Romawi

Sekarang tibalah bagian yang menarik! Mari tambahkan judul pertama dengan penomoran angka Romawi kecil.

Penjelasan: Kami menerapkan gaya NumberingStyle.NumeralsRomanLowercase ke judul, yang akan menampilkan penomoran dalam angka Romawi (i, ii, iii, dst.).

```csharp
// Buat judul pertama dengan angka Romawi
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
```

## Langkah 5: Tambahkan Judul Angka Romawi Kedua

Untuk tujuan demonstrasi, mari tambahkan judul angka Romawi kedua, tetapi kali ini kita akan mulai dari 13.

Penjelasan: Properti StartNumber memungkinkan Anda memulai penomoran dari angka khusus—dalam kasus ini, kita mulai dari 13.

```csharp
// Buat judul kedua dimulai dengan angka Romawi 13
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
```

## Langkah 6: Tambahkan Judul dengan Penomoran Alfabet

Untuk variasi, mari tambahkan judul ketiga, tetapi kali ini kita akan menggunakan penomoran alfabet dalam huruf kecil (a, b, c, dst.).

Penjelasan: Mengubah NumberingStyle menjadi LettersLowercase memungkinkan kita menerapkan penomoran alfabetis pada judul kita.

```csharp
// Buat judul dengan penomoran alfabet
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

## Langkah 7: Menyimpan PDF

Akhirnya, setelah menerapkan semua judul dan gaya nomor, mari simpan file PDF ke direktori yang Anda inginkan.

Penjelasan: Langkah ini menyimpan berkas PDF yang berisi semua judul yang diformat dengan gaya penomoran yang diterapkan.

```csharp
// Simpan dokumen PDF
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);
```

## Kesimpulan

Nah, itu dia! Anda telah berhasil menerapkan gaya penomoran—angka Romawi dan alfabet—pada judul dalam file PDF menggunakan Aspose.PDF untuk .NET. Fleksibilitas yang disediakan oleh Aspose.PDF untuk mengendalikan tata letak halaman, gaya penomoran, dan posisi konten memberi Anda seperangkat alat yang hebat untuk membuat dokumen PDF yang terorganisasi dengan baik dan profesional.

## Pertanyaan yang Sering Diajukan

### Dapatkah saya menerapkan gaya angka yang berbeda pada dokumen PDF yang sama?  
Ya, Aspose.PDF untuk .NET memungkinkan Anda mencampur berbagai gaya penomoran seperti angka Romawi, angka Arab, dan penomoran alfabet dalam dokumen yang sama.

### Bagaimana saya dapat menyesuaikan nomor awal untuk judul?  
 Anda dapat mengatur nomor awal untuk judul apa pun dengan menggunakan`StartNumber` milik.

### Apakah ada cara untuk mengatur ulang urutan penomoran?  
Ya, Anda dapat mengatur ulang penomoran dengan menyesuaikan`StartNumber` properti untuk setiap judul.

### Dapatkah saya menerapkan gaya tebal atau miring pada judul selain penomoran?  
 Tentu saja! Anda dapat menyesuaikan gaya judul dengan memodifikasi properti seperti font, ukuran, tebal, dan miring menggunakan`TextState` obyek.

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.PDF?  
 Anda dapat memperoleh lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/) untuk menguji Aspose.PDF tanpa batasan.