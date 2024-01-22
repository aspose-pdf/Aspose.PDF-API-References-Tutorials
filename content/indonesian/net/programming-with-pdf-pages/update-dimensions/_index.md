---
title: Perbarui Dimensi Halaman PDF
linktitle: Perbarui Dimensi Halaman PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk memperbarui dimensi halaman PDF menggunakan Aspose.PDF untuk .NET. Periksa dimensi sesuai kebutuhan Anda.
type: docs
weight: 150
url: /id/net/programming-with-pdf-pages/update-dimensions/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk memperbarui dimensi halaman dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Kami akan menjelaskan paket kode sumber C# dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan mengetahui cara mengubah dimensi halaman dalam dokumen PDF menggunakan Aspose.PDF untuk .NET.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#
- Aspose.PDF untuk .NET diinstal di lingkungan pengembangan Anda

## Langkah 1: Tentukan direktori dokumen
Pertama, Anda perlu menyetel jalur ke direktori dokumen Anda. Ini adalah lokasi di mana Anda ingin menyimpan dokumen PDF yang telah Anda edit. Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Buka dokumen PDF
 Kemudian Anda dapat membuka dokumen PDF yang ada menggunakan`Document` kelas Aspose.PDF. Pastikan untuk menentukan jalur dokumen yang benar.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Langkah 3: Dapatkan Koleksi Halaman
 Sekarang Anda dapat mengakses kumpulan halaman dokumen PDF menggunakan`Pages` properti dari`Document` kelas.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Langkah 4: Dapatkan halaman tertentu
Kemudian Anda dapat memilih halaman tertentu dari dokumen menggunakan indeks halaman dalam koleksi. Dalam contoh ini, kami menggunakan halaman kedua (indeks 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Langkah 5: Tentukan dimensi halaman baru
 Sekarang Anda dapat mengatur ukuran halaman baru menggunakan`SetPageSize()` metode`Page`obyek. Dalam contoh ini, kami mengatur dimensi halaman ke A4 (11,7 x 8,3 inci), dikonversi ke poin (1 inci = 72 poin).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## Langkah 6: Simpan dokumen yang diperbarui
 Terakhir, Anda dapat menyimpan dokumen PDF yang diperbarui ke file menggunakan`Save()` metode`Document`kelas. Pastikan untuk menentukan jalur dan nama file yang benar.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Contoh kode sumber untuk Pembaruan Dimensi menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Dapatkan koleksi halaman
PageCollection pageCollection = pdfDocument.Pages;
// Dapatkan halaman tertentu
Page pdfPage = pageCollection[1];
// Tetapkan ukuran halaman sebagai A4 (11,7 x 8,3 inci) dan di Aspose.Pdf, 1 inci = 72 poin
// Jadi dimensi A4 dalam poin adalah (842.4, 597.6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Simpan dokumen yang diperbarui
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara memperbarui dimensi halaman dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah mengubah dimensi halaman dalam dokumen PDF sesuai kebutuhan. Aspose.PDF menawarkan API yang kuat dan fleksibel untuk bekerja dengan file PDF dan melakukan berbagai manipulasi, termasuk mengubah dimensi halaman. Dengan pengetahuan ini, Anda dapat mengontrol dan menyesuaikan dimensi halaman PDF untuk memenuhi kebutuhan spesifik Anda.

### FAQ untuk memperbarui dimensi halaman PDF

#### T: Bagaimana cara memperbarui dimensi halaman tertentu dalam dokumen PDF menggunakan Aspose.PDF untuk .NET?

J: Untuk memperbarui dimensi halaman tertentu dalam dokumen PDF menggunakan Aspose.PDF untuk .NET, Anda dapat mengikuti langkah-langkah berikut:

1. Atur direktori dokumen dengan menentukan jalur di mana file PDF asli Anda berada dan di mana Anda ingin menyimpan file PDF yang diperbarui. Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai.
2.  Buka dokumen PDF yang ada untuk diperbarui menggunakan`Document` kelas Aspose.PDF. Pastikan untuk menentukan jalur yang benar ke dokumen PDF asli.
3.  Akses kumpulan halaman dokumen PDF menggunakan`Pages` properti dari`Document` kelas.
4. Pilih halaman tertentu yang ingin Anda perbarui dari kumpulan halaman menggunakan indeks halaman. Dalam kode sumber C# yang disediakan, kami menggunakan halaman kedua (indeks 1).
5.  Tentukan ukuran halaman baru menggunakan`SetPageSize()` metode`Page` obyek. Dalam contoh, kami mengatur dimensi halaman ke ukuran A4 (11,7 x 8,3 inci), dikonversi ke poin (1 inci = 72 poin).
6.  Simpan dokumen PDF yang diperbarui ke file menggunakan`Save()` metode`Document`kelas. Pastikan untuk menentukan jalur dan nama file yang benar.

#### T: Dapatkah saya memperbarui dimensi beberapa halaman dalam dokumen PDF secara bersamaan?

J: Ya, Anda dapat memodifikasi kode sumber yang disediakan untuk memperbarui dimensi beberapa halaman dalam dokumen PDF secara bersamaan. Daripada memilih halaman tertentu (seperti yang ditunjukkan pada langkah 4), Anda dapat menelusuri semua halaman dalam kumpulan halaman dan mengatur ukuran halaman yang diinginkan untuk setiap halaman.

#### T: Bagaimana cara mengonversi dimensi halaman dari inci ke titik saat menggunakan Aspose.PDF untuk .NET?

 A: Di Aspose.PDF untuk .NET, satuan pengukuran yang digunakan untuk dimensi halaman adalah titik, dimana 1 inci setara dengan 72 titik. Untuk mengubah inci menjadi titik, Anda dapat menggunakan rumus:`points = inches * 72`. Misalnya, untuk mengatur ukuran halaman 11,7 x 8,3 inci, Anda dapat menghitung dimensi terkait dalam poin sebagai (11,7*72) dan (8,3*72).

#### T: Apakah pembaruan dimensi halaman akan memengaruhi tata letak konten dokumen PDF?

J: Ya, memperbarui dimensi halaman akan mempengaruhi tata letak konten dokumen PDF pada halaman tertentu. Saat Anda mengubah dimensi halaman, konten pada halaman akan disesuaikan agar sesuai dengan dimensi baru.

#### T: Apakah mungkin untuk mengembalikan perubahan dan mengembalikan dimensi halaman asli setelah memperbaruinya?

J: Ya, jika Anda ingin mengembalikan perubahan dan mengembalikan dimensi halaman asli, Anda dapat menyimpan salinan dokumen PDF asli sebelum melakukan perubahan atau membuka kembali dokumen PDF asli tanpa menyimpan perubahan. Dengan cara ini, dimensi aslinya akan dipertahankan.