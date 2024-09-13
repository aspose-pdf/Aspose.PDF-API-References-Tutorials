---
title: Buat PDF dengan Gambar yang Ditandai
linktitle: Buat PDF dengan Gambar yang Ditandai
second_title: Referensi API Aspose.PDF untuk .NET
description: Panduan langkah demi langkah untuk membuat PDF dengan gambar yang diberi tag menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 40
url: /id/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
Dalam tutorial ini, kami akan memberikan panduan langkah demi langkah tentang cara membuat dokumen PDF dengan gambar yang diberi tag menggunakan Aspose.PDF untuk .NET. Aspose.PDF adalah pustaka canggih yang memungkinkan Anda membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram. Dengan menggunakan fitur struktur konten yang diberi tag dari Aspose.PDF, Anda dapat menambahkan gambar yang diberi tag ke dokumen PDF Anda.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio terinstal dengan kerangka kerja .NET.
2. Pustaka Aspose.PDF untuk .NET.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek baru di Visual Studio dan tambahkan referensi ke pustaka Aspose.PDF untuk .NET. Anda dapat mengunduh pustaka tersebut dari situs web resmi Aspose dan menginstalnya di komputer Anda.

## Langkah 2: Impor namespace yang diperlukan

Dalam berkas kode C# Anda, impor namespace yang diperlukan untuk mengakses kelas dan metode yang disediakan oleh Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Langkah 3: Membuat dokumen PDF dengan gambar yang diberi tag

Gunakan kode berikut untuk membuat dokumen PDF dengan gambar yang diberi tag:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

Kode ini membuat dokumen PDF kosong dan menambahkan gambar yang diberi tag menggunakan metode yang disediakan oleh Aspose.PDF. Gambar ditentukan dengan teks alt, judul, dan tag.

## Langkah 4: Menyimpan Dokumen PDF

Gunakan kode berikut untuk menyimpan dokumen PDF:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Kode ini menyimpan dokumen PDF dengan gambar yang diberi tag ke berkas yang ditentukan.

### Contoh kode sumber untuk Membuat PDF dengan Gambar Berlabel menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// Tambahkan gambar dengan resolusi 300 DPI (secara default)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// Simpan Dokumen PDF
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Kesimpulan

Dalam tutorial ini, Anda mempelajari cara membuat dokumen PDF dengan gambar yang diberi tag menggunakan Aspose.PDF for .NET. Gambar yang diberi tag menambahkan informasi terstruktur tambahan ke dokumen PDF Anda.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan membuat dokumen PDF dengan gambar yang diberi tag menggunakan Aspose.PDF for .NET?

A: Membuat dokumen PDF dengan gambar yang diberi tag menggunakan Aspose.PDF for .NET memungkinkan Anda menambahkan gambar yang diberi tag ke konten dokumen. Gambar yang diberi tag menyediakan informasi terstruktur, seperti teks alt dan judul, yang meningkatkan aksesibilitas dan pengaturan.

#### T: Bagaimana pustaka Aspose.PDF membantu dalam pembuatan dokumen PDF dengan gambar yang diberi tag?

J: Aspose.PDF untuk .NET adalah pustaka tangguh yang menyediakan fungsionalitas untuk membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram. Dalam tutorial ini, fitur struktur konten bertag pustaka digunakan untuk menambahkan gambar bertag ke dokumen PDF.

#### T: Apa saja prasyarat untuk membuat dokumen PDF dengan gambar yang ditandai menggunakan Aspose.PDF for .NET?

A: Sebelum memulai, pastikan Anda telah menginstal Visual Studio dengan kerangka kerja .NET dan memiliki pustaka Aspose.PDF untuk .NET yang dirujuk dalam proyek Anda.

#### T: Bagaimana kode C# yang disediakan membuat dokumen PDF dengan gambar yang diberi tag?

A: Kode ini menunjukkan cara membuat dokumen PDF, menentukan elemen gambar yang diberi tag, dan menambahkannya ke konten dokumen. Gambar yang diberi tag menyertakan teks alt, judul, dan tag menggunakan metode yang disediakan oleh Aspose.PDF.

#### T: Dapatkah saya menggunakan format gambar yang berbeda untuk gambar yang diberi tag?

A: Ya, Anda dapat menggunakan format gambar yang berbeda untuk gambar yang diberi tag, seperti JPEG, PNG, GIF, dll. Contoh kode yang diberikan dalam tutorial ini menggunakan gambar JPEG, tetapi Anda dapat menggantinya dengan jalur ke file gambar dalam format pilihan Anda.

#### T: Bagaimana teks alternatif (teks alt) digunakan pada gambar yang diberi tag?

 A: Teks alt menyediakan deskripsi tekstual dari gambar, yang dibacakan dengan keras oleh pembaca layar untuk pengguna yang memiliki gangguan penglihatan. Dalam kode yang diberikan, teks alt diatur menggunakan`AlternativeText` milik`IllustrationElement` mewakili gambar yang diberi tag.

#### T: Bagaimana caranya`SetTitle` method contribute to the PDF document's tagged image?

 Sebuah:`SetTitle` metode menetapkan judul konten yang diberi tag pada dokumen PDF, yang menyediakan konteks tambahan untuk gambar yang diberi tag. Judul ini dapat membantu mengidentifikasi tujuan atau subjek konten yang diberi tag.

#### T: Dapatkah saya menyesuaikan tag dan judul gambar yang diberi tag?

 A: Ya, Anda dapat menyesuaikan tag dan judul gambar yang diberi tag menggunakan`SetTag` Dan`Title` metode dari`IllustrationElement`Contoh kode ini menunjukkan cara menyetel tag ke "Fig" dan judul ke "Picture 1."

#### T: Bagaimana saya dapat memastikan bahwa gambar yang diberi tag dapat diakses dan mematuhi standar aksesibilitas?

J: Dengan menggunakan fitur struktur konten bertag dari Aspose.PDF dan menyediakan teks alt dan informasi relevan lainnya, Anda berkontribusi pada aksesibilitas gambar bertag. Memastikan kepatuhan terhadap standar aksesibilitas melibatkan praktik terbaik berikut untuk teks alt dan struktur dokumen.

#### T: Apakah mungkin untuk menambahkan beberapa gambar yang diberi tag ke dokumen PDF yang sama menggunakan teknik yang sama?

A: Ya, Anda dapat menambahkan beberapa gambar yang diberi tag ke dokumen PDF yang sama menggunakan teknik yang sama. Anda akan membuat gambar tambahan`IllustrationElement` contoh untuk setiap gambar yang diberi tag dan menyesuaikan propertinya sesuai kebutuhan.