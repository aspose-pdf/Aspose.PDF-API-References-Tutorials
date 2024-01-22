---
title: Putar Teks Menggunakan Fragmen Teks Dan Paragraf
linktitle: Putar Teks Menggunakan Fragmen Teks Dan Paragraf
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara memutar teks menggunakan fragmen teks dan paragraf dalam dokumen PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 400
url: /id/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
Tutorial ini menjelaskan cara menggunakan Aspose.PDF untuk .NET untuk memutar teks menggunakan fragmen teks dan paragraf. Kode sumber C# yang disediakan menunjukkan proses langkah demi langkah.

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
```

## Langkah 3: Buat dokumen PDF

 Inisialisasi`Document` objek untuk membuat dokumen PDF baru:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Pastikan untuk mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 4: Tambahkan halaman

 Dapatkan halaman tertentu dari dokumen menggunakan`Pages.Add()` metode:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Langkah 5: Buat fragmen teks

 Buat banyak`TextFragment` objek, atur teks dan propertinya, dan tentukan sudut rotasi:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

Sesuaikan teks, sudut rotasi, dan properti lainnya sesuai keinginan.

## Langkah 6: Tambahkan fragmen teks ke halaman

 Tambahkan fragmen teks yang dibuat ke halaman dengan menambahkannya ke`Paragraphs` koleksi:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Langkah 7: Simpan dokumen PDF

 Simpan dokumen PDF yang dimodifikasi ke file menggunakan`Save` metode:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Pastikan untuk mengganti`"TextFragmentTests_Rotated3_out.pdf"` dengan nama file keluaran yang diinginkan.

### Contoh kode sumber untuk Memutar Teks Menggunakan Fragmen Teks Dan Paragraf menggunakan Aspose.PDF untuk .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inisialisasi objek dokumen
Document pdfDocument = new Document();
// Dapatkan halaman tertentu
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Buat fragmen teks
TextFragment textFragment1 = new TextFragment("main text");
// Atur properti teks
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Buat fragmen teks
TextFragment textFragment2 = new TextFragment("rotated text");
// Atur properti teks
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Atur rotasi
textFragment2.TextState.Rotation = 315;
// Buat fragmen teks
TextFragment textFragment3 = new TextFragment("rotated text");
// Atur properti teks
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Atur rotasi
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Simpan dokumen
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara memutar teks menggunakan fragmen teks dan paragraf dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Tutorial ini memberikan panduan langkah demi langkah, mulai dari membuat dokumen hingga menyimpan versi modifikasi. Anda sekarang dapat memasukkan kode ini ke dalam proyek C# Anda sendiri untuk memanipulasi rotasi teks dalam file PDF.

### FAQ

#### Q: Apa tujuan dari tutorial "Memutar Teks Menggunakan Fragmen Teks Dan Paragraf"?

J: Tutorial "Putar Teks Menggunakan Fragmen Teks Dan Paragraf" bertujuan untuk memandu Anda melalui proses penggunaan perpustakaan Aspose.PDF untuk .NET untuk memutar teks menggunakan fragmen teks dan paragraf dalam dokumen PDF. Tutorial ini memberikan petunjuk langkah demi langkah dan kode contoh untuk mencapai fungsi ini.

#### Q: Apa perbedaan tutorial ini dengan tutorial rotasi teks sebelumnya?

J: Tutorial ini menggabungkan penggunaan fragmen teks dan paragraf untuk mencapai rotasi teks dalam dokumen PDF. Ini menunjukkan cara memutar fragmen teks satu per satu dan kemudian menambahkannya ke halaman`Paragraphs` koleksi untuk mencapai efek rotasi teks yang lebih komprehensif.

#### T: Apa keuntungan menggunakan fragmen teks dan paragraf untuk rotasi teks?

J: Menggunakan fragmen teks dan paragraf secara bersamaan memungkinkan lebih banyak fleksibilitas dalam rotasi teks. Fragmen teks memungkinkan pengaturan rotasi dan pemformatan individual, sementara paragraf menyediakan struktur untuk mengatur dan memposisikan fragmen teks dalam halaman.

#### T: Dapatkah saya menerapkan sudut rotasi berbeda pada fragmen teks berbeda dalam paragraf yang sama?

 A: Ya, Anda dapat menerapkan sudut rotasi yang berbeda ke sudut yang berbeda`TextFragment` objek dalam paragraf yang sama. Setiap fragmen teks dapat memiliki sudut rotasinya sendiri yang ditentukan menggunakan`TextState.Rotation` Properti.

#### T: Apakah mungkin untuk mencapai efek rotasi teks yang kompleks menggunakan metode ini?

J: Ya, dengan menggabungkan fragmen teks dengan berbagai sudut rotasi dan mengaturnya dalam paragraf, Anda dapat mencapai efek rotasi teks yang kompleks dan disesuaikan, sehingga meningkatkan daya tarik visual dokumen PDF Anda.

#### T: Langkah apa saja yang terlibat dalam memutar teks menggunakan fragmen teks dan paragraf?

J: Langkah-langkahnya antara lain:

1. Menyiapkan proyek dengan membuat proyek C# baru dan menambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.
2. Membuat dokumen PDF dan menambahkan halaman.
3. Membuat fragmen teks, mengatur propertinya, dan menentukan sudut rotasi.
4.  Menambahkan fragmen teks ke halaman menggunakan`Paragraphs` koleksi.
5. Menyimpan dokumen PDF yang dimodifikasi.

#### T: Dapatkah saya menerapkan rotasi ke seluruh paragraf?

 J: Ya, Anda dapat menerapkan rotasi ke seluruh paragraf dengan mengatur`TextState.Rotation` milik paragraf itu sendiri. Ini akan memutar semua fragmen teks dalam paragraf itu.