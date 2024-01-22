---
title: Tambahkan Elemen Struktur Ke Elemen
linktitle: Tambahkan Elemen Struktur Ke Elemen
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk menambahkan elemen struktur ke elemen dalam dokumen PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 20
url: /id/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
Dalam tutorial ini, kami akan memberi Anda panduan langkah demi langkah tentang cara menambahkan elemen struktur ke elemen dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Aspose.PDF adalah perpustakaan canggih yang memungkinkan Anda membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram. Dengan menggunakan fitur struktur konten yang ditandai dari Aspose.PDF, Anda dapat membuat struktur hierarki dalam dokumen PDF Anda.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio diinstal dengan kerangka .NET.
2. Pustaka Aspose.PDF untuk .NET.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek baru di Visual Studio dan tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET. Anda dapat mengunduh perpustakaan dari situs resmi Aspose dan menginstalnya di mesin Anda.

## Langkah 2: Impor namespace yang diperlukan

Dalam file kode C# Anda, impor namespace yang diperlukan untuk mengakses kelas dan metode yang disediakan oleh Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Langkah 3: Membuat dokumen PDF dan menentukan elemen terstruktur

Gunakan kode berikut untuk membuat dokumen PDF dan menentukan elemen terstruktur:

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

Kode ini membuat dokumen PDF kosong dan menambahkan elemen terstruktur seperti paragraf dan bentang. Setiap elemen struktur dibuat menggunakan metode yang disediakan oleh Aspose.PDF.

## Langkah 4: Menyimpan Dokumen PDF

Gunakan kode berikut untuk menyimpan dokumen PDF:

```csharp
document. Save(outFile);
```

Kode ini menyimpan dokumen PDF dengan elemen terstruktur ke file tertentu.

### Contoh kode sumber untuk Menambahkan Elemen Struktur Ke Elemen menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// Dokumen pembuatan dan mendapatkan Konten Pdf yang Ditandai
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Mengatur Judul dan Bahasa Alam untuk dokumen
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Mendapatkan elemen struktur Root (Elemen struktur dokumen)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// Simpan Dokumen Pdf yang Ditandai
document.Save(outFile);
// Memeriksa kepatuhan PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Kesimpulan

Dalam tutorial ini, Anda mempelajari cara menambahkan elemen struktur ke elemen dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan menggunakan fitur struktur konten yang ditandai dari Aspose.PDF, Anda dapat membuat struktur hierarki dalam dokumen PDF Anda, yang membuatnya lebih mudah untuk mengelola dan menavigasi konten.

### FAQ

#### T: Apa tujuan menambahkan elemen struktur ke elemen dalam dokumen PDF menggunakan Aspose.PDF untuk .NET?

J: Menambahkan elemen struktur ke elemen dalam dokumen PDF menggunakan Aspose.PDF untuk .NET memungkinkan Anda membuat struktur hierarki dalam konten dokumen. Struktur hierarki ini meningkatkan pengorganisasian dan navigasi konten, sehingga lebih mudah untuk mengelola dan mengakses elemen tertentu.

#### T: Bagaimana perpustakaan Aspose.PDF membantu menambahkan elemen struktur ke dokumen PDF?

J: Aspose.PDF untuk .NET adalah perpustakaan canggih yang menyediakan kemampuan untuk membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram. Dalam tutorial ini, fitur struktur konten yang ditandai pada perpustakaan dimanfaatkan untuk membuat dan menambahkan elemen struktur ke konten dokumen PDF.

#### T: Apa saja prasyarat untuk menambahkan elemen struktur ke dokumen PDF menggunakan Aspose.PDF untuk .NET?

J: Sebelum memulai, pastikan Anda telah menginstal Visual Studio dengan kerangka .NET dan memiliki pustaka Aspose.PDF untuk .NET yang direferensikan dalam proyek Anda.

#### T: Bagaimana cara kode C# yang disediakan membuat dan menambahkan elemen struktur ke konten dokumen PDF?

J: Kode ini menunjukkan cara membuat dokumen PDF, menentukan elemen struktur akar, dan menambahkan berbagai elemen terstruktur seperti paragraf dan span ke dalamnya. Setiap elemen terstruktur dibuat menggunakan metode yang disediakan oleh Aspose.PDF, memungkinkan Anda membangun struktur hierarki.

#### T: Dapatkah saya menyesuaikan jenis elemen struktur yang saya tambahkan ke dokumen PDF?

J: Ya, Anda dapat menyesuaikan tipe elemen struktur dengan menjelajahi berbagai metode yang disediakan oleh pustaka Aspose.PDF. Kode menampilkan paragraf dan span sebagai contoh, namun Anda dapat membuat dan menambahkan jenis elemen terstruktur lainnya sesuai kebutuhan.

#### T: Bagaimana cara mendefinisikan hubungan hierarki antara elemen struktur yang ditambahkan?

 J: Hubungan hierarki antara elemen struktur ditentukan oleh urutan penambahannya ke elemen induknya. Dalam kode tersebut, hubungan orang tua-anak dibuat dengan menggunakan`AppendChild` metode.

#### T: Apa manfaat membuat struktur hierarki dalam dokumen PDF?

J: Membuat struktur hierarki dalam dokumen PDF meningkatkan aksesibilitas, navigasi, dan pengorganisasiannya. Hal ini memungkinkan teknologi bantu untuk menafsirkan dan menyampaikan konten dokumen dengan lebih baik, sehingga lebih ramah pengguna bagi individu penyandang disabilitas.

#### T: Bagaimana cara memvalidasi kepatuhan PDF/UA setelah menambahkan elemen struktur?

 J: Kode yang diberikan dalam tutorial menunjukkan cara memvalidasi kepatuhan PDF/UA menggunakan`Validate` metode. Dengan memvalidasi dokumen berdasarkan standar PDF/UA, Anda dapat memastikan bahwa elemen struktur yang ditambahkan mematuhi pedoman aksesibilitas.

#### T: Dapatkah saya menggunakan pendekatan ini untuk menambahkan elemen struktur ke dokumen PDF yang sudah ada?

J: Ya, Anda dapat mengubah pendekatan yang disediakan untuk menambahkan elemen struktur ke dokumen PDF yang sudah ada. Daripada membuat dokumen baru, Anda akan memuat dokumen yang sudah ada menggunakan Aspose.PDF dan kemudian mengikuti langkah serupa untuk menambahkan elemen struktur.