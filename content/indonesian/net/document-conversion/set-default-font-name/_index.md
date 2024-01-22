---
title: Tetapkan Nama Font Default
linktitle: Tetapkan Nama Font Default
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk mengatur nama font default dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 270
url: /id/net/document-conversion/set-default-font-name/
---
Dalam tutorial ini, kami akan menunjukkan cara mengatur nama font default dalam file PDF menggunakan Aspose.PDF untuk .NET. Terkadang saat Anda mengekstrak gambar dari file PDF, Anda mungkin mengalami masalah font yang hilang. Dengan menentukan nama font default, Anda dapat memastikan bahwa teks yang diekstrak akan ditampilkan dengan benar. Ikuti langkah-langkah di bawah ini untuk mengatur nama font default dalam file PDF.

## Prasyarat
Sebelum memulai, pastikan Anda memenuhi prasyarat berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET diinstal di sistem Anda.
- Lingkungan pengembangan seperti Visual Studio.

## Langkah 1: Memuat dokumen PDF
 Langkah pertama adalah memuat dokumen PDF ke a`Document` obyek. Gunakan kode berikut:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // Kode untuk ditambahkan
}
```

 Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan direktori sebenarnya tempat file PDF Anda berada.

## Langkah 2: Tetapkan nama font default
 Selanjutnya, kita akan menetapkan nama font default menggunakan`DefaultFontName` pilihan dari`RenderingOptions` obyek. Gunakan kode berikut:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // Kode untuk ditambahkan
     }
}
```

 Pastikan untuk mengganti`"Arial"` dengan nama font yang diinginkan.

## Langkah 3: Ekstraksi Gambar
Selanjutnya, kita akan mengekstrak gambar dari halaman tertentu pada dokumen PDF. Gunakan kode berikut:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 Pastikan untuk menentukan nomor halaman yang benar`pdfDocument.Pages[1]`.

### Contoh kode sumber untuk Tetapkan Nama Font Default menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengatur nama font default dalam file PDF menggunakan Aspose.PDF untuk .NET. Dengan menentukan nama font default, Anda dapat memastikan bahwa teks yang diekstrak akan ditampilkan dengan benar. Gunakan metode ini untuk mengatasi masalah font yang hilang saat mengekstraksi gambar dari file PDF.

### FAQ

#### T: Apa itu Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan dokumen PDF dalam aplikasi C#. Ia menawarkan berbagai fungsi, termasuk mengatur nama font default dalam file PDF.

#### T: Mengapa saya perlu menyetel nama font default di file PDF?

J: Menyetel nama font default berguna saat mengekstraksi teks dari dokumen PDF. Jika PDF berisi teks dengan font yang tidak tersedia di mesin ekstraksi, menentukan nama font default memastikan tampilan teks yang benar.

#### T: Bagaimana cara memuat dokumen PDF dan mengatur nama font default menggunakan Aspose.PDF untuk .NET?

 J: Untuk memuat dokumen PDF dan mengatur nama font default, Anda dapat menggunakan`Document`kelas untuk memuat file PDF dan`RenderingOptions.DefaultFontName` properti untuk menentukan nama font default yang diinginkan.

#### T: Bisakah saya memilih font apa pun sebagai nama font default?

A:Ya, Anda dapat memilih font apa pun yang tersedia di mesin ekstraksi sebagai nama font default. Gunakan font yang sangat cocok dengan font yang hilang di PDF asli untuk memastikan rendering teks akurat.

#### T: Apakah menyetel nama font default merupakan perubahan permanen pada file PDF?

J: Tidak, menyetel nama font default menggunakan Aspose.PDF untuk .NET adalah perubahan sementara yang dilakukan selama ekstraksi teks. Itu tidak mengubah file PDF asli.