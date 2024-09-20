---
title: Cari Teks Dan Gambar Persegi Panjang
linktitle: Cari Teks Dan Gambar Persegi Panjang
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mencari teks dalam PDF dan menyorotnya dengan persegi panjang menggunakan Aspose.PDF untuk .NET! Tutorial langkah demi langkah yang mudah untuk meningkatkan keterampilan manipulasi PDF.
type: docs
weight: 460
url: /id/net/programming-with-text/search-text-and-draw-rectangle/
---
## Perkenalan

Apakah Anda ingin meningkatkan keterampilan manipulasi PDF Anda? Apakah Anda ingin mempelajari cara mencari teks tertentu dalam file PDF dan menyorotnya dengan persegi panjang? Anda telah menemukan panduan yang tepat! Hari ini, saya akan memandu Anda tentang cara menggunakan Aspose.PDF untuk .NET guna mencari teks dalam dokumen PDF dan menggambar persegi panjang di sekitarnya. Artikel ini akan memberikan tutorial langkah demi langkah yang dirancang dengan mempertimbangkan kejelasan dan kegunaan, memastikan Anda dapat mengikuti dan menerapkan teknik ini pada proyek Anda. 

## Prasyarat

Sebelum menyelami tutorial, mari persiapkan apa yang Anda butuhkan untuk memastikan alur kerja lancar:

1. Pemahaman Dasar tentang .NET: Anda harus terbiasa dengan pemrograman C# dan kerangka kerja .NET untuk mengikuti tutorial ini secara efektif.
   
2. Visual Studio Terpasang: Anda akan memerlukan lingkungan pengembangan terpadu (IDE) untuk menulis dan menguji kode Anda. Visual Studio Community adalah pilihan yang bagus, dan gratis.
   
