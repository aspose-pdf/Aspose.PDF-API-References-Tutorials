---
title: Hapus Sematan Font Dan Optimalkan File PDF
linktitle: Hapus Sematan Font Dan Optimalkan File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menggunakan Aspose.PDF untuk .NET untuk mendapatkan Font yang Tidak Disematkan dan mengoptimalkan file PDF. Panduan langkah demi langkah.
type: docs
weight: 370
url: /id/net/programming-with-document/unembedfonts/
---
Aspose.PDF untuk .NET adalah perpustakaan canggih yang menyediakan berbagai fitur untuk bekerja dengan dokumen PDF. Salah satu fiturnya adalah mendapatkan font yang tidak disematkan dari dokumen PDF. Ini berguna jika Anda perlu mengekstrak font dari dokumen PDF dan menggunakannya di aplikasi lain.

kami akan memberikan panduan langkah demi langkah untuk menjelaskan kode sumber C# berikut untuk mendapatkan fitur font yang tidak tersemat di Aspose.PDF untuk .NET.

## Langkah 1: Tetapkan jalur ke direktori dokumen

Sebelum kita mulai, kita perlu mengatur path ke direktori dimana dokumen PDF kita berada. Kami akan menyimpan jalur ini dalam variabel bernama "dataDir".

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori tempat dokumen PDF Anda berada.

## Langkah 2: Buka Dokumen PDF

 Langkah pertama adalah memuat dokumen PDF yang ingin Anda lakukan, gunakan`Document` kelas Aspose.PDF untuk .NET. Cuplikan kode berikut menunjukkan cara memuat dokumen PDF:

```csharp
// Buka dokumen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Langkah3: Atur Opsi UnembedFonts

 Untuk mendapatkan font yang tidak disematkan dari dokumen PDF, Anda perlu mengaturnya`UnembedFonts` pilihan untuk`true` . Opsi ini tersedia di`OptimizationOptions` kelas. Cuplikan kode berikut menunjukkan cara menyetel`UnembedFonts` pilihan:

```csharp
// Setel opsi UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Langkah 4: Optimalkan Dokumen PDF

 Setelah mengatur`UnembedFonts` pilihan, Anda dapat mengoptimalkan dokumen PDF menggunakan`OptimizeResources` metode`Document` kelas. Cuplikan kode berikut menunjukkan cara mengoptimalkan dokumen PDF:

```csharp
// Optimalkan dokumen PDF menggunakan OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Langkah 5: Simpan Dokumen yang Diperbarui

 Setelah dokumen PDF dioptimalkan, Anda dapat menyimpan dokumen yang diperbarui menggunakan`Save` metode`Document`kelas. Cuplikan kode berikut menunjukkan cara menyimpan dokumen yang diperbarui:

```csharp
// Simpan dokumen yang diperbarui
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Langkah 6: Dapatkan Ukuran File Asli dan Diperkecil

 Terakhir, Anda bisa mendapatkan ukuran file dokumen PDF asli dan diperkecil menggunakan`FileInfo` kelas Sistem.IO. Cuplikan kode berikut menunjukkan cara mendapatkan ukuran file asli dan diperkecil:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Contoh Kode Sumber untuk Mendapatkan Font yang Tidak Disematkan menggunakan Aspose.PDF untuk .NET

Berikut adalah contoh lengkap kode sumber untuk mendapatkan font yang tidak disematkan dari dokumen PDF menggunakan Aspose.PDF untuk .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Setel opsi UnembedFonts
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

Dalam tutorial ini, kami mendemonstrasikan cara menggunakan Aspose.PDF untuk .NET untuk mendapatkan font yang tidak disematkan dari dokumen PDF. Dengan mengikuti panduan langkah demi langkah, Anda dapat dengan mudah mengimplementasikan fitur ini di aplikasi C# Anda. Membatalkan penyematan font dapat bermanfaat ketika Anda perlu bekerja dengan font yang diekstraksi secara terpisah atau memastikan penggunaan font yang konsisten di berbagai platform.

## FAQ

#### T: Apa tujuan tidak menyematkan font dari dokumen PDF?

J: Membatalkan penyematan font dari dokumen PDF memungkinkan Anda mengekstrak font yang disematkan dan menggunakannya di aplikasi lain. Hal ini berguna untuk memastikan rendering font yang konsisten dan menjaga tampilan visual dokumen.

#### T: Bagaimana cara menentukan jalur ke direktori dokumen dalam kode C#?

 A: Untuk menentukan jalur ke direktori dokumen, ganti`"YOUR DOCUMENT DIRECTORY"` dalam kode dengan jalur sebenarnya ke direktori tempat dokumen PDF Anda berada.

####  T: Apa yang dimaksud dengan`UnembedFonts` option do, and where is it set?

 J: Itu`UnembedFonts` pilihan, tersedia di`OptimizationOptions` kelas, mengaktifkan atau menonaktifkan penyisipan font dari dokumen PDF. Untuk menyetel opsi ini ke`true`, gunakan kode berikut:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### T: Dapatkah saya mengembalikan perubahan yang dibuat selama proses pengoptimalan?

J: Aspose.PDF untuk .NET tidak membuat perubahan permanen pada dokumen PDF asli selama optimasi. Proses optimasi dilakukan pada salinan dokumen, membiarkan aslinya tetap utuh.

#### T: Bagaimana cara memeriksa ukuran file asli dan yang diperkecil setelah pengoptimalan?

J: Anda dapat menggunakan`FileInfo` kelas`System.IO` untuk mendapatkan ukuran file asli dan diperkecil. Berikut ini contoh cuplikan kode untuk mencapai hal ini:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```