---
title: Algoritma Bradley
linktitle: Algoritma Bradley
second_title: Referensi API Aspose.PDF untuk .NET
description: Konversi dokumen PDF menggunakan algoritma Bradley dengan Aspose.PDF untuk .NET.
type: docs
weight: 30
url: /id/net/programming-with-images/bradley-algorithm/
---
Panduan langkah demi langkah ini menjelaskan cara menggunakan Algoritma Bradley dengan Aspose.PDF untuk .NET. Pastikan Anda telah menyiapkan lingkungan Anda dan ikuti langkah-langkah di bawah ini:

## Langkah 1: Tentukan direktori dokumen

Sebelum memulai, pastikan Anda mengatur direktori yang benar untuk dokumen tersebut. Ganti`"YOUR DOCUMENT DIRECTORY"` dalam kode dengan jalur ke direktori tempat dokumen PDF Anda berada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buka dokumen

 Pada langkah ini, kita akan membuka dokumen PDF menggunakan`Document` kelas Aspose.PDF. Gunakan`Document` konstruktor dan meneruskan jalur ke dokumen PDF.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Langkah 3: Tentukan file keluaran

 Tentukan nama file keluaran untuk gambar yang dihasilkan dan gambar biner. Ganti`"resultant_out.tif"` Dan`"37116-bin_out.tif"` dengan nama yang diinginkan untuk file keluaran.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Langkah 4: Buat objek Resolusi

 Membuat sebuah`Resolution` objek untuk mengatur resolusi gambar TIFF. Dalam contoh ini, kami menggunakan resolusi 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Langkah 5: Buat objek TiffSettings

 Membuat sebuah`TiffSettings` objek untuk menentukan pengaturan untuk file TIFF keluaran. Dalam contoh ini, kami menggunakan kompresi LZW dan kedalaman warna 1 bit per piksel (format 1 bpp).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## Langkah 6: Buat perangkat TIFF

 Buat perangkat TIFF menggunakan`TiffDevice` objek, menentukan resolusi dan pengaturan TIFF.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Langkah 7: Konversi halaman tertentu dan simpan gambarnya

 Gunakan`Process` metode perangkat TIFF untuk mengonversi halaman tertentu dari dokumen PDF dan menyimpan gambar ke berkas TIFF. Tentukan jalur keluaran berkas.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Langkah 8: Binerisasi gambar menggunakan algoritma Bradley

 Gunakan`BinarizeBradley`metode perangkat TIFF untuk melakukan binerisasi gambar menggunakan algoritma Bradley. Metode ini mengambil aliran masukan dari gambar asli dan aliran keluaran untuk gambar biner. Tentukan ambang binerisasi (0,1 dalam contoh ini).

```csharp
using (FileStream

  inStream = new FileStream(outputImageFile, FileMode.Open))
{
using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
{
tiffDevice. Binarize Bradley(inStream, outStream, 0.1);
}
}
```

### Contoh kode sumber untuk Algoritma Bradley menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
// Buat objek Resolusi
Resolution resolution = new Resolution(300);
// Buat objek TiffSettings
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// Buat perangkat TIFF
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// Konversi halaman tertentu dan simpan gambar ke streaming
tiffDevice.Process(pdfDocument, outputImageFile);
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
	using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
	{
		tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
	}
}
System.Console.WriteLine("Conversion using bradley algorithm performed successfully!");
```

## Kesimpulan

Selamat! Anda telah berhasil menyelesaikan konversi menggunakan algoritma Bradley dengan Aspose.PDF untuk .NET. Kini Anda dapat menggunakan gambar yang dihasilkan dalam proyek atau aplikasi Anda.

### Pertanyaan yang Sering Diajukan

#### T: Apa itu Algoritma Bradley dan bagaimana hubungannya dengan Aspose.PDF untuk .NET?

J: Algoritma Bradley adalah teknik pemrosesan gambar yang digunakan untuk meningkatkan kualitas dan kejelasan gambar. Aspose.PDF untuk .NET menyediakan cara mudah untuk menerapkan Algoritma Bradley ke dokumen PDF, sehingga menghasilkan gambar yang lebih baik.

#### T: Bagaimana cara mengatur lingkungan saya untuk menggunakan Algoritma Bradley dengan Aspose.PDF untuk .NET?

A: Sebelum memulai, pastikan Anda telah menginstal Aspose.PDF untuk .NET dengan benar dan lingkungan pengembangan Anda dikonfigurasi.

#### T: Apa pentingnya mendefinisikan direktori dokumen dalam proses Algoritma Bradley?

A: Menentukan direktori dokumen yang benar sangat penting untuk memastikan bahwa dokumen PDF berada di jalur yang tepat untuk diproses.

#### T: Bagaimana cara membuka dokumen PDF menggunakan Aspose.PDF untuk .NET dalam Algoritma Bradley?

 A: Gunakan`Document` kelas untuk membuka dokumen PDF, yang berfungsi sebagai input untuk proses Algoritma Bradley.

#### T: Apa tujuan mendefinisikan nama file keluaran untuk gambar dan gambar biner dalam proses Algoritma Bradley?

A: Menentukan nama file keluaran memungkinkan Anda menentukan di mana gambar yang dihasilkan dan gambar biner akan disimpan setelah menerapkan Algoritma Bradley.

#### T: Bagaimana pengaturan resolusi memengaruhi kualitas gambar TIFF dalam proses Algoritma Bradley?

A: Pengaturan resolusi menentukan tingkat detail dan kejelasan pada gambar TIFF yang dihasilkan setelah menerapkan Algoritma Bradley.

#### T: Pengaturan apa yang dapat saya sesuaikan untuk gambar TIFF keluaran dalam proses Algoritma Bradley?
A: Anda dapat menyesuaikan pengaturan seperti jenis kompresi dan kedalaman warna untuk mencapai hasil yang diinginkan untuk gambar TIFF.

#### T: Bagaimana perangkat TIFF berkontribusi pada proses Algoritma Bradley?

A: Perangkat TIFF berfungsi sebagai alat untuk memproses gambar dan menerapkan Algoritma Bradley, sehingga menghasilkan peningkatan kualitas gambar.

#### T: Bagaimana cara mengonversi halaman tertentu dari dokumen PDF ke gambar TIFF dalam proses Algoritma Bradley?

 A: Memanfaatkan`Process` metode perangkat TIFF untuk mengubah halaman tertentu dokumen PDF menjadi gambar TIFF, yang kemudian dapat diproses lebih lanjut menggunakan Algoritma Bradley.