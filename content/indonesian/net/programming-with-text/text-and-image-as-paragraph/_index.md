---
title: Teks Dan Gambar Sebagai Paragraf Dalam File PDF
linktitle: Teks Dan Gambar Sebagai Paragraf Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menambahkan teks dan gambar sebagai paragraf sebaris dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 530
url: /id/net/programming-with-text/text-and-image-as-paragraph/
---
Tutorial ini menjelaskan cara menambahkan teks dan gambar sebagai paragraf sebaris dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan proses langkah demi langkah.

## Prasyarat

Sebelum melanjutkan tutorial, pastikan Anda memiliki hal berikut:

- Pengetahuan dasar bahasa pemrograman C#.
- Aspose.PDF untuk perpustakaan .NET diinstal. Anda dapat memperolehnya dari situs Aspose atau menggunakan NuGet untuk menginstalnya di proyek Anda.

## Langkah 1: Siapkan proyek

Mulailah dengan membuat proyek C# baru di lingkungan pengembangan terintegrasi (IDE) pilihan Anda dan tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan

Tambahkan arahan penggunaan berikut di awal file C# Anda untuk mengimpor namespace yang diperlukan:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## Langkah 3: Tetapkan jalur ke direktori dokumen

 Tetapkan jalur ke direktori dokumen Anda menggunakan`dataDir` variabel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 4: Buat Dokumen dan Halaman baru

 Buat yang baru`Document` objek dan menambahkan halaman ke koleksi halamannya:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Langkah 5: Buat TextFragment dan tambahkan sebagai paragraf

 Membuat`TextFragment` objek dan menambahkannya ke kumpulan paragraf di halaman:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Langkah 6: Tambahkan gambar sebagai paragraf sebaris

 Buat sebuah`Aspose.Pdf.Image` objek dan atur sebagai paragraf sebaris sehingga muncul tepat setelah paragraf sebelumnya:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Opsional: Atur tinggi gambar
