---
title: Sematkan Font Dalam File PDF Dengan Strategi Subset
linktitle: Sematkan Font Dengan Strategi Subset
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menyematkan font dalam file PDF dengan Subset Strategy menggunakan Aspose.PDF untuk .NET. Optimalkan ukuran PDF Anda dengan hanya menyematkan karakter yang diperlukan.
type: docs
weight: 130
url: /id/net/programming-with-document/embedfontsusingsubsetstrategy/
---
Pada tutorial kali ini kita akan membahas cara menyematkan font pada file PDF dengan strategi subset menggunakan Aspose.PDF for .NET. Aspose.PDF untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang membuat, mengedit, dan memanipulasi dokumen PDF secara terprogram. Menyematkan font dalam file PDF merupakan langkah penting untuk memastikan bahwa dokumen ditampilkan dengan benar di perangkat yang berbeda, terlepas dari apakah font yang diperlukan diinstal pada perangkat tersebut atau tidak.

## Langkah 1: Buat Aplikasi Konsol C# baru
Untuk memulai, buat Aplikasi Konsol C# baru di Visual Studio. Anda dapat menamainya sesuka Anda. Setelah proyek dibuat, Anda perlu menambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Impor Namespace Aspose.PDF
Tambahkan baris kode berikut di bagian atas file C# Anda untuk mengimpor namespace Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Langkah 3: Muat File PDF yang Ada
Untuk menyematkan font dalam file PDF yang ada, Anda perlu memuat file tersebut menggunakan kelas Dokumen. Kode berikut menunjukkan cara memuat file PDF yang ada:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Muat file PDF yang ada
Document doc = new Document(dataDir + "input.pdf");
```

## Langkah 4: Sematkan Font dengan Strategi Subset
Aspose.PDF untuk .NET menyediakan dua strategi untuk penyematan font: SubsetAllFonts dan SubsetEmbeddedFontsOnly.

Strategi SubsetAllFonts akan menyematkan semua font dalam dokumen sebagai subset. Subset adalah bagian font yang hanya berisi karakter yang digunakan dalam dokumen. Strategi ini berguna untuk memperkecil ukuran file dokumen PDF.

Strategi SubsetEmbeddedFontsOnly hanya akan menyematkan subset font yang sudah tertanam dalam dokumen. Jika font tidak disematkan, maka tidak akan terpengaruh oleh strategi ini.

Kode berikut menunjukkan cara menyematkan font dalam file PDF dengan strategi subset:

```csharp
// Semua font akan disematkan sebagai subset ke dalam dokumen jika SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

// Subset font akan disematkan untuk font yang tertanam sepenuhnya tetapi font yang tidak tertanam ke dalam dokumen tidak akan terpengaruh.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## Langkah 5: Simpan Dokumen PDF
Setelah Anda menyematkan semua font dalam file PDF dengan strategi subset, Anda perlu menyimpan dokumen tersebut. Kode berikut menunjukkan cara menyimpan file PDF:

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### Contoh kode sumber untuk menyematkan font dengan strategi subset menggunakan Aspose.PDF untuk .NET. 

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
// Semua font akan disematkan sebagai subset ke dalam dokumen jika SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
// Subset font akan disematkan untuk font yang tertanam sepenuhnya tetapi font yang tidak tertanam ke dalam dokumen tidak akan terpengaruh.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
doc.Save(dataDir + "Output_out.pdf");
```

## Kesimpulan
Pada artikel ini, kita telah membahas cara menyematkan font dalam file PDF dengan strategi subset menggunakan Aspose.PDF untuk .NET. Aspose.PDF untuk .NET menyediakan API sederhana dan mudah digunakan untuk bekerja dengan dokumen PDF, termasuk menambahkan dan menyematkan font dengan strategi berbeda. Menyematkan font dalam file PDF merupakan langkah penting untuk memastikan bahwa dokumen ditampilkan dengan benar di perangkat yang berbeda, dan strategi subset adalah fitur yang berguna untuk mengurangi ukuran file dokumen PDF.

### FAQ untuk menyematkan font dalam file PDF dengan strategi subset

#### T: Apa yang dimaksud dengan strategi subset untuk menyematkan font dalam file PDF?

J: Strategi subset untuk penyematan font dalam file PDF berarti hanya sebagian font yang berisi karakter yang digunakan dalam dokumen yang akan disematkan. Ini membantu mengurangi ukuran file dokumen PDF dengan menghilangkan data font yang tidak perlu.

#### T: Apa perbedaan antara strategi SubsetAllFonts dan SubsetEmbeddedFontsOnly?

 J: Itu`SubsetAllFonts`strategi akan menyematkan semua font dalam dokumen sebagai subset, sedangkan`SubsetEmbeddedFontsOnly` strategi hanya akan menyematkan subset font yang sudah tertanam dalam dokumen. Strategi terakhir tidak akan mempengaruhi font yang belum tertanam.

#### T: Mengapa penyematan font dengan strategi subset penting?

J: Penyematan font dengan strategi subset penting untuk memastikan bahwa file PDF berisi data font yang diperlukan untuk menampilkan teks dengan benar, sekaligus menjaga ukuran file lebih kecil dengan hanya menyertakan karakter yang digunakan dalam dokumen.

#### T: Dapatkah saya menggunakan Aspose.PDF untuk .NET untuk menyematkan font dengan strategi berbeda?

 A: Ya, Aspose.PDF untuk .NET menyediakan berbagai strategi untuk penyematan font, termasuk`SubsetAllFonts` Dan`SubsetEmbeddedFontsOnly`. Anda dapat memilih strategi yang sesuai berdasarkan kebutuhan Anda.

#### T: Apakah Aspose.PDF untuk .NET merupakan perpustakaan yang andal untuk bekerja dengan dokumen PDF?

J: Ya, Aspose.PDF untuk .NET adalah perpustakaan yang andal dan kuat untuk bekerja dengan dokumen PDF. Ini menyediakan fitur ekstensif untuk membuat, mengedit, dan memanipulasi file PDF dalam aplikasi .NET.