---
title: Ekstrak Teks Menggunakan Perangkat Teks
linktitle: Ekstrak Teks Menggunakan Perangkat Teks
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengekstrak teks dari dokumen PDF menggunakan Perangkat Teks di Aspose.PDF untuk .NET.
type: docs
weight: 210
url: /id/net/programming-with-text/extract-text-using-text-device/
---
## Perkenalan

Mengekstrak teks dari PDF bisa jadi sulit, terutama saat menangani dokumen yang memiliki berbagai format, font tertanam, atau tata letak yang rumit. Namun dengan Aspose.PDF untuk .NET, proses ini menjadi mudah! Baik Anda ingin mengonversi halaman PDF menjadi teks biasa untuk analisis lebih lanjut atau sekadar perlu mengekstrak bagian tertentu, Aspose.PDF siap membantu Anda. Dalam tutorial ini, kami akan menguraikan langkah demi langkah cara mengekstrak teks dari PDF menggunakan kelas TextDevice di Aspose.PDF. Kami juga akan memberikan penjelasan yang jelas, sehingga Anda dapat menerapkan metode yang sama ke proyek Anda sendiri dengan mudah.

## Prasyarat

Sebelum kita mulai membuat kode, pastikan Anda telah menyiapkan semua yang diperlukan untuk mengikuti langkah-langkah ini. Berikut ini yang Anda perlukan:

1.  Aspose.PDF untuk .NET: Unduh versi terbaru dari[Halaman unduhan Aspose.PDF untuk .NET](https://releases.aspose.com/pdf/net/).
2. Lingkungan Pengembangan: Visual Studio atau lingkungan pengembangan C# lainnya.
3. .NET Framework: Pastikan proyek Anda menargetkan .NET Framework 4.x atau yang lebih tinggi.
4. Input File PDF: File PDF yang akan Anda gunakan untuk mengekstrak teks. Tempatkan ini di direktori di komputer Anda (kami akan menyebutnya sebagai`YOUR DOCUMENT DIRECTORY`).

## Paket Impor

Di bagian atas kode Anda, Anda perlu mengimpor namespace yang diperlukan untuk bekerja dengan Aspose.PDF:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Devices;
using System;
using System.Text;
```

## Langkah 1: Muat Dokumen PDF Anda

 Sebelum mengekstrak teks, kita perlu memuat dokumen PDF ke dalam memori. Pada langkah ini, Anda akan membuka PDF Anda menggunakan Aspose.PDF.`Document` kelas. Ini akan memungkinkan Anda mengakses semua halaman dan konten dalam berkas tersebut.

```csharp
// Tentukan jalur ke dokumen PDF Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Muat dokumen PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Di sini, kami menggunakan`Document pdfDocument = new Document(dataDir + "input.pdf");` untuk memuat PDF.`dataDir` variabel menyimpan jalur direktori berkas PDF Anda. Ini akan memberi kita akses ke seluruh dokumen, yang memungkinkan kita untuk mengulang halaman dan mengekstrak konten.

## Langkah 2: Siapkan Pembuat String untuk Penyimpanan Teks

 Sekarang dokumen sudah dimuat, kita perlu cara untuk menyimpan teks yang diekstrak. Untuk ini, kita akan menggunakan`StringBuilder` yang memungkinkan penggabungan string secara efisien.

```csharp
// StringBuilder untuk menampung teks yang diekstraksi
StringBuilder builder = new StringBuilder();
```

 Kami menginisialisasikan`StringBuilder`contoh, yang akan mengumpulkan teks yang diekstrak dari setiap halaman. Ini adalah cara yang lebih efisien untuk menangani string besar dibandingkan dengan penggabungan string biasa dalam satu loop.

## Langkah 3: Ulangi Melalui Halaman PDF

 Selanjutnya, kami mengulang setiap halaman dokumen PDF untuk mengekstrak teks. Kami akan memproses setiap halaman secara individual menggunakan`TextDevice` kelas, yang bertanggung jawab untuk mengubah konten PDF ke format teks.

```csharp
// Ulangi semua halaman dalam PDF
foreach (Page pdfPage in pdfDocument.Pages)
{
    // Memproses setiap halaman untuk ekstraksi teks
}
```

Loop ini melewati setiap halaman PDF (`pdfDocument.Pages` ). Untuk setiap halaman, kami akan mengekstrak teks dan menambahkannya ke`StringBuilder`.

## Langkah 4: Ekstrak Teks dari Setiap Halaman

 Sekarang, kita akan mengatur proses ekstraksi teks untuk setiap halaman. Di sini, kita akan membuat`TextDevice` objek dan menggunakannya untuk memproses halaman PDF.`TextDevice` mengekstrak teks mentah atau yang diformat berdasarkan opsi ekstraksi yang kami tetapkan.

```csharp
using (MemoryStream textStream = new MemoryStream())
{
    // Buat perangkat teks untuk ekstraksi teks
    TextDevice textDevice = new TextDevice();
    
    // Atur opsi ekstraksi teks ke mode 'Murni'
    TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
    textDevice.ExtractionOptions = textExtOptions;

    //Ekstrak teks dari halaman saat ini dan simpan ke aliran memori
    textDevice.Process(pdfPage, textStream);

    // Ubah aliran memori menjadi teks
    string extractedText = Encoding.Unicode.GetString(textStream.ToArray());

    // Tambahkan teks yang diekstrak ke StringBuilder
    builder.Append(extractedText);
}
```

- `TextDevice textDevice = new TextDevice();` : : Itu`TextDevice` kelas digunakan untuk mengekstrak teks dari PDF.
- `TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);` : Opsi ini mengekstrak teks mentah tanpa mempertahankan format apa pun seperti font atau posisi. Anda juga dapat menggunakan`TextFormattingMode.Raw` jika Anda memerlukan kontrol lebih lanjut atas pemformatan.
- `textDevice.Process(pdfPage, textStream);` : Ini memproses setiap halaman PDF dan menyimpan teks yang diekstraksi dalam`MemoryStream`.
-  Terakhir, kita mengkonversi teks dari`MemoryStream` ke string dan menambahkannya ke`StringBuilder`.

## Langkah 5: Simpan Teks yang Diekstrak ke File

 Setelah memproses semua halaman, teks disimpan di`StringBuilder`Langkah terakhir adalah menyimpan teks yang diekstrak ini ke dalam sebuah berkas.

```csharp
// Tentukan jalur keluaran untuk file teks
dataDir = dataDir + "input_Text_Extracted_out.txt";

// Simpan teks yang diekstrak ke dalam file
File.WriteAllText(dataDir, builder.ToString());

Console.WriteLine("\nText extracted successfully from PDF document.\nFile saved at " + dataDir);
```

- `File.WriteAllText(dataDir, builder.ToString());` : Ini menulis seluruh konten`StringBuilder` ke dalam berkas teks.
- Jalur untuk file keluaran diatur dengan menambahkan nama file (`"input_Text_Extracted_out.txt"` ) ke`dataDir` jalur.

## Kesimpulan

Mengekstrak teks dari PDF menggunakan Aspose.PDF untuk .NET merupakan proses yang sederhana dan efisien. Dengan mengikuti langkah-langkah yang diuraikan dalam panduan ini, Anda dapat dengan mudah membuka dokumen PDF, menelusuri halaman, dan mengekstrak teks ke dalam berkas teks. Hal ini sangat berguna untuk memproses data PDF dalam jumlah besar, melakukan analisis teks, atau mengonversi dokumen untuk manipulasi lebih lanjut.

Dengan Aspose.PDF, Anda tidak terbatas pada ekstraksi teks—Anda dapat menangani anotasi, memanipulasi gambar, atau bahkan mengonversi PDF ke format lain seperti HTML atau Word. Fleksibilitas dan kekuatan pustaka ini menjadikannya alat yang sangat berharga untuk manajemen PDF dalam aplikasi .NET.

## Pertanyaan yang Sering Diajukan

### Bisakah Aspose.PDF mengekstrak teks dari PDF berbasis gambar?
Tidak, Aspose.PDF dirancang untuk mengekstrak teks dari PDF berbasis konten. Untuk PDF berbasis gambar, diperlukan teknologi OCR.

### Apakah Aspose.PDF mempertahankan format saat mengekstrak teks?
Secara default, teks diekstraksi tanpa pemformatan, tetapi Anda dapat menyesuaikan opsi ekstraksi jika Anda ingin mempertahankan beberapa pemformatan.

### Bisakah saya mengekstrak teks dari rentang halaman tertentu?
Ya, Anda dapat mengubah kode agar mengulang rentang halaman tertentu, bukan semua halaman.

### Apa saja mode ekstraksi teks di Aspose.PDF?
Aspose.PDF menyediakan dua mode: Raw dan Pure. Mode Raw mencoba mempertahankan tata letak asli, sedangkan mode Pure hanya mengekstrak teks tanpa pemformatan.

### Apakah Aspose.PDF untuk .NET kompatibel dengan .NET Core?
Ya, Aspose.PDF untuk .NET sepenuhnya kompatibel dengan .NET Core dan .NET Framework.