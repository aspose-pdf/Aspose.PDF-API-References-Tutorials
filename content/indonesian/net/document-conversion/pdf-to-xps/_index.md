---
title: PDF Ke XPS
linktitle: PDF Ke XPS
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk mengonversi PDF ke XPS menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 220
url: /id/net/document-conversion/pdf-to-xps/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses mengonversi file PDF ke format XPS (Spesifikasi Kertas XML) menggunakan Aspose.PDF untuk .NET. Format XPS adalah format file berbasis XML yang digunakan untuk mewakili dokumen secara elektronik. Dengan mengikuti langkah-langkah di bawah ini, Anda akan dapat mengonversi file PDF ke format XPS.

## Prasyarat
Sebelum memulai, pastikan Anda memenuhi prasyarat berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET diinstal di sistem Anda.
- Lingkungan pengembangan seperti Visual Studio.

## Langkah 1: Memuat dokumen PDF
Pada langkah ini kita akan memuat file PDF sumber menggunakan Aspose.PDF untuk .NET. Ikuti kode di bawah ini:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan direktori sebenarnya tempat file PDF Anda berada.

## Langkah 2: Buat instance opsi penyimpanan XPS
Setelah memuat file PDF, kami akan membuat contoh opsi penyimpanan XPS. Gunakan kode berikut:

```csharp
// Buat instance opsi penyimpanan XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Langkah 3: Menyimpan file XPS yang dihasilkan
Sekarang kita akan menyimpan file PDF yang dikonversi dalam format XPS. Gunakan kode berikut:

```csharp
// Simpan dokumen XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 Kode di atas menyimpan file PDF yang dikonversi dalam format XPS dengan nama file`"PDFToXPS_out.xps"`.


### Contoh kode sumber untuk PDF ke XPS menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Muat dokumen PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// Buat instance opsi Simpan XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// Simpan dokumen XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## Kesimpulan
Dalam tutorial ini, kami membahas proses langkah demi langkah mengonversi file PDF ke format XPS menggunakan Aspose.PDF untuk .NET. Dengan mengikuti petunjuk yang diuraikan di atas, Anda sekarang dapat mengonversi file PDF ke format XPS. Fitur ini berguna ketika Anda ingin melihat atau mencetak dokumen PDF dalam format XPS.

### FAQ

#### T: Apakah format XPS cocok untuk kompatibilitas lintas platform?

J: Format XPS, sebagai format file berbasis XML, tidak bergantung pada platform dan dapat dilihat di berbagai sistem operasi dan perangkat. File XPS didukung pada platform Windows secara default, dan beberapa aplikasi serta penampil pihak ketiga mungkin tersedia untuk platform lain.

#### T: Dapatkah Aspose.PDF untuk .NET menangani file PDF kompleks dengan banyak halaman dan gambar selama konversi XPS?

J: Ya, Aspose.PDF untuk .NET dapat menangani file PDF kompleks dengan banyak halaman dan gambar selama konversi XPS. Ini secara akurat mempertahankan tata letak, gambar, dan konten tekstual PDF saat mengonversinya ke format XPS.

#### T: Apakah mungkin untuk menentukan pengaturan atau opsi tambahan selama proses konversi XPS?

 J: Ya, Aspose.PDF untuk .NET menyediakan berbagai opsi dan pengaturan yang dapat disesuaikan selama proses konversi XPS. Anda dapat mengontrol kompresi gambar, penyematan font, dan pengaturan lainnya menggunakan`XpsSaveOptions` kelas.

#### T: Apakah PDF yang dilindungi kata sandi dapat dikonversi ke format XPS menggunakan Aspose.PDF untuk .NET?

 J: Ya, Aspose.PDF untuk .NET mendukung konversi PDF yang dilindungi kata sandi ke format XPS. Saat memuat PDF yang dilindungi kata sandi, Anda dapat memberikan kata sandi menggunakan`Document` konstruktor kelas atau dengan mengatur`Password` properti sebelum memuat PDF.