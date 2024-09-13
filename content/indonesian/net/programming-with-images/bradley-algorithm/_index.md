---
title: Algoritma Bradley
linktitle: Algoritma Bradley
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara mengonversi PDF ke TIFF menggunakan algoritma Bradley di Aspose.PDF untuk .NET. Panduan langkah demi langkah, prasyarat, dan Tanya Jawab Umum untuk konversi yang lancar.
type: docs
weight: 30
url: /id/net/programming-with-images/bradley-algorithm/
---
## Perkenalan

Bekerja dengan file PDF terkadang menuntut lebih dari sekadar membaca atau mengeditnya—Anda mungkin perlu mengubahnya menjadi gambar. Salah satu cara ampuh untuk mengubah PDF menjadi gambar TIFF adalah dengan menggunakan Algoritma Bradley melalui pustaka Aspose.PDF for .NET. Metode ini memastikan gambar biner berkualitas tinggi, sempurna untuk pengarsipan dokumen dan kasus penggunaan khusus lainnya.

Tutorial ini akan memandu Anda melalui proses yang terperinci dan mudah diikuti untuk mengonversi halaman PDF menjadi gambar TIFF dengan Algoritma Binarisasi Bradley. Aspose.PDF untuk .NET menyederhanakan tugas ini, memberi Anda kemampuan untuk mengotomatiskan dan menyederhanakan alur kerja dokumen Anda.

## Prasyarat

Sebelum kita masuk ke kodenya, mari pastikan Anda sudah memiliki semua yang perlu diikuti:

-  Aspose.PDF untuk .NET: Anda memerlukan pustakanya. Unduh dari[Di Sini](https://releases.aspose.com/pdf/net/).
- Visual Studio (atau IDE C# apa pun).
- Pengetahuan dasar tentang C#.
-  Lisensi yang valid atau[lisensi sementara](https://purchase.aspose.com/temporary-license/) dari Aspose.

## Paket Impor

Pertama-tama, pastikan untuk mengimpor namespace yang diperlukan ke dalam proyek Anda. Pustaka ini akan menyediakan alat untuk memanipulasi dokumen PDF, mengonversinya ke format TIFF, dan menerapkan algoritma binarisasi Bradley.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Mari kita uraikan prosesnya menjadi beberapa langkah mudah untuk memastikan Anda dapat mengikutinya dengan lancar. Di akhir panduan ini, Anda akan berhasil mengonversi halaman PDF menjadi gambar TIFF biner menggunakan algoritma Bradley.

## Langkah 1: Mengatur Direktori Dokumen

Langkah pertama adalah menentukan jalur ke direktori tempat dokumen PDF Anda berada. Anda juga akan menentukan jalur keluaran untuk gambar TIFF yang akan dihasilkan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Jalur ke file PDF Anda
```

Di sinilah Anda menyimpan file PDF sumber dan file TIFF yang dikonversi. Pastikan direktori diatur dengan benar sehingga kode dapat membaca dan menulis file tanpa kesalahan.

## Langkah 2: Buka Dokumen PDF

Setelah jalurnya ditetapkan, saatnya membuka dokumen PDF yang ingin Anda konversi. Aspose.PDF untuk .NET memudahkan pemuatan dokumen untuk diproses lebih lanjut.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

 Di Sini,`PageToTIFF.pdf` adalah contoh berkas. Anda dapat menggantinya dengan berkas PDF pilihan Anda. Objek dokumen sekarang menyimpan PDF untuk manipulasi lebih lanjut.

## Langkah 3: Tentukan Jalur Output untuk Gambar

Berikutnya, Anda akan menentukan jalur keluaran untuk file TIFF yang dihasilkan, termasuk TIFF standar dan versi biner.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

Dengan memisahkan jalur ini, Anda akan memiliki satu file untuk konversi TIFF standar dan file lainnya untuk gambar biner setelah algoritma Bradley diterapkan.

## Langkah 4: Buat Objek Resolusi

Saat mengonversi PDF ke TIFF, resolusi memegang peranan penting dalam menentukan kualitas gambar. Untuk keperluan kita, kita akan menyetelnya ke 300 DPI untuk memastikan hasil berkualitas tinggi.

```csharp
Resolution resolution = new Resolution(300);
```

DPI yang lebih tinggi berarti kejelasan gambar yang lebih baik, terutama saat menangani dokumen yang akan dicetak atau diarsipkan.

## Langkah 5: Konfigurasikan Pengaturan TIFF

Selanjutnya, Anda perlu mengonfigurasi pengaturan untuk gambar TIFF. Di sini, kita akan menggunakan Kompresi LZW dan mengatur kedalaman warna menjadi 1bpp (1-bit per piksel) untuk memperoleh gambar biner.

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

Dengan menetapkan kedalaman ke 1bpp, kami menyiapkan gambar untuk keluaran biner. Kompresi LZW dipilih karena efisiensinya dalam mengurangi ukuran file tanpa kehilangan kualitas.

## Langkah 6: Buat Perangkat TIFF

Sekarang, Anda perlu membuat perangkat TIFF yang akan menangani konversi. Perangkat ini menggunakan resolusi dan pengaturan TIFF yang ditetapkan sebelumnya.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

Perangkat TIFF merupakan inti dari operasi ini. Perangkat ini mengambil dokumen PDF dan mengonversi setiap halaman menjadi gambar TIFF, berdasarkan pengaturan yang telah Anda tentukan sebelumnya.

## Langkah 7: Ubah Halaman PDF ke TIFF

 Saatnya memproses PDF dan mengonversi halaman pertama menjadi gambar TIFF.`Process` Metode ini memungkinkan Anda mengonversi halaman tertentu atau seluruh dokumen. Dalam contoh ini, kami mengonversi halaman pertama.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

Setelah metode selesai, Anda akan memiliki gambar TIFF yang tersimpan di lokasi yang ditentukan sebelumnya.

## Langkah 8: Terapkan Algoritma Binarisasi Bradley

Kini hadir keajaiban—Algoritma Bradley! Algoritma ini mengubah gambar TIFF skala abu-abu menjadi gambar biner, mengoptimalkannya untuk sistem pengenalan dokumen.

```csharp
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
    using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
    {
        tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
    }
}
```

 Metode BinarizeBradley mengambil dua aliran file (input dan output), serta nilai ambang batas (di sini,`0.1`) yang menentukan tingkat binerisasi. Setelah eksekusi, Anda akan memiliki gambar binerisasi sempurna yang siap digunakan.

## Langkah 9: Konfirmasikan Konversi Berhasil

Terakhir, sebaiknya Anda memberi tahu pengguna bahwa prosesnya berhasil. Anda dapat melakukannya dengan output konsol sederhana.

```csharp
System.Console.WriteLine("Conversion using Bradley algorithm performed successfully!");
```

Setelah dicetak, Anda tahu halaman PDF Anda telah berhasil diubah menjadi gambar TIFF biner!

## Kesimpulan

Nah, itu dia! Anda baru saja mempelajari cara mengonversi halaman PDF menjadi gambar TIFF dan menerapkan algoritma binarisasi Bradley menggunakan Aspose.PDF untuk .NET. Proses ini penting untuk pengarsipan dokumen, pengenalan karakter optik (OCR), dan aplikasi profesional lainnya. Dengan resolusi berkualitas tinggi dan kompresi yang efisien, Anda dapat memastikan bahwa gambar dokumen Anda jelas dan ukurannya dapat diatur.

## Pertanyaan yang Sering Diajukan

### Apa itu Algoritma Bradley?
Algoritma Bradley adalah teknik binarisasi yang mengubah gambar skala abu-abu menjadi gambar biner (hitam dan putih) dengan menentukan ambang batas adaptif untuk setiap piksel berdasarkan lingkungannya.

### Bisakah saya mengonversi beberapa halaman PDF ke TIFF menggunakan metode ini?
 Ya, Anda dapat memodifikasi`Process` metode untuk mengonversi semua halaman dengan melakukan pengulangan melalui halaman-halaman dalam dokumen.

### Berapa resolusi optimal untuk mengonversi PDF ke TIFF?
Untuk gambar berkualitas tinggi, 300 DPI umumnya direkomendasikan. Namun, Anda dapat menyesuaikan nilai ini berdasarkan kebutuhan Anda.

### Apa arti 1bpp dalam kedalaman warna?
1bpp (1 bit per piksel) berarti gambar akan berwarna hitam dan putih, dengan setiap piksel sepenuhnya hitam atau sepenuhnya putih.

### Apakah Algoritma Bradley cocok untuk OCR?
Ya, Algoritma Bradley sering digunakan dalam praproses OCR karena meningkatkan kontras teks dalam dokumen yang dipindai.