3. Aspose.PDF untuk .NET: Anda perlu menginstal pustaka Aspose.PDF di proyek Anda. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/pdf/net/) atau pertimbangkan[lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk fitur yang diperluas.
   
4.  Contoh Dokumen PDF: Untuk tutorial ini, Anda memerlukan file PDF contoh bernama`SearchAndGetTextFromAll.pdf` disimpan di direktori proyek Anda. 

## Paket Impor

Untuk memulai, pertama-tama Anda perlu mengimpor paket yang diperlukan ke dalam proyek .NET Anda. Ikuti langkah-langkah berikut:

### Buka Visual Studio

Luncurkan Visual Studio dan buat Aplikasi Konsol baru atau gunakan yang sudah ada di mana Anda ingin mengimplementasikan fungsionalitas PDF.

### Tambahkan Aspose.PDF ke Proyek Anda

1. Klik kanan pada proyek Anda di Solution Explorer.
2. Pilih "Kelola Paket NuGet."
3.  Pencarian untuk`Aspose.PDF` dan instal versi terbaru.

Dengan melakukan ini, Anda menyiapkan dasar untuk semua manipulasi PDF menakjubkan yang akan Anda lakukan.

## Mengimpor Ruang Nama

Di bagian atas file program Anda, Anda ingin mengimpor namespace yang relevan dari pustaka Aspose:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

Hal ini memudahkan untuk mengakses kelas dan metode dalam pustaka Aspose.PDF untuk tugas Anda.


Sekarang setelah Anda menyiapkan semuanya, mari kita uraikan proses pencarian teks dalam PDF dan menggambar persegi panjang di sekitarnya menjadi beberapa langkah yang lebih mudah dikelola.

## Langkah 1: Tetapkan Jalur untuk Dokumen Anda

 Pertama, atur jalur ke file PDF Anda. Pastikan untuk mengganti`YOUR DOCUMENT DIRECTORY` dengan jalur sebenarnya tempat Anda`SearchAndGetTextFromAll.pdf` disimpan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buka Dokumen PDF

 Selanjutnya, buatlah sebuah instance dari`Document` kelas untuk memuat PDF Anda:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

Baris kode ini membuka berkas PDF yang Anda tentukan, sehingga memungkinkan Anda memanipulasinya lebih lanjut.

## Langkah 3: Buat Penyerap Teks

 Sekarang, Anda memerlukan cara untuk mencari teks dalam dokumen tersebut. Untuk ini, kami menggunakan`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Ekspresi reguler`@"[\S]+"` dirancang untuk mencocokkan string apa pun yang bukan spasi dalam PDF. 

## Langkah 4: Konfigurasikan Opsi Pencarian Teks

Berikutnya, Anda harus mengatur opsi pencarian teks:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

 Di sini,`true` parameter berarti pencarian akan peka huruf besar/kecil. Anda dapat mengaturnya ke`false` jika Anda menginginkan pencarian tanpa memperhatikan huruf besar/kecil.

## Langkah 5: Terima Text Absorber di Dokumen

 Dengan kamu`TextFragmentAbsorber` dan opsi pencarian sudah siap, saatnya menyerap teks dari dokumen:

```csharp
document.Pages.Accept(textAbsorber);
```

Metode ini memeriksa setiap halaman dalam PDF Anda untuk menemukan fragmen teks yang cocok dengan pola yang ditentukan.

## Langkah 6: Buat PdfContentEditor

 Untuk menggambar bentuk pada dokumen, Anda memerlukan`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

Editor ini memungkinkan Anda untuk memanipulasi dan mengedit konten PDF dengan mudah.

## Langkah 7: Ulangi Fragmen Teks yang Ditemukan

Sekarang, Anda ingin mengulang fragmen teks yang ditemukan untuk menggambar persegi panjang di sekelilingnya:

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

 Loop ini mengulangi setiap fragmen teks dan segmennya, memanggil`DrawBox` metode untuk menggambar persegi panjang.

## Langkah 8: Tentukan Metode DrawBox

 Anda perlu mendefinisikan`DrawBox` metode, yang akan menangani logika menggambar persegi panjang. Berikut implementasi sederhananya:

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    // Hitung dimensi persegi panjang berdasarkan segmen teks
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    // Gambarlah persegi panjang menggunakan nilai yang dihitung
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

Metode ini menentukan posisi dan ukuran persegi panjang berdasarkan persegi panjang pembatas segmen dan menggunakan editor untuk menggambarnya.

## Langkah 9: Simpan Dokumen yang Dimodifikasi

Setelah menggambar persegi panjang di sekitar teks yang ditemukan, Anda dapat menyimpan dokumen yang dimodifikasi:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

Pastikan file baru Anda disimpan dengan nama yang berbeda untuk menghindari penimpaan dokumen asli Anda.

## Langkah 10: Pesan Konfirmasi

Terakhir, cetak pesan konfirmasi ke konsol untuk memberi tahu Anda bahwa operasi berhasil:

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

Nah, itu dia! Anda telah berhasil membuat skrip untuk mencari teks dalam PDF dan menyorotnya dengan persegi panjang.

## Kesimpulan

Selamat! Anda baru saja membuka keterampilan hebat yang dapat meningkatkan kemampuan manipulasi PDF Anda menggunakan Aspose.PDF untuk .NET. Hanya dengan beberapa langkah sederhana, Anda dapat mencari teks apa pun dalam dokumen Anda dan menyorotnya secara visual, membuat dokumen PDF Anda lebih interaktif dan mudah dikelola. Jangan ragu untuk bereksperimen dengan pola regex dan opsi warna yang berbeda untuk benar-benar menjadikan alat ini milik Anda!

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka yang menyediakan cara komprehensif untuk membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram.

### Dapatkah saya menggunakan Aspose.PDF secara gratis?
Ya, Aspose menawarkan uji coba gratis yang dapat Anda gunakan untuk menguji fungsionalitas pustaka. Lihatlah[Di Sini](https://releases.aspose.com/).

### Bahasa pemrograman apa yang perlu saya gunakan dengan Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET dirancang untuk digunakan dengan C# dan bahasa .NET lainnya.

### Bagaimana cara mendapatkan bantuan dengan Aspose.PDF?
 Anda dapat mengunjungi forum dukungan Aspose untuk mendapatkan bantuan terkait masalah atau pertanyaan apa pun yang mungkin Anda miliki. Temukan dukungan[Di Sini](https://forum.aspose.com/c/pdf/10).

### Di mana saya mengunduh Aspose.PDF untuk .NET?
 Anda dapat mengunduh pustaka dari situs web Aspose,[Di Sini](https://releases.aspose.com/pdf/net/).