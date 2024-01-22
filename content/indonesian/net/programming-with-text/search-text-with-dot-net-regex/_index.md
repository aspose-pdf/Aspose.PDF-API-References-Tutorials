---
title: Cari Teks Dengan Dot Net Regex
linktitle: Cari Teks Dengan Dot Net Regex
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mencari teks menggunakan ekspresi reguler .NET dalam dokumen PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 480
url: /id/net/programming-with-text/search-text-with-dot-net-regex/
---
Tutorial ini menjelaskan cara menggunakan Aspose.PDF untuk .NET untuk mencari teks menggunakan ekspresi reguler .NET dalam dokumen PDF. Kode sumber C# yang disediakan menunjukkan proses langkah demi langkah.

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

## Langkah 3: Tetapkan jalur ke direktori dokumen

 Tetapkan jalur ke direktori dokumen Anda menggunakan`dataDir` variabel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 4: Buat objek .NET Regex

 Membuat`.NET Regex` objek untuk menentukan pola pencarian:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Mengganti`@"[\S]+"` dengan pola ekspresi reguler yang Anda inginkan.

## Langkah 5: Muat dokumen PDF

 Muat dokumen PDF menggunakan`Document` kelas:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Mengganti`"SearchTextRegex.pdf"` dengan nama sebenarnya file PDF Anda.

## Langkah 6: Dapatkan halaman tertentu

Dapatkan halaman dokumen yang diinginkan:

```csharp
Page page = document.Pages[1];
```

 Mengganti`1` dengan nomor halaman yang diinginkan (indeks berbasis 1).

## Langkah 7: Buat TextFragmentAbsorber

 Membuat`TextFragmentAbsorber` objek untuk menemukan semua contoh ekspresi reguler masukan:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Langkah 8: Terima penyerap untuk halaman tersebut

Terima penyerap untuk halaman:

```csharp
page.Accept(textFragmentAbsorber);
```

## Langkah 9: Ambil fragmen teks yang diekstraksi

Dapatkan fragmen teks yang diekstraksi menggunakan`TextFragments` properti dari`TextFragmentAbsorber` obyek:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Langkah 10: Ulangi fragmen teks

Ulangi fragmen teks yang diambil dan lakukan tindakan yang diinginkan:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Ubah kode dalam loop untuk melakukan tindakan lebih lanjut pada setiap fragmen teks jika diperlukan.

### Contoh kode sumber untuk Teks Pencarian Dengan Dot Net Regex menggunakan Aspose.PDF untuk .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat objek Regex untuk menemukan semua kata
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Buka dokumen
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Dapatkan halaman tertentu
Page page = document.Pages[1];
// Buat objek TextAbsorber untuk menemukan semua instance regex input
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Terima penyerap untuk halaman tersebut
page.Accept(textFragmentAbsorber);
// Dapatkan fragmen teks yang diekstraksi
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Ulangi fragmennya
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara mencari teks menggunakan ekspresi reguler .NET dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Tutorial ini memberikan panduan langkah demi langkah, mulai dari menyiapkan proyek hingga mengakses fragmen teks yang diekstraksi. Anda sekarang dapat memasukkan kode ini ke dalam proyek C# Anda sendiri untuk melakukan pencarian teks lanjutan dalam file PDF.

### FAQ

#### Q: Apa tujuan dari tutorial "Mencari Teks Dengan Dot Net Regex"?

J: Tutorial "Mencari Teks Dengan Dot Net Regex" bertujuan untuk memandu pengguna dalam menggunakan pustaka Aspose.PDF untuk .NET guna mencari teks dalam dokumen PDF menggunakan ekspresi reguler .NET. Tutorial ini memberikan petunjuk langkah demi langkah dan contoh kode C# untuk mendemonstrasikan prosesnya.

#### T: Bagaimana tutorial ini membantu dalam mencari teks menggunakan ekspresi reguler .NET dalam PDF?

J: Tutorial ini membantu pengguna memahami cara memanfaatkan kemampuan Aspose.PDF untuk .NET untuk mencari teks menggunakan ekspresi reguler .NET dalam dokumen PDF. Dengan mengikuti langkah-langkah dan contoh kode yang disediakan, pengguna dapat secara efektif mencari pola teks yang cocok dengan ekspresi reguler yang mereka tentukan.

#### Q: Prasyarat apa saja yang diperlukan untuk mengikuti tutorial ini?

A: Sebelum memulai tutorial, Anda harus memiliki pemahaman dasar tentang bahasa pemrograman C#. Selain itu, Anda perlu menginstal perpustakaan Aspose.PDF untuk .NET. Anda dapat memperolehnya dari situs Aspose atau menginstalnya di proyek Anda menggunakan NuGet.

#### T: Bagaimana cara menyiapkan proyek saya untuk mengikuti tutorial ini?

J: Untuk memulai, buat proyek C# baru di lingkungan pengembangan terintegrasi (IDE) pilihan Anda dan tambahkan referensi ke pustaka Aspose.PDF untuk .NET. Ini akan memungkinkan Anda memanfaatkan fitur perpustakaan untuk mencari dan bekerja dengan dokumen PDF.

#### T: Dapatkah saya menggunakan tutorial ini untuk mencari jenis teks tertentu menggunakan ekspresi reguler .NET?

 J: Ya, tutorial ini memberikan instruksi tentang cara mencari teks menggunakan ekspresi reguler .NET dalam dokumen PDF. Anda dapat menyesuaikannya`.NET Regex` objek untuk menentukan pola pencarian spesifik yang ingin Anda gunakan.

#### T: Bagaimana cara menentukan pola ekspresi reguler .NET yang akan dicari dalam tutorial ini?

 A: Untuk menentukan pola ekspresi reguler .NET yang ingin Anda cari, buat a`.NET Regex` objek dan atur polanya menggunakan sintaks ekspresi reguler yang sesuai. Ganti defaultnya`@"[\S]+"` dalam kode tutorial dengan ekspresi reguler yang Anda inginkan.

#### T: Bagaimana cara mengambil properti dari fragmen teks yang diekstraksi?

 A: Setelah menerima`TextFragmentAbsorber` untuk halaman PDF tertentu, Anda dapat mengambil fragmen teks yang diekstraksi menggunakan`TextFragments` properti dari objek penyerap. Ini memberikan akses ke kumpulan fragmen teks yang cocok dengan ekspresi reguler .NET yang ditentukan.

#### T: Dapatkah saya menyesuaikan kode untuk melakukan tindakan tambahan pada setiap fragmen teks yang diekstraksi?

J: Tentu saja. Kode contoh tutorial menyertakan loop untuk mengulangi fragmen teks yang diambil. Anda dapat menyesuaikan kode dalam loop ini untuk melakukan tindakan tambahan pada setiap fragmen teks yang diekstraksi berdasarkan kebutuhan proyek Anda.

#### T: Bagaimana cara menyimpan dokumen PDF yang dimodifikasi setelah mengekstraksi fragmen teks?

J: Tutorial ini terutama berfokus pada pencarian teks menggunakan ekspresi reguler .NET dan mengambil fragmen teks. Jika Anda berniat melakukan modifikasi pada PDF, Anda dapat merujuk ke dokumentasi Aspose.PDF lainnya untuk mempelajari cara memanipulasi dan menyimpan dokumen berdasarkan kebutuhan spesifik Anda.