---
title: Dapatkan Dimensi SVG
linktitle: Dapatkan Dimensi SVG
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk mendapatkan dimensi SVG menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 40
url: /id/net/document-conversion/get-svg-dimensions/
---
## Perkenalan
Dalam tutorial ini, kami akan memandu Anda melalui proses mendapatkan dimensi file SVG menggunakan Aspose.PDF untuk .NET. SVG (Scalable Vector Graphics) adalah format gambar berbasis XML yang digunakan untuk merepresentasikan grafik vektor. Dengan menggunakan langkah-langkah di bawah ini, Anda bisa mendapatkan dimensi file SVG dan menyimpannya sebagai PDF.

## Prasyarat
Sebelum memulai, pastikan Anda memenuhi prasyarat berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET diinstal di sistem Anda.
- Lingkungan pengembangan seperti Visual Studio.

## Langkah 1: Memuat file SVG
Pada langkah ini, kita akan memuat file SVG menggunakan Aspose.PDF untuk .NET. Ikuti kode di bawah ini:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan direktori sebenarnya tempat file SVG Anda berada.

## Langkah 2: Penyesuaian ukuran halaman
Sekarang kita telah memuat file SVG, kita dapat menyesuaikan ukuran halaman untuk mengakomodasi konten SVG. Gunakan kode berikut:

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

Kode di atas menyetel margin halaman ke nol, sehingga ukuran halaman dapat disesuaikan berdasarkan konten SVG.

## Langkah 3: Menyimpan PDF yang dihasilkan
Setelah menyesuaikan ukuran halaman, kini kita dapat menyimpan dokumen PDF yang dihasilkan. Inilah langkah terakhir:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan direktori yang diinginkan tempat Anda ingin menyimpan file PDF keluaran.
  
### Contoh kode sumber untuk Dapatkan Dimensi SVG menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## Kesimpulan
Dalam tutorial ini, kami telah membahas proses langkah demi langkah untuk mendapatkan dimensi file SVG menggunakan Aspose.PDF untuk .NET. Dengan mengikuti petunjuk yang diuraikan di atas, Anda sekarang bisa mendapatkan dimensi file SVG dan menyimpannya ke Format PDF. Fitur ini dapat berguna ketika Anda perlu mengukur dimensi grafik vektor.

### FAQ

#### T: Apa itu SVG?

J: SVG (Scalable Vector Graphics) adalah format gambar berbasis XML yang digunakan untuk merepresentasikan grafik vektor. Tidak seperti gambar raster, file SVG tidak bergantung pada resolusi dan dapat diskalakan tanpa kehilangan kualitas. SVG banyak digunakan untuk menampilkan grafik di web dan dapat diedit dan dimanipulasi dengan mudah.

#### T: Mengapa menggunakan Aspose.PDF untuk .NET untuk konversi SVG ke PDF?

J: Aspose.PDF untuk .NET menyediakan cara yang andal dan efisien untuk menangani file SVG dan mengonversinya ke format PDF. Ini menawarkan berbagai opsi dan pengaturan untuk menyesuaikan proses konversi, seperti menyesuaikan ukuran halaman, margin, dan properti lainnya untuk memastikan representasi akurat dalam PDF.

#### T: Bisakah saya mengonversi file SVG dengan grafik dan teks yang rumit?

J: Ya, Aspose.PDF untuk .NET dapat menangani file SVG dengan elemen grafik, teks, dan vektor yang kompleks. Ini secara akurat menjaga detail dan kualitas konten SVG selama proses konversi, menghasilkan dokumen PDF berkualitas tinggi.

#### T: Apakah mungkin mengekstrak teks dari file SVG dengan Aspose.PDF untuk .NET?

J: Ya, Aspose.PDF untuk .NET memungkinkan Anda mengekstrak teks dari file SVG. Anda dapat menggunakan fitur ekstraksi teks perpustakaan untuk mengekstrak elemen teks dari SVG dan menyimpannya secara terpisah untuk diproses lebih lanjut.