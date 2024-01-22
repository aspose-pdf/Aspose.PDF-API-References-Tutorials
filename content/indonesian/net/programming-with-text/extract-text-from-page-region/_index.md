---
title: Ekstrak Teks Dari Wilayah Halaman Dalam File PDF
linktitle: Ekstrak Teks Dari Wilayah Halaman Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara mengekstrak teks dari wilayah tertentu pada halaman dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 190
url: /id/net/programming-with-text/extract-text-from-page-region/
---
Tutorial ini akan memandu Anda melalui proses mengekstraksi teks dari wilayah tertentu pada halaman dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang disediakan menunjukkan langkah-langkah yang diperlukan.

## Persyaratan
Sebelum memulai, pastikan Anda memiliki hal berikut:

- Visual Studio atau kompiler C# lainnya yang diinstal pada mesin Anda.
- Aspose.PDF untuk perpustakaan .NET. Anda dapat mendownloadnya dari situs resmi Aspose atau menggunakan manajer paket seperti NuGet untuk menginstalnya.

## Langkah 1: Siapkan proyek
1. Buat proyek C# baru di lingkungan pengembangan pilihan Anda.
2. Tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET.

## Langkah 2: Impor namespace yang diperlukan
Dalam file kode tempat Anda ingin mengekstrak teks, tambahkan arahan penggunaan berikut di bagian atas file:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Langkah 3: Atur direktori dokumen
 Dalam kode, temukan baris yang bertuliskan`string dataDir = "YOUR DOCUMENT DIRECTORY";` dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori tempat dokumen Anda disimpan.

## Langkah 4: Buka dokumen PDF
 Buka dokumen PDF yang ada menggunakan`Document`konstruktor dan meneruskan jalur ke file PDF masukan.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Langkah 5: Ekstrak teks dari wilayah halaman
 Membuat`TextAbsorber` objek untuk mengekstrak teks dari dokumen. Konfigurasikan`TextSearchOptions` untuk membatasi pencarian pada wilayah halaman tertentu yang ditentukan oleh persegi panjang.

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## Langkah 6: Dapatkan teks yang diekstraksi
 Akses teks yang diekstraksi dari`TextAbsorber` obyek.

```csharp
string extractedText = absorb.Text;
```

## Langkah 7: Simpan teks yang diekstraksi
 Membuat`TextWriter` dan buka file tempat Anda ingin menyimpan teks yang diekstraksi. Tulis teks yang diekstraksi ke file dan tutup alirannya.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Contoh kode sumber untuk Ekstrak Teks Dari Wilayah Halaman menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buka dokumen
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Buat objek TextAbsorber untuk mengekstrak teks
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
// Terima penyerap untuk halaman pertama
pdfDocument.Pages[1].Accept(absorber);
// Dapatkan teks yang diekstraksi
string extractedText = absorber.Text;
// Buat penulis dan buka file
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Tulis sebaris teks ke file
tw.WriteLine(extractedText);
// Tutup alirannya
tw.Close();
```

## Kesimpulan
Anda telah berhasil mengekstraksi teks dari wilayah tertentu pada halaman dokumen PDF menggunakan Aspose.PDF untuk .NET. Teks yang diekstraksi telah disimpan ke file keluaran yang ditentukan.

### FAQ

#### T: Apa tujuan dari tutorial ini?

J: Tutorial ini bertujuan untuk memandu Anda melalui proses mengekstraksi teks dari wilayah tertentu pada halaman dalam file PDF menggunakan Aspose.PDF untuk .NET. Kode sumber C# yang menyertainya memberikan petunjuk langkah demi langkah untuk menyelesaikan tugas ini.

#### T: Namespace apa yang harus saya impor?

A: Dalam file kode tempat Anda ingin mengekstrak teks, sertakan arahan penggunaan berikut di awal file:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### T: Bagaimana cara menentukan direktori dokumen?

 A: Temukan garisnya`string dataDir = "YOUR DOCUMENT DIRECTORY";` dalam kode dan ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

#### T: Bagaimana cara membuka dokumen PDF yang sudah ada?

 J: Pada Langkah 4, Anda akan membuka dokumen PDF yang ada menggunakan`Document` konstruktor dan menyediakan jalur ke file PDF masukan.

#### T: Bagaimana cara mengekstrak teks dari wilayah halaman tertentu?

 J: Langkah 5 melibatkan pembuatan a`TextAbsorber`objek untuk mengekstrak teks dari dokumen PDF. Anda kemudian akan mengonfigurasi`TextSearchOptions` untuk menentukan wilayah persegi panjang tertentu pada halaman menggunakan koordinat.

#### T: Bagaimana cara mengakses teks yang diekstraksi?

 J: Langkah 6 memandu Anda dalam mengakses teks yang diekstrak dari`TextAbsorber` obyek.

#### T: Bagaimana cara menyimpan teks yang diekstrak ke file?

 J: Pada Langkah 7, Anda akan membuat a`TextWriter`, buka file tempat Anda ingin menyimpan teks yang diekstraksi, tulis teks yang diekstraksi ke file, lalu tutup aliran.

#### T: Apa inti dari tutorial ini?

J: Dengan mengikuti tutorial ini, Anda telah mempelajari cara mengekstrak teks dari wilayah tertentu pada halaman dokumen PDF menggunakan Aspose.PDF untuk .NET. Teks yang diekstraksi telah disimpan ke file keluaran tertentu, memungkinkan Anda menargetkan dan menganalisis konten tekstual yang diinginkan secara tepat.