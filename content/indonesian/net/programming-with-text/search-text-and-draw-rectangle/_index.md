---
title: Cari Teks Dan Gambar Persegi Panjang
linktitle: Cari Teks Dan Gambar Persegi Panjang
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mencari teks dalam PDF, menggambar persegi panjang di sekitar teks yang ditemukan, dan menyimpan dokumen yang dimodifikasi menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 460
url: /id/net/programming-with-text/search-text-and-draw-rectangle/
---
Tutorial ini menjelaskan cara menggunakan Aspose.PDF untuk .NET untuk mencari teks tertentu dalam dokumen PDF, menggambar persegi panjang di sekitar teks yang ditemukan, dan menyimpan dokumen yang dimodifikasi. Kode sumber C# yang disediakan menunjukkan proses langkah demi langkah.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Langkah 3: Tetapkan jalur ke direktori dokumen

 Tetapkan jalur ke direktori dokumen Anda menggunakan`dataDir` variabel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 4: Muat dokumen PDF

 Muat dokumen PDF menggunakan`Document` kelas:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Mengganti`"SearchAndGetTextFromAll.pdf"` dengan nama sebenarnya file PDF Anda.

## Langkah 5: Buat TextFragmentAbsorber

 Membuat`TextFragmentAbsorber` objek untuk menemukan semua contoh frasa pencarian masukan:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Mengganti`@"[\S]+"` dengan pola ekspresi reguler yang Anda inginkan.

## Langkah 6: Aktifkan pencarian ekspresi reguler

 Aktifkan pencarian ekspresi reguler dengan mengatur`TextSearchOptions` properti penyerap:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Langkah 7: Cari di semua halaman

Terima penyerap untuk semua halaman dokumen:

```csharp
document.Pages.Accept(textAbsorber);
```

## Langkah 8: Gambarlah persegi panjang di sekitar teks yang ditemukan

 Membuat`PdfContentEditor` objek dan ulangi fragmen teks yang diambil, gambar persegi panjang di sekitar setiap segmen teks:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Langkah 9: Simpan dokumen yang dimodifikasi

Simpan dokumen yang diubah:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Pastikan untuk mengganti`"SearchTextAndDrawRectangle_out.pdf"` dengan nama file keluaran yang diinginkan.

### Contoh kode sumber untuk Pencarian Teks Dan Gambar Persegi Panjang menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Buat objek TextAbsorber untuk menemukan semua frasa yang cocok dengan ekspresi reguler
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara mencari teks tertentu dalam dokumen PDF, menggambar persegi panjang di sekitar teks yang ditemukan, dan menyimpan dokumen yang dimodifikasi menggunakan Aspose.PDF untuk .NET. Tutorial ini memberikan panduan langkah demi langkah, mulai dari menyiapkan proyek hingga melakukan tindakan yang diperlukan. Anda sekarang dapat memasukkan kode ini ke dalam proyek C# Anda sendiri untuk memanipulasi teks dan menggambar persegi panjang dalam file PDF.

### FAQ

#### Q: Apa tujuan dari tutorial "Mencari Teks Dan Menggambar Persegi Panjang"?

J: Tutorial "Telusuri Teks Dan Menggambar Persegi Panjang" bertujuan untuk memandu pengguna melalui proses penggunaan perpustakaan Aspose.PDF untuk .NET untuk mencari teks tertentu dalam dokumen PDF, menggambar persegi panjang di sekitar segmen teks yang ditemukan, dan menyimpan yang dimodifikasi dokumen. Tutorial ini memberikan instruksi rinci dan contoh kode C# untuk mengilustrasikan setiap langkah proses.

#### T: Bagaimana tutorial ini membantu menggambar persegi panjang di sekitar teks tertentu dalam dokumen PDF?

J: Tutorial ini memberikan panduan komprehensif tentang cara menemukan dan menggambar persegi panjang di sekitar segmen teks tertentu dalam dokumen PDF. Ini menunjukkan proses menyiapkan proyek, memuat dokumen PDF, mengaktifkan pencarian ekspresi reguler, menggambar persegi panjang di sekitar segmen teks yang ditemukan, dan menyimpan PDF yang dimodifikasi.

#### Q: Prasyarat apa saja yang diperlukan untuk mengikuti tutorial ini?

A: Sebelum memulai tutorial, Anda harus memiliki pemahaman dasar tentang bahasa pemrograman C#. Selain itu, Anda perlu menginstal perpustakaan Aspose.PDF untuk .NET. Anda dapat memperolehnya dari situs Aspose atau menginstalnya di proyek Anda menggunakan NuGet.

#### T: Bagaimana cara menyiapkan proyek saya untuk mengikuti tutorial ini?

J: Mulailah dengan membuat proyek C# baru di lingkungan pengembangan terintegrasi (IDE) pilihan Anda. Kemudian, tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET ke proyek Anda. Ini akan memungkinkan Anda menggunakan fungsionalitas perpustakaan untuk memanipulasi dokumen PDF.

#### T: Bisakah saya menggambar persegi panjang di sekitar teks tertentu menggunakan tutorial ini?

A: Ya, tutorial ini berfokus pada menggambar persegi panjang di sekitar segmen teks tertentu dalam dokumen PDF. Ini menunjukkan cara menemukan teks yang diinginkan menggunakan ekspresi reguler, membuat persegi panjang di sekitar segmen teks yang diidentifikasi, dan menyimpan PDF yang dimodifikasi.

#### T: Bagaimana cara menentukan teks yang ingin saya cari dan menggambar persegi panjang?

 A: Untuk menentukan teks yang ingin Anda cari dan gambar persegi panjang di sekelilingnya, buat a`TextFragmentAbsorber` objek dan atur polanya menggunakan`Text` parameter. Ganti pola default`@"[\S]+"` dalam kode tutorial dengan pola ekspresi reguler yang Anda inginkan.

#### T: Bagaimana cara mengaktifkan pencarian ekspresi reguler untuk teks?

 A: Pencarian ekspresi reguler diaktifkan dengan membuat a`TextSearchOptions` objek dan menetapkan nilainya menjadi`true` . Tetapkan objek ini ke`TextSearchOptions` properti dari`TextFragmentAbsorber` contoh. Hal ini memastikan bahwa pola ekspresi reguler digunakan selama pencarian teks.

#### T: Bagaimana cara menggambar persegi panjang di sekitar teks yang ditemukan?

 A: Setelah mengidentifikasi segmen teks menggunakan`TextFragmentAbsorber` , tutorial menyediakan perulangan untuk mengulangi segmen ini. Untuk setiap segmen teks, tutorial menunjukkan cara membuat persegi panjang di sekelilingnya menggunakan`DrawBox` metode dan tentukan tampilan persegi panjang.

#### Q: Bagaimana langkah-langkah untuk menyimpan PDF yang dimodifikasi dengan gambar persegi panjang?

A: Setelah menggambar persegi panjang di sekitar segmen teks yang diinginkan, gunakan`Document` kelas`Save` metode untuk menyimpan dokumen yang dimodifikasi. Kode contoh tutorial menunjukkan cara menyimpan PDF yang telah diedit dan menampilkan pesan sukses.

#### T: Dapatkah saya menyesuaikan tampilan persegi panjang yang digambar?

 A: Ya, Anda dapat menyesuaikan tampilan persegi panjang yang digambar. Dalam kode contoh tutorial,`DrawBox` metode yang digunakan untuk membuat persegi panjang. Anda dapat memodifikasi properti seperti warna, gaya, dan ketebalan untuk menyesuaikan tampilan persegi panjang yang digambar.