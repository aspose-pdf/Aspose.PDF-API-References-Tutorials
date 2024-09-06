---
title: Tambahkan Elemen Struktur Ke Dalam Elemen
linktitle: Tambahkan Elemen Struktur Ke Dalam Elemen
second_title: Referensi API Aspose.PDF untuk .NET
description: Panduan langkah demi langkah untuk menambahkan elemen struktur ke elemen dalam dokumen PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 20
url: /id/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
Dalam tutorial ini, kami akan memberikan panduan langkah demi langkah tentang cara menambahkan elemen struktur ke elemen dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Aspose.PDF adalah pustaka canggih yang memungkinkan Anda membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram. Dengan menggunakan fitur struktur konten bertanda dari Aspose.PDF, Anda dapat membuat struktur hierarkis dalam dokumen PDF Anda.

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

## Langkah 3: Membuat dokumen PDF dan mendefinisikan elemen terstruktur

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

Kode ini membuat dokumen PDF kosong dan menambahkan elemen terstruktur seperti paragraf dan rentang. Setiap elemen struktur dibuat menggunakan metode yang disediakan oleh Aspose.PDF.

## Langkah 4: Menyimpan Dokumen PDF

Gunakan kode berikut untuk menyimpan dokumen PDF:

```csharp
document. Save(outFile);
```

Kode ini menyimpan dokumen PDF dengan elemen terstruktur ke berkas tertentu.

### Contoh kode sumber untuk Menambahkan Elemen Struktur ke dalam Elemen menggunakan Aspose.PDF untuk .NET 
```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// Dokumen pembuatan dan mendapatkan Konten Pdf yang Ditandai
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Pengaturan Judul dan Bahasa Alam untuk dokumen
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

Dalam tutorial ini, Anda mempelajari cara menambahkan elemen struktur ke elemen dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan menggunakan fitur struktur konten bertanda dari Aspose.PDF, Anda dapat membuat struktur hierarkis dalam dokumen PDF Anda, yang memudahkan pengelolaan dan navigasi konten.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan menambahkan elemen struktur ke elemen dalam dokumen PDF menggunakan Aspose.PDF untuk .NET?

A: Menambahkan elemen struktur ke elemen dalam dokumen PDF menggunakan Aspose.PDF for .NET memungkinkan Anda membuat struktur hierarkis dalam konten dokumen. Struktur hierarkis ini meningkatkan pengaturan dan navigasi konten, sehingga memudahkan pengelolaan dan akses elemen tertentu.

#### T: Bagaimana pustaka Aspose.PDF membantu menambahkan elemen struktur ke dokumen PDF?

J: Aspose.PDF untuk .NET adalah pustaka canggih yang menyediakan kemampuan untuk membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram. Dalam tutorial ini, fitur struktur konten bertanda pustaka dimanfaatkan untuk membuat dan menambahkan elemen struktur ke konten dokumen PDF.

#### T: Apa saja prasyarat untuk menambahkan elemen struktur ke dokumen PDF menggunakan Aspose.PDF for .NET?

A: Sebelum memulai, pastikan Anda telah menginstal Visual Studio dengan kerangka kerja .NET dan memiliki pustaka Aspose.PDF untuk .NET yang dirujuk dalam proyek Anda.

#### T: Bagaimana kode C# yang disediakan membuat dan menambahkan elemen struktur ke konten dokumen PDF?

A: Kode ini menunjukkan cara membuat dokumen PDF, menentukan elemen struktur akar, dan menambahkan berbagai elemen terstruktur seperti paragraf dan rentang ke dalamnya. Setiap elemen terstruktur dibuat menggunakan metode yang disediakan oleh Aspose.PDF, yang memungkinkan Anda membangun struktur hierarkis.

#### T: Dapatkah saya menyesuaikan jenis elemen struktur yang saya tambahkan ke dokumen PDF?

A: Ya, Anda dapat menyesuaikan jenis elemen struktur dengan menjelajahi berbagai metode yang disediakan oleh pustaka Aspose.PDF. Kode tersebut menampilkan paragraf dan rentang sebagai contoh, tetapi Anda dapat membuat dan menambahkan jenis elemen terstruktur lainnya sesuai kebutuhan.

#### T: Bagaimana cara menentukan hubungan hierarkis antara elemen struktur yang ditambahkan?

 A: Hubungan hierarkis antara elemen struktur ditentukan oleh urutan penambahan elemen tersebut ke elemen induknya. Dalam kode, hubungan induk-anak ditetapkan dengan menggunakan`AppendChild` metode.

#### T: Apa manfaat membuat struktur hierarki dalam dokumen PDF?

J: Membuat struktur hierarki dalam dokumen PDF meningkatkan aksesibilitas, navigasi, dan pengorganisasiannya. Struktur ini memungkinkan teknologi bantuan untuk menginterpretasikan dan menyampaikan konten dokumen dengan lebih baik, sehingga lebih mudah digunakan bagi penyandang disabilitas.

#### T: Bagaimana saya dapat memvalidasi kepatuhan PDF/UA setelah menambahkan elemen struktur?

 A: Kode yang diberikan dalam tutorial menunjukkan cara memvalidasi kepatuhan PDF/UA menggunakan`Validate` metode. Dengan memvalidasi dokumen terhadap standar PDF/UA, Anda dapat memastikan bahwa elemen struktur yang ditambahkan sesuai dengan pedoman aksesibilitas.

#### T: Dapatkah saya menggunakan pendekatan ini untuk menambahkan elemen struktur ke dokumen PDF yang ada?

A: Ya, Anda dapat mengubah pendekatan yang diberikan untuk menambahkan elemen struktur ke dokumen PDF yang sudah ada. Daripada membuat dokumen baru, Anda akan memuat dokumen yang sudah ada menggunakan Aspose.PDF lalu ikuti langkah-langkah serupa untuk menambahkan elemen struktur.