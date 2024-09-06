---
title: Penyelarasan Teks Untuk Konten Kotak Mengambang Dalam File PDF
linktitle: Penyelarasan Teks Untuk Konten Kotak Mengambang Dalam File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menyelaraskan teks dalam kotak mengambang di berkas PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 520
url: /id/net/programming-with-text/text-alignment-for-floating-box-contents/
---
Tutorial ini menjelaskan cara menyelaraskan teks dalam kotak mengambang di berkas PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan proses tersebut langkah demi langkah.

## Prasyarat

Sebelum melanjutkan tutorial, pastikan Anda memiliki hal berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET telah terinstal. Anda dapat memperolehnya dari situs web Aspose atau menggunakan NuGet untuk menginstalnya di proyek Anda.

## Langkah 1: Siapkan proyek

Mulailah dengan membuat proyek C# baru di lingkungan pengembangan terintegrasi (IDE) pilihan Anda dan tambahkan referensi ke pustaka Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan

Tambahkan perintah berikut di awal file C# Anda untuk mengimpor namespace yang diperlukan:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Langkah 3: Tetapkan jalur ke direktori dokumen

 Atur jalur ke direktori dokumen Anda menggunakan`dataDir` variabel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 4: Buat Dokumen Baru

 Buat yang baru`Document` obyek:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## Langkah 5: Buat Kotak Mengambang dengan Fragmen Teks

 Buat beberapa`FloatingBox` Objek dengan perataan vertikal dan perataan horizontal yang berbeda:

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);

Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);

Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

 Ubah teks dan gaya`TextFragment` objek sesuai keinginan.

## Langkah 6: Simpan dokumen PDF

Simpan dokumen PDF yang dimodifikasi:

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 Pastikan untuk mengganti`"FloatingBox_alignment_review_out.pdf"` dengan nama file keluaran yang diinginkan.

### Contoh kode sumber untuk Penyelarasan Teks untuk Konten Kotak Mengambang menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara menyelaraskan teks dalam kotak mengambang dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Tutorial ini menyediakan panduan langkah demi langkah, mulai dari menyiapkan proyek hingga menyimpan dokumen yang dimodifikasi. Anda sekarang dapat memasukkan kode ini ke dalam proyek C# Anda sendiri untuk menyesuaikan penyelarasan teks dalam kotak mengambang dalam file PDF.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan dari tutorial "Penyelarasan Teks untuk Isi Kotak Mengambang dalam Berkas PDF"?

J: Tutorial "Penyelarasan Teks untuk Konten Kotak Mengambang dalam Berkas PDF" bertujuan untuk memandu pengguna tentang cara menyelaraskan teks dalam kotak mengambang dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Tutorial ini menyediakan petunjuk langkah demi langkah dan contoh kode C# untuk menunjukkan prosesnya.

#### T: Bagaimana tutorial ini membantu dalam menyelaraskan teks dalam kotak mengambang?

J: Tutorial ini membantu pengguna memahami cara menggunakan Aspose.PDF for .NET untuk menyelaraskan teks dalam kotak mengambang dalam dokumen PDF. Dengan mengikuti langkah-langkah dan contoh kode yang diberikan, pengguna dapat menyesuaikan penyelarasan vertikal dan horizontal teks dalam kotak mengambang.

#### T: Prasyarat apa yang diperlukan untuk mengikuti tutorial ini?

J: Sebelum memulai tutorial ini, Anda harus memiliki pemahaman dasar tentang bahasa pemrograman C#. Selain itu, Anda perlu menginstal pustaka Aspose.PDF for .NET. Anda dapat memperolehnya dari situs web Aspose atau menginstalnya di proyek Anda menggunakan NuGet.

#### T: Bagaimana cara menyiapkan proyek saya untuk mengikuti tutorial ini?

J: Untuk memulai, buat proyek C# baru di lingkungan pengembangan terpadu (IDE) pilihan Anda dan tambahkan referensi ke pustaka Aspose.PDF untuk .NET. Ini memungkinkan Anda memanfaatkan fitur pustaka untuk bekerja dengan dokumen PDF dan menyelaraskan teks dalam kotak mengambang.

#### T: Dapatkah saya menggunakan tutorial ini untuk menyelaraskan teks dalam semua jenis kotak mengambang?

A: Ya, tutorial ini menyediakan petunjuk tentang cara menyelaraskan teks dalam kotak mengambang dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan contoh kode yang disediakan untuk menyesuaikan penyelarasan vertikal dan horizontal teks dalam kotak mengambang.

#### T: Bagaimana cara menentukan perataan teks dalam kotak mengambang?

 A: Tutorial ini menunjukkan cara membuat`FloatingBox`objek dan mengaturnya`VerticalAlignment` Dan`HorizontalAlignment` properti untuk mengontrol perataan teks yang ada. Anda dapat menyesuaikan properti ini sesuai dengan kebutuhan Anda.

#### T: Bagaimana saya dapat menyesuaikan tampilan kotak mengambang?

 A: Anda dapat menyesuaikan tampilan kotak mengambang dengan memodifikasi properti seperti batas, ukuran, dan konten teks. Tutorial ini menyediakan contoh kode yang menunjukkan cara membuat dan memberi gaya pada kotak mengambang.`FloatingBox` objek.

#### T: Dapatkah saya menambahkan beberapa kotak mengambang dengan perataan berbeda dalam dokumen PDF yang sama?

 A: Ya, tutorial ini mengilustrasikan cara membuat beberapa`FloatingBox` objek dengan perataan vertikal dan horizontal yang berbeda dan menambahkannya ke dokumen PDF yang sama. Ini memungkinkan Anda melihat efek dari berbagai perataan dalam dokumen yang sama.

#### T: Bagaimana cara menyimpan dokumen PDF yang dimodifikasi?

 A: Untuk menyimpan dokumen PDF yang dimodifikasi, Anda dapat menggunakan`Save` metode dari`Document` objek. Tutorial ini menyediakan contoh kode yang menunjukkan cara menyimpan dokumen PDF yang dihasilkan.