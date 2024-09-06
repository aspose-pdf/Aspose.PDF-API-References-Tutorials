---
title: Dapatkan Dimensi Halaman PDF
linktitle: Dapatkan Dimensi Halaman PDF
second_title: Referensi API Aspose.PDF untuk .NET
description: Dalam tutorial ini, kami menjelaskan cara mendapatkan dimensi halaman PDF dan melakukan manipulasi menggunakan Aspose.PDF untuk .NET. Langkah-langkah terperinci disediakan untuk memandu Anda melalui proses tersebut.
type: docs
weight: 60
url: /id/net/programming-with-pdf-pages/get-dimensions/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk mendapatkan dimensi halaman dalam file PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan kode sumber C# yang disertakan dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan mengetahui cara mendapatkan dimensi halaman dalam file PDF menggunakan Aspose.PDF untuk .NET.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#
- Aspose.PDF untuk .NET terinstal di lingkungan pengembangan Anda

## Langkah 1: Tentukan direktori dokumen
Pertama, Anda perlu mengatur jalur ke direktori dokumen Anda. Ini adalah lokasi tempat berkas PDF Anda berada. Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Buka dokumen PDF
 Kemudian Anda dapat membuka file PDF menggunakan`Document` kelas Aspose.PDF. Pastikan untuk menentukan jalur yang benar ke berkas PDF.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Langkah 3: Tambahkan halaman kosong (jika diperlukan)
 Jika dokumen PDF sudah berisi halaman, Anda dapat melompat ke halaman yang ada menggunakan indeks`1` (halaman pertama memiliki indeks 1). Jika tidak, Anda dapat menambahkan halaman baru ke dokumen tersebut.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Langkah 4: Dapatkan dimensi halaman
 Anda sekarang bisa mendapatkan dimensi halaman menggunakan`GetPageRect()` metode dari`Page` objek. Metode ini mengembalikan`Rectangle` objek yang berisi dimensi halaman. Anda dapat mengakses lebar dan tinggi menggunakan`Width` Dan`Height` properti.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Langkah 5: Putar halaman
 Jika Anda ingin memutar halaman, Anda dapat menggunakan`Rotate` milik`Page`objek. Dalam contoh ini, halaman diputar 90 derajat.

```csharp
page. Rotate = Rotate. on90;
```

## Langkah 6: Dapatkan kembali dimensi halaman
 Setelah rotasi halaman, Anda bisa mendapatkan dimensi halaman lagi menggunakan`GetPageRect()` metode.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Contoh kode sumber untuk Mendapatkan Dimensi menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Menambahkan halaman kosong ke dokumen pdf
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Dapatkan informasi tinggi dan lebar halaman
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Putar halaman pada sudut 90 derajat
page.Rotate = Rotation.on90;
// Dapatkan informasi tinggi dan lebar halaman
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mendapatkan dimensi halaman dalam file PDF menggunakan Aspose.PDF for .NET. Dengan mengikuti langkah-langkah yang diberikan, Anda dapat dengan mudah mengekstrak dimensi halaman dan melakukan operasi manipulasi PDF lainnya. Aspose.PDF for .NET menawarkan fleksibilitas yang tinggi untuk bekerja dengan file PDF dan memungkinkan Anda mengembangkan solusi yang canggih dan disesuaikan.

Jangan ragu untuk menjelajahi dokumentasi Aspose.PDF lebih lanjut untuk menemukan semua fitur yang ditawarkan oleh pustaka ini.

### FAQ untuk mendapatkan dimensi halaman PDF

#### T: Bagaimana cara mendapatkan dimensi halaman tertentu dalam berkas PDF?

A: Untuk mendapatkan dimensi halaman tertentu dalam file PDF, Anda dapat menggunakan`GetPageRect()` metode dari`Page` objek di Aspose.PDF untuk .NET. Metode ini mengembalikan`Rectangle` objek yang berisi dimensi (lebar dan tinggi) halaman.

####  T: Apa yang dimaksud dengan`GetPageRect(true)` method do in the provided C# source code?

 Sebuah:`GetPageRect(true)` metode dalam kode sumber C# yang diberikan mengembalikan dimensi halaman setelah menerapkan rotasi apa pun. Jika halaman diputar, metode akan mengembalikan dimensi halaman yang diputar, yang mungkin berbeda dari dimensi aslinya.

#### T: Bisakah saya mendapatkan dimensi semua halaman dalam dokumen PDF menggunakan Aspose.PDF untuk .NET?

 A: Ya, Anda bisa mendapatkan dimensi semua halaman dalam dokumen PDF dengan mengulangi`Pages` koleksi dari`Document` objek dan menggunakan`GetPageRect(true)` metode untuk setiap halaman.

#### T: Bagaimana cara menentukan orientasi halaman (potret atau lanskap) berdasarkan dimensinya?

A: Untuk menentukan orientasi halaman berdasarkan dimensinya, Anda dapat membandingkan lebar dan tinggi halaman. Jika lebarnya lebih besar dari tingginya, halaman tersebut berorientas lanskap, dan jika tingginya lebih besar dari lebarnya, halaman tersebut berorientas potret.

#### T: Dapatkah saya mengubah dimensi halaman menggunakan Aspose.PDF untuk .NET?

 A: Ya, Anda dapat mengubah dimensi halaman di Aspose.PDF untuk .NET. Setelah mendapatkan`Rectangle` objek yang mewakili dimensi halaman, Anda dapat menyesuaikan lebar dan tinggi sesuai kebutuhan Anda lalu menerapkan perubahan ke halaman.