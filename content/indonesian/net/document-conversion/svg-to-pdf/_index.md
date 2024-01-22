---
title: SVG Ke PDF
linktitle: SVG Ke PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Konversi SVG ke PDF dengan mudah dan cepat menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 280
url: /id/net/document-conversion/svg-to-pdf/
---
Tutorial ini akan memandu Anda melalui langkah-langkah untuk mengonversi file SVG ke file PDF menggunakan Aspose.PDF untuk .NET. Aspose.PDF menawarkan solusi sederhana dan efektif untuk mengonversi file SVG ke PDF dengan tetap menjaga kualitas dan tata letak konten. Ikuti langkah-langkah di bawah ini untuk melakukan konversi ini.

## Prasyarat
Sebelum memulai, pastikan Anda memenuhi prasyarat berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET diinstal di sistem Anda.
- Lingkungan pengembangan seperti Visual Studio.

## Langkah 1: Memuat file SVG
Langkah pertama adalah memuat file SVG ke a`Document` objek menggunakan opsi memuat SVG (`SvgLoadOptions`). Gunakan kode berikut:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat instance objek LoadOption menggunakan opsi pemuatan SVG
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Buat objek Dokumen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

 Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan direktori sebenarnya tempat file SVG Anda berada.

## Langkah 2: Konversikan ke PDF
 Langkah kedua adalah mengkonversi dokumen SVG ke dokumen PDF menggunakan`Save` metode`Document` obyek. Gunakan kode berikut:

```csharp
// Simpan dokumen PDF yang dihasilkan
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

Pastikan untuk menentukan jalur dan nama file yang diinginkan untuk file PDF yang dihasilkan.

### Contoh kode sumber SVG ke PDF menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat instance objek LoadOption menggunakan opsi pemuatan SVG
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Buat objek Dokumen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

// Simpan dokumen PDF yang dihasilkan
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengonversi file SVG ke file PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti langkah-langkah yang diberikan di atas, Anda dapat dengan mudah melakukan konversi ini. Gunakan metode ini untuk mengonversi file SVG Anda ke PDF dan nikmati fleksibilitas dan kualitas Aspose.PDF.

### FAQ

#### T: Apa itu Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan dokumen PDF dalam aplikasi C#. Ia menawarkan berbagai fungsi, termasuk mengonversi file SVG ke PDF.

#### T: Mengapa saya ingin mengonversi file SVG ke PDF?

J: File SVG (Scalable Vector Graphics) biasanya digunakan untuk grafik vektor di web. Mengonversi file SVG ke format PDF memungkinkan berbagi, mencetak, dan menyematkan konten grafis dengan lebih mudah.

#### T: Bagaimana cara memuat file SVG dan mengonversinya menjadi PDF menggunakan Aspose.PDF untuk .NET?

 A: Untuk memuat file SVG, Anda dapat menggunakan`SvgLoadOptions` kelas untuk menentukan opsi pemuatan SVG. Kemudian, buat a`Document` objek dan memuat file SVG ke dalamnya. Terakhir, gunakan`Save` metode`Document` objek untuk mengonversi dan menyimpan SVG sebagai PDF.

#### T: Dapatkah saya menyesuaikan keluaran PDF selama konversi?

J: Ya, Anda dapat menyesuaikan keluaran PDF selama proses konversi. Aspose.PDF untuk .NET menyediakan berbagai opsi dan properti untuk mengontrol tampilan dan tata letak dokumen PDF.

#### T: Apakah kualitas konten SVG dipertahankan dalam PDF yang dihasilkan?

J: Ya, Aspose.PDF untuk .NET memastikan pelestarian kualitas dan tata letak konten selama konversi SVG ke PDF, memastikan transisi yang mulus antar format.