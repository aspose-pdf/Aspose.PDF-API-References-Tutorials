---
title: Hapus Font yang Disematkan dan Optimalkan File PDF
linktitle: Hapus Font yang Disematkan dan Optimalkan File PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menggunakan Aspose.PDF untuk .NET guna mendapatkan Font yang Tidak Disematkan dan mengoptimalkan file PDF. Panduan langkah demi langkah.
type: docs
weight: 370
url: /id/net/programming-with-document/unembedfonts/
---
Aspose.PDF untuk .NET adalah pustaka canggih yang menyediakan berbagai fitur untuk bekerja dengan dokumen PDF. Salah satu fiturnya adalah mendapatkan font yang tidak disematkan dari dokumen PDF. Ini dapat berguna jika Anda perlu mengekstrak font dari dokumen PDF dan menggunakannya di aplikasi lain.

kami akan memberikan panduan langkah demi langkah untuk menjelaskan kode sumber C# berikut untuk fitur mendapatkan font yang tidak tertanam di Aspose.PDF untuk .NET.

## Langkah 1: Tetapkan jalur ke direktori dokumen

Sebelum memulai, kita perlu mengatur jalur ke direktori tempat dokumen PDF kita berada. Kita akan menyimpan jalur ini dalam variabel yang disebut "dataDir".

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat dokumen PDF Anda berada.

## Langkah 2: Buka Dokumen PDF

 Langkah pertama adalah memuat dokumen PDF yang ingin Anda lakukan ini, gunakan`Document` kelas Aspose.PDF untuk .NET. Potongan kode berikut menunjukkan cara memuat dokumen PDF:

```csharp
// Buka dokumen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Langkah 3: Mengatur Opsi UnembedFonts

 Untuk mendapatkan font yang tidak tertanam dari dokumen PDF, Anda perlu mengatur`UnembedFonts` pilihan untuk`true` Opsi ini tersedia di`OptimizationOptions` kelas. Potongan kode berikut menunjukkan cara mengatur`UnembedFonts` pilihan:

```csharp
// Tetapkan opsi UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Langkah 4: Optimalkan Dokumen PDF

 Setelah mengatur`UnembedFonts` pilihan, Anda dapat mengoptimalkan dokumen PDF menggunakan`OptimizeResources` metode dari`Document` kelas. Potongan kode berikut menunjukkan cara mengoptimalkan dokumen PDF:

```csharp
// Optimalkan dokumen PDF menggunakan OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Langkah 5: Simpan Dokumen yang Diperbarui

 Setelah dokumen PDF dioptimalkan, Anda dapat menyimpan dokumen yang diperbarui menggunakan`Save` metode dari`Document`kelas. Potongan kode berikut menunjukkan cara menyimpan dokumen yang diperbarui:

```csharp
// Simpan dokumen yang diperbarui
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Langkah 6: Dapatkan Ukuran File Asli dan yang Diperkecil

 Akhirnya, Anda bisa mendapatkan ukuran file asli dan diperkecil dari dokumen PDF menggunakan`FileInfo` kelas System.IO. Potongan kode berikut menunjukkan cara mendapatkan ukuran file asli dan yang diperkecil:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Contoh Kode Sumber untuk Mendapatkan Font yang Tidak Disematkan menggunakan Aspose.PDF untuk .NET

Berikut adalah contoh kode sumber lengkap untuk mendapatkan font yang tidak tertanam dari dokumen PDF menggunakan Aspose.PDF untuk .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Tetapkan opsi UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// Optimalkan dokumen PDF menggunakan OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// Simpan dokumen yang diperbarui
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Kesimpulan

Dalam tutorial ini, kami menunjukkan cara menggunakan Aspose.PDF untuk .NET guna mendapatkan font yang tidak disematkan dari dokumen PDF. Dengan mengikuti panduan langkah demi langkah, Anda dapat dengan mudah menerapkan fitur ini dalam aplikasi C# Anda. Font yang tidak disematkan dapat bermanfaat saat Anda perlu bekerja dengan font yang diekstrak secara terpisah atau memastikan penggunaan font yang konsisten di berbagai platform.

## Pertanyaan yang Sering Diajukan

#### T: Apa tujuan menghapus font dari dokumen PDF?

A: Dengan menghapus font yang disematkan dari dokumen PDF, Anda dapat mengekstrak font yang disematkan dan menggunakannya di aplikasi lain. Ini berguna untuk memastikan tampilan font yang konsisten dan mempertahankan tampilan visual dokumen.

#### T: Bagaimana cara menentukan jalur ke direktori dokumen dalam kode C#?

 A: Untuk menentukan jalur ke direktori dokumen, ganti`"YOUR DOCUMENT DIRECTORY"` dalam kode dengan jalur sebenarnya ke direktori tempat dokumen PDF Anda berada.

####  T: Apa yang dimaksud dengan`UnembedFonts` option do, and where is it set?

 Sebuah:`UnembedFonts` pilihan, tersedia di`OptimizationOptions` kelas, mengaktifkan atau menonaktifkan pelepasan font dari dokumen PDF. Untuk menyetel opsi ini ke`true`, gunakan kode berikut:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### T: Dapatkah saya mengembalikan perubahan yang dibuat selama proses pengoptimalan?

J: Aspose.PDF untuk .NET tidak membuat perubahan permanen pada dokumen PDF asli selama pengoptimalan. Proses pengoptimalan dilakukan pada salinan dokumen, dengan membiarkan dokumen asli tetap utuh.

#### T: Bagaimana cara memeriksa ukuran file asli dan yang diperkecil setelah pengoptimalan?

 A: Kamu bisa menggunakan`FileInfo` kelas dari`System.IO` untuk mendapatkan ukuran file asli dan yang diperkecil. Berikut ini contoh potongan kode untuk mencapainya:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```