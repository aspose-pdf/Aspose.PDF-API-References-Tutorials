---
title: PDF Ke SVG
linktitle: PDF Ke SVG
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk mengonversi PDF ke SVG menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 180
url: /id/net/document-conversion/pdf-to-svg/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses mengonversi format PDF ke SVG menggunakan Aspose.PDF untuk .NET. SVG (Scalable Vector Graphics) adalah format gambar vektor yang membantu menjaga kualitas dan skala grafik. Dengan mengikuti langkah-langkah di bawah ini, Anda akan dapat mengonversi file PDF ke format SVG.

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
Document doc = new Document(dataDir + "input.pdf");
```

 Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan direktori sebenarnya tempat file PDF Anda berada.

## Langkah 2: Instansiasi opsi penyimpanan SVG
Setelah memuat file PDF, kami akan membuat contoh opsi penyimpanan SVG. Gunakan kode berikut:

```csharp
// Buat instance objek SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Jangan mengompres gambar SVG dalam arsip Zip
saveOptions.CompressOutputToZipArchive = false;
```

## Langkah 3: Menyimpan file SVG yang dihasilkan
Sekarang kita akan menyimpan file PDF yang dikonversi dalam format SVG. Gunakan kode berikut:

```csharp
// Simpan keluaran ke file SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 Kode di atas menyimpan format PDF ke SVG yang telah dikonversi dengan nama file`"PDFToSVG_out.svg"`.

### Contoh kode sumber untuk PDF ke SVG menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Muat dokumen PDF
Document doc = new Document(dataDir + "input.pdf");
// Buat instance objek SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Jangan kompres gambar SVG ke arsip Zip
saveOptions.CompressOutputToZipArchive = false;
// Simpan hasilnya dalam file SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## Kesimpulan
Dalam tutorial ini, kami membahas proses langkah demi langkah mengonversi file PDF ke format SVG menggunakan Aspose.PDF untuk .NET. Dengan mengikuti petunjuk yang diuraikan di atas, Anda sekarang dapat mengonversi file PDF ke format SVG. Fitur ini berguna ketika Anda ingin menjaga kualitas dan skala grafis saat mengkonversi ke gambar vektor.

### FAQ

#### T: Dapatkah saya mengontrol resolusi atau ukuran file SVG yang dihasilkan selama konversi PDF ke SVG?

 J: Ya, Anda dapat mengontrol resolusi atau ukuran file SVG yang dihasilkan selama konversi PDF ke SVG menggunakan Aspose.PDF untuk .NET. Itu`SvgSaveOptions` kelas menyediakan properti seperti`PageSavingCallback` Dan`SaveFormat` yang memungkinkan Anda mengatur resolusi, ukuran halaman, atau parameter lain yang terkait dengan keluaran SVG. Anda dapat menyesuaikan opsi ini sesuai kebutuhan Anda untuk mengontrol kualitas dan ukuran file SVG.

#### T: Apakah Aspose.PDF untuk .NET mendukung konversi PDF terenkripsi atau dilindungi kata sandi ke SVG?

J: Ya, Aspose.PDF untuk .NET mendukung konversi PDF terenkripsi atau dilindungi kata sandi ke format SVG. Saat Anda memuat PDF yang dilindungi kata sandi, Anda dapat memberikan kata sandi menggunakan`Document` konstruktor kelas atau dengan mengatur`Password` properti sebelum memuat PDF. Aspose.PDF untuk .NET akan menangani dekripsi selama proses konversi PDF ke SVG.

#### T: Bisakah saya mengonversi hanya halaman tertentu dari PDF ke SVG, bukan seluruh dokumen?

J: Ya, Anda hanya dapat mengonversi halaman tertentu dari PDF ke SVG, bukan seluruh dokumen menggunakan Aspose.PDF untuk .NET. Sebelum menyimpan keluaran sebagai file SVG, Anda dapat memilih halaman yang ingin Anda konversi dengan menentukan nomor halaman atau rentangnya. Dengan cara ini, Anda hanya dapat mengekstrak dan mengonversi halaman yang diinginkan dari format PDF ke SVG.

#### T: Apakah Aspose.PDF untuk .NET kompatibel dengan semua versi SVG?

J: Aspose.PDF untuk .NET dirancang agar kompatibel dengan spesifikasi SVG 1.1 (Scalable Vector Graphics). Ini mendukung pembuatan file SVG sesuai dengan standar SVG 1.1. Namun perlu diketahui bahwa SVG 2.0 telah diperkenalkan sebagai versi terbaru dari spesifikasi SVG. Meskipun Aspose.PDF untuk .NET mungkin masih berfungsi dengan baik dengan SVG 2.0 dalam banyak kasus, disarankan untuk memeriksa kompatibilitas dan potensi batasan dengan fitur SVG spesifik yang ingin Anda gunakan.