---
title: Izinkan Penggunaan Kembali Konten Halaman
linktitle: Izinkan Penggunaan Kembali Konten Halaman
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengoptimalkan PDF dengan mengaktifkan fitur "Izinkan Penggunaan Kembali Konten Halaman" menggunakan Aspose.PDF untuk .NET. Kurangi ukuran file dan tingkatkan kinerja.
type: docs
weight: 50
url: /id/net/programming-with-document/allowresusepagecontent/
---
Dalam tutorial ini, kami akan menjelaskan cara mengaktifkan fitur "Izinkan Penggunaan Kembali Konten Halaman" menggunakan Aspose.PDF untuk .NET. Fitur ini mengoptimalkan dokumen PDF dengan menggunakan kembali konten halaman, mengurangi ukuran file, dan meningkatkan kinerja. Ikuti panduan langkah demi langkah di bawah ini:

## Langkah 1: Muat dokumen PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Langkah 2: Setel opsi AllowReusePageContent

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## Langkah 3: Optimalkan dokumen PDF

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Langkah 4: Simpan dokumen yang diperbarui

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Langkah 5: Periksa pengurangan ukuran file

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Selamat! Anda telah berhasil mengizinkan penggunaan kembali konten halaman dalam dokumen PDF Anda.

### Contoh kode sumber untuk Mengizinkan Penggunaan Kembali Konten Halaman menggunakan Aspose.PDF untuk .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// Setel opsi AllowReusePageContent
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
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

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

Sekarang Anda dapat mengoptimalkan dokumen PDF Anda secara efektif dengan mengizinkan penggunaan kembali konten halaman.

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara mengaktifkan fitur "Izinkan Penggunaan Kembali Konten Halaman" menggunakan Aspose.PDF untuk .NET. Dengan mengikuti panduan langkah demi langkah yang disediakan dan memanfaatkan kode sumber C#, Anda dapat mengoptimalkan dokumen PDF Anda secara efektif dengan mengizinkan penggunaan kembali konten halaman. Pengoptimalan ini menghasilkan file PDF yang lebih kecil, yang dapat mempercepat waktu pemuatan dan meningkatkan kinerja saat menangani dokumen PDF berukuran besar. Aspose.PDF untuk .NET memberikan solusi yang kuat dan mudah digunakan untuk pengoptimalan PDF, memungkinkan Anda membuat file PDF yang efisien dan berkualitas tinggi dengan mudah.

### FAQ

#### T: Apa tujuan mengaktifkan fitur "Izinkan Penggunaan Kembali Konten Halaman" di dokumen PDF?

J: Mengaktifkan fitur "Izinkan Penggunaan Kembali Konten Halaman" dalam dokumen PDF akan mengoptimalkan file dengan menggunakan kembali konten halaman, sehingga mengurangi ukuran file dan meningkatkan kinerja secara keseluruhan. Pengoptimalan ini menghasilkan file PDF yang lebih kecil tanpa mengurangi kualitas konten.

#### T: Bagaimana cara kerja fitur "Izinkan Penggunaan Kembali Konten Halaman"?

J: Ketika fitur "Izinkan Penggunaan Kembali Konten Halaman" diaktifkan, objek halaman identik dalam dokumen PDF akan dibagikan dan digunakan kembali, bukannya diduplikasi untuk setiap kemunculan. Berbagi konten halaman ini secara signifikan mengurangi ukuran file secara keseluruhan.

#### T: Dapatkah saya mengembalikan pengoptimalan dan memulihkan dokumen asli?

J: Tidak, setelah optimasi dengan "Izinkan Penggunaan Kembali Konten Halaman" dilakukan dan dokumen PDF disimpan, perubahannya bersifat permanen. Dianjurkan untuk menyimpan cadangan dokumen asli sebelum melakukan optimasi apa pun.

#### Q: Apakah mengaktifkan fitur ini akan mempengaruhi tampilan visual atau isi dokumen PDF?

A: Mengaktifkan fitur "Izinkan Penggunaan Kembali Konten Halaman" tidak mempengaruhi tampilan visual atau konten dokumen PDF. Ini hanya mengoptimalkan struktur internal file untuk mengurangi redundansi dan meningkatkan efisiensi.

#### T: Apakah Aspose.PDF untuk .NET merupakan solusi yang andal untuk pengoptimalan dan manipulasi PDF?

J: Ya, Aspose.PDF untuk .NET adalah perpustakaan yang andal dan kaya fitur untuk pengoptimalan dan manipulasi PDF. Ini menawarkan opsi ekstensif untuk mengoptimalkan file PDF, termasuk mengurangi ukuran file, menghapus sumber daya yang tidak terpakai, dan meningkatkan kinerja secara keseluruhan.