image.FixWidth = 100; // Opsional: Atur lebar gambar
page.Paragraphs.Add(image);
```

 Mengganti`"aspose-logo.jpg"` dengan nama file gambar sebenarnya dan sesuaikan tinggi dan lebar gambar opsional sesuai keinginan.

## Langkah 7: Tambahkan TextFragment lain sebagai paragraf sebaris

 Inisialisasi ulang`TextFragment` objek dengan konten berbeda dan menambahkannya sebagai paragraf sebaris:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Langkah 8: Simpan dokumen PDF

Simpan dokumen PDF yang dimodifikasi:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Pastikan untuk mengganti`"TextAndImageAsParagraph_out.pdf"` dengan nama file keluaran yang diinginkan.

### Contoh kode sumber untuk Teks Dan Gambar Sebagai Paragraf menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat instance Dokumen
Document doc = new Document();
// Tambahkan halaman ke halaman kumpulan contoh Dokumen
Page page = doc.Pages.Add();
// Buat TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Tambahkan fragmen teks ke kumpulan paragraf objek Halaman
page.Paragraphs.Add(text);
// Buat contoh gambar
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Atur gambar sebagai paragraf sebaris sehingga muncul tepat setelahnya
// Objek paragraf sebelumnya (TextFragment)
image.IsInLineParagraph = true;
// Tentukan jalur file gambar
image.File = dataDir + "aspose-logo.jpg";
// Atur Tinggi gambar (opsional)
image.FixHeight = 30;
// Atur Lebar Gambar (opsional)
image.FixWidth = 100;
// Tambahkan gambar ke kumpulan paragraf objek halaman
page.Paragraphs.Add(image);
// Inisialisasi ulang objek TextFragment dengan konten berbeda
text = new TextFragment(" Hello Again..");
// Tetapkan TextFragment sebagai paragraf sebaris
text.IsInLineParagraph = true;
// Tambahkan TextFragment yang baru dibuat ke kumpulan paragraf halaman
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara menambahkan teks dan gambar sebagai paragraf sebaris dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Tutorial ini memberikan panduan langkah demi langkah, mulai dari menyiapkan proyek hingga menyimpan dokumen yang dimodifikasi. Anda sekarang dapat memasukkan kode ini ke dalam proyek C# Anda sendiri untuk menyesuaikan tata letak teks dan gambar dalam file PDF.

### FAQ

#### Q: Apa tujuan dari tutorial "Teks Dan Gambar Sebagai Paragraf Dalam File PDF"?

J: Tutorial "Teks Dan Gambar Sebagai Paragraf Dalam File PDF" bertujuan untuk memandu pengguna tentang cara menambahkan teks dan gambar sebagai paragraf sebaris dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Tutorial ini memberikan petunjuk langkah demi langkah dan contoh kode C# untuk mendemonstrasikan prosesnya.

#### T: Bagaimana tutorial ini membantu menambahkan teks dan gambar sebagai paragraf sebaris?

J: Tutorial ini membantu pengguna memahami cara menggunakan Aspose.PDF untuk .NET untuk menggabungkan teks dan gambar sebagai paragraf sebaris dalam dokumen PDF. Dengan mengikuti langkah-langkah dan contoh kode yang disediakan, pengguna dapat membuat file PDF dengan tata letak khusus yang menggabungkan teks dan gambar.

#### Q: Prasyarat apa saja yang diperlukan untuk mengikuti tutorial ini?

A: Sebelum memulai tutorial, Anda harus memiliki pemahaman dasar tentang bahasa pemrograman C#. Selain itu, Anda perlu menginstal perpustakaan Aspose.PDF untuk .NET. Anda dapat memperolehnya dari situs Aspose atau menginstalnya di proyek Anda menggunakan NuGet.

#### T: Bagaimana cara menyiapkan proyek saya untuk mengikuti tutorial ini?

J: Untuk memulai, buat proyek C# baru di lingkungan pengembangan terintegrasi (IDE) pilihan Anda dan tambahkan referensi ke pustaka Aspose.PDF untuk .NET. Ini memungkinkan Anda memanfaatkan fitur perpustakaan untuk bekerja dengan dokumen PDF, fragmen teks, dan gambar.

#### T: Dapatkah saya menggunakan tutorial ini untuk menambahkan beberapa paragraf teks dan gambar dalam PDF?

J: Ya, Anda dapat menggunakan contoh kode yang disediakan untuk menambahkan beberapa paragraf teks dan gambar dalam dokumen PDF yang sama. Tutorial ini menunjukkan cara membuat paragraf sebaris, sehingga memudahkan untuk memasukkan berbagai kombinasi teks dan gambar.

#### T: Bagaimana cara menentukan konten dan tampilan paragraf teks dan gambar?

 A: Tutorial ini menunjukkan cara membuat`TextFragment`objek untuk mewakili paragraf teks dan`Aspose.Pdf.Image` objek untuk merepresentasikan gambar. Anda dapat menyesuaikan konten, dimensi, dan tampilan teks dan gambar menggunakan contoh kode yang disediakan.

#### T: Dapatkah saya menyesuaikan tata letak paragraf sebaris?

 J: Ya, Anda dapat menyesuaikan tata letak paragraf sebaris dengan mengontrol posisi, dimensi, dan urutannya dalam halaman. Tutorial ini menunjukkan cara mengatur atribut inline, seperti`IsInLineParagraph`, untuk mengontrol tata letak paragraf teks dan gambar.

#### T: Bagaimana cara menyimpan dokumen PDF yang dimodifikasi?

 A: Untuk menyimpan dokumen PDF yang telah dimodifikasi, Anda dapat menggunakan`Save` metode`Document` obyek. Tutorial ini menyediakan contoh kode yang menunjukkan cara menyimpan dokumen PDF yang dihasilkan.