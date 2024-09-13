---
title: Hapus Font yang Disematkan dan Optimalkan File PDF
linktitle: Hapus Font yang Disematkan dan Optimalkan File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara membatalkan penyematan font dan mengoptimalkan file PDF menggunakan Aspose.PDF untuk .NET dalam tutorial langkah demi langkah ini.
type: docs
weight: 370
url: /id/net/programming-with-document/unembedfonts/
---
## Perkenalan

Di era digital, PDF ada di mana-mana. Baik Anda berbagi laporan, presentasi, atau eBook, Portable Document Format (PDF) adalah pilihan utama untuk menjaga integritas dokumen Anda. Namun, seiring kita membuat dan berbagi lebih banyak PDF, ukuran file dapat membengkak, sehingga sulit untuk dikirim atau disimpan. Di sinilah Aspose.PDF for .NET berperan, menawarkan alat yang hebat untuk mengoptimalkan file PDF Anda. Dalam tutorial ini, kita akan membahas cara menghapus font dan mengoptimalkan file PDF menggunakan Aspose.PDF for .NET.

## Prasyarat

Sebelum kita masuk ke inti pembahasan, mari pastikan Anda memiliki semua yang dibutuhkan untuk memulai:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di komputer Anda. Ini adalah IDE yang akan kita gunakan untuk menulis dan menjalankan kode .NET.
2.  Aspose.PDF untuk .NET: Anda perlu mengunduh dan memasang pustaka Aspose.PDF. Anda dapat mengunduhnya dari[tautan unduhan](https://releases.aspose.com/pdf/net/).
3. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan membantu Anda memahami potongan kode yang akan kita gunakan.
4.  File PDF: Siapkan file PDF yang ingin Anda optimalkan. Anda dapat menggunakan PDF apa pun, tetapi untuk demonstrasi, kami akan menyebutnya sebagai`OptimizeDocument.pdf`.

## Paket Impor

Untuk memulai, Anda perlu mengimpor paket yang diperlukan ke dalam proyek C# Anda. Berikut cara melakukannya:

1. Buka proyek Anda di Visual Studio.
2. Tambahkan referensi ke Aspose.PDF: Klik kanan pada proyek Anda di Solution Explorer, pilih "Kelola Paket NuGet," dan cari`Aspose.PDF`Instal paketnya.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Sekarang setelah semuanya disiapkan, mari kita uraikan proses pengoptimalan menjadi langkah-langkah yang lebih mudah dikelola.

## Langkah 1: Siapkan Direktori Dokumen Anda

Pertama-tama, Anda perlu menentukan jalur ke direktori dokumen Anda. Di sinilah file PDF Anda akan disimpan. Berikut cara melakukannya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat file PDF Anda berada. Hal ini penting karena program perlu mengetahui tempat menemukan PDF yang ingin Anda optimalkan.

## Langkah 2: Buka Dokumen PDF

Setelah direktori kita siap, saatnya membuka dokumen PDF yang ingin kita optimalkan. Berikut kode untuk melakukannya:

```csharp
// Buka dokumen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

 Baris kode ini membuat yang baru`Document` objek, yang mewakili berkas PDF Anda. Pastikan nama berkas sesuai dengan nama yang ada di direktori Anda.

## Langkah 3: Tetapkan Opsi Optimasi

Selanjutnya, kita perlu menentukan opsi pengoptimalan. Dalam kasus ini, kita ingin menghapus font yang disematkan. Berikut cara mengaturnya:

```csharp
// Tetapkan opsi UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    UnembedFonts = true
};
```

 Dengan pengaturan`UnembedFonts` ke`true`, kami menginstruksikan Aspose.PDF untuk mengoptimalkan PDF dengan menghapus font yang disematkan. Hal ini dapat mengurangi ukuran file secara signifikan, terutama jika PDF berisi banyak font yang disematkan.

## Langkah 4: Optimalkan Dokumen PDF

Setelah opsi yang kita tentukan, saatnya mengoptimalkan dokumen PDF. Berikut kode untuk melakukannya:

```csharp
Console.WriteLine("Start");
// Optimalkan dokumen PDF menggunakan OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

Potongan kode ini memanggil`OptimizeResources` metode pada`pdfDocument` objek, dengan menerapkan opsi pengoptimalan yang telah kami definisikan sebelumnya. Anda akan melihat pesan di konsol yang menunjukkan bahwa proses pengoptimalan telah dimulai.

## Langkah 5: Simpan Dokumen yang Diperbarui

Setelah mengoptimalkan PDF, kita perlu menyimpan dokumen yang telah diperbarui. Berikut cara melakukannya:

```csharp
// Simpan dokumen yang diperbarui
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
```

 Kode ini menyimpan PDF yang dioptimalkan sebagai`OptimizeDocument_out.pdf` dalam direktori yang sama. Anda dapat memilih nama yang berbeda jika Anda mau, tetapi dengan nama yang sama akan membantu mengidentifikasi versi asli dan yang sudah dioptimalkan.

## Langkah 6: Bandingkan Ukuran File

Terakhir, sebaiknya Anda selalu memeriksa berapa banyak ruang yang telah Anda hemat. Berikut cara membandingkan ukuran file asli dan yang dioptimalkan:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Kode ini mengambil ukuran file dari PDF asli dan PDF yang dioptimalkan, lalu mencetaknya ke konsol. Sungguh momen yang memuaskan untuk melihat seberapa besar Anda telah mengurangi ukuran file!

## Kesimpulan

Nah, itu dia! Anda telah berhasil menghapus font yang disematkan dan mengoptimalkan file PDF menggunakan Aspose.PDF untuk .NET. Proses ini tidak hanya membantu mengurangi ukuran file tetapi juga meningkatkan kinerja dokumen PDF Anda. Baik Anda berbagi file melalui email atau menyimpannya di cloud, ukuran file yang lebih kecil dapat membuat perbedaan besar.

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.PDF untuk .NET?
Aspose.PDF untuk .NET adalah pustaka hebat yang memungkinkan pengembang untuk membuat, memanipulasi, dan mengoptimalkan dokumen PDF secara terprogram.

### Dapatkah saya menggunakan Aspose.PDF secara gratis?
 Ya, Aspose menawarkan versi uji coba gratis. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/).

### Bagaimana cara mendapatkan dukungan untuk Aspose.PDF?
 Anda bisa mendapatkan dukungan melalui[Forum Aspose](https://forum.aspose.com/c/pdf/10).

### Jenis optimasi apa yang dapat saya lakukan pada PDF?
Anda dapat membatalkan penyematan font, mengompres gambar, menghapus objek yang tidak digunakan, dan masih banyak lagi untuk mengoptimalkan berkas PDF Anda.

### Di mana saya dapat membeli Aspose.PDF untuk .NET?
 Anda dapat membeli lisensi dari[Halaman pembelian Aspose](https://purchase.aspose.com/buy).