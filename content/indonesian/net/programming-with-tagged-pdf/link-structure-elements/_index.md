---
title: Elemen Struktur Tautan
linktitle: Elemen Struktur Tautan
second_title: Referensi API Aspose.PDF untuk .NET
description: Panduan langkah demi langkah untuk menggunakan elemen struktur tautan dengan Aspose.PDF untuk .NET. Buat hyperlink dalam dokumen PDF Anda.
type: docs
weight: 120
url: /id/net/programming-with-tagged-pdf/link-structure-elements/
---
Dalam panduan langkah demi langkah ini, kami akan menunjukkan cara menggunakan elemen struktur tautan dengan Aspose.PDF untuk .NET. Aspose.PDF adalah pustaka canggih yang memungkinkan Anda membuat dan memanipulasi dokumen PDF secara terprogram. Elemen struktur tautan memungkinkan Anda menambahkan hyperlink ke dokumen PDF, sehingga pengguna dapat mengeklik tautan dan menavigasi ke sumber daya daring.

Mari selami kodenya dan pelajari cara menggunakan elemen struktur tautan dengan Aspose.PDF untuk .NET.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

1. Pustaka Aspose.PDF untuk .NET terpasang.
2. Pengetahuan dasar tentang bahasa pemrograman C#.

## Langkah 1: Menyiapkan lingkungan

Untuk memulai, buka lingkungan pengembangan C# Anda dan buat proyek baru. Pastikan Anda telah menambahkan referensi ke pustaka Aspose.PDF untuk .NET dalam proyek Anda.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## Langkah 2: Membuat dokumen

 Langkah pertama adalah membuat dokumen PDF baru menggunakan`Document` kelas.

```csharp
// Buat dokumen PDF
Document document = new Document();
```

## Langkah 3: Bekerja dengan konten yang diberi tag

Lalu, kita dapatkan konten dokumen yang diberi tag untuk dikerjakan.

```csharp
// Dapatkan konten yang ditandai dari dokumen
ITaggedContent taggedContent = document.TaggedContent;
```

## Langkah 4: Tetapkan judul dan bahasa dokumen

Sekarang kita dapat mengatur judul dokumen dan bahasa.

```csharp
// Tentukan judul dan bahasa dokumen
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Langkah 5: Tambahkan elemen struktur tautan

Sekarang mari tambahkan elemen struktur tautan ke dokumen kita. Kita akan membuat berbagai jenis tautan, termasuk tautan teks sederhana, tautan gambar, dan tautan multi-baris.
```csharp
// Dapatkan elemen struktur akar (elemen struktur dokumen)
StructureElement rootElement = taggedContent.RootElement;

// Tambahkan paragraf dengan hyperlink
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Tambahkan paragraf dengan hyperlink yang berisi teks kaya
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Tambahkan paragraf dengan hyperlink yang berisi teks yang diformat sebagian
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// Tambahkan paragraf dengan hyperlink multiline
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// Tambahkan paragraf dengan hyperlink yang berisi gambar
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## Langkah 6: Simpan dokumen PDF yang diberi tag

Terakhir, kami menyimpan dokumen PDF yang diberi tag.

```csharp
// Simpan dokumen PDF yang diberi tag
document. Save(outFile);
```

## Langkah 7: Periksa kepatuhan PDF/UA

 Kita juga dapat memeriksa dokumen untuk kepatuhan PDF/UA menggunakan`Validate` metode dari`Document` kelas.

```csharp
// Periksa kepatuhan PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Contoh kode sumber untuk Elemen Struktur Tautan menggunakan Aspose.PDF untuk .NET 
```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Dokumen pembuatan dan mendapatkan Konten Pdf yang Ditandai
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Pengaturan Judul dan Bahasa Alam untuk dokumen
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Mendapatkan elemen struktur Root (Elemen struktur dokumen)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// Simpan Dokumen Pdf yang Ditandai
document.Save(outFile);

// Memeriksa kepatuhan PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Kesimpulan

Selamat! Anda telah mempelajari cara menggunakan elemen struktur tautan dengan Aspose.PDF untuk .NET. Sekarang Anda dapat membuat hyperlink dalam dokumen PDF Anda, yang memungkinkan pengguna untuk menavigasi ke sumber daya daring. Bereksperimenlah dan jelajahi lebih banyak fitur Aspose.PDF untuk membuat dokumen PDF yang interaktif dan lengkap.

### Pertanyaan yang Sering Diajukan

#### T: Apa saja elemen struktur tautan dalam dokumen PDF, dan bagaimana elemen tersebut meningkatkan interaktivitas dokumen?

A: Elemen struktur tautan dalam dokumen PDF digunakan untuk membuat hyperlink yang memungkinkan pengguna menavigasi ke sumber daya daring atau lokasi tertentu dalam dokumen. Elemen ini meningkatkan interaktivitas dengan menyediakan tautan yang dapat diklik yang memungkinkan pengguna mengakses konten terkait atau situs web eksternal.

#### T: Bagaimana elemen struktur tautan dapat bermanfaat dalam dokumen PDF?

A: Elemen struktur tautan meningkatkan pengalaman pengguna dengan membuat dokumen PDF menjadi interaktif. Elemen ini menyediakan akses cepat ke informasi tambahan, konten terkait, situs web eksternal, atau bagian tertentu dalam dokumen, sehingga meningkatkan navigasi dan memudahkan pencarian informasi.

#### T: Dapatkah saya membuat berbagai jenis hyperlink menggunakan elemen struktur tautan di Aspose.PDF untuk .NET?

A: Ya, Anda dapat membuat berbagai jenis hyperlink menggunakan elemen struktur tautan. Aspose.PDF untuk .NET memungkinkan Anda membuat hyperlink dengan teks biasa, teks kaya, gambar, dan deskripsi multi-baris, yang menawarkan fleksibilitas dalam cara Anda menautkan ke konten eksternal atau lokasi dalam dokumen.

#### T: Bagaimana cara menyiapkan dan menginisialisasi elemen struktur tautan dalam dokumen PDF menggunakan Aspose.PDF untuk .NET?

 A: Untuk menggunakan elemen struktur tautan, pertama-tama Anda perlu membuat dokumen PDF baru menggunakan`Document` kelas. Kemudian, dapatkan konten yang diberi tag menggunakan`TaggedContent`properti dokumen. Dari sana, Anda dapat membuat dan menyesuaikan elemen struktur tautan dan menambahkannya ke elemen struktur akar.

#### T: Bagaimana cara membuat hyperlink teks sederhana menggunakan elemen struktur tautan?
 A: Anda dapat membuat hyperlink teks sederhana dengan membuat`LinkElement` dan pengaturannya`Hyperlink` properti ke suatu`WebHyperlink` dengan URL yang ingin Anda tautkan. Anda juga dapat mengatur teks tampilan tautan menggunakan`SetText` metode.

#### T: Apakah mungkin membuat hyperlink dengan gambar menggunakan elemen struktur tautan?

 A: Ya, Anda dapat membuat hyperlink dengan gambar menggunakan elemen struktur tautan. Anda akan membuat`LinkElement` dan kemudian tambahkan`FigureElement` dengan gambar di dalamnya. Ini memungkinkan Anda membuat hyperlink berbasis gambar.

#### T: Bagaimana saya dapat memastikan bahwa dokumen PDF saya dengan hyperlink mematuhi standar PDF/UA untuk aksesibilitas?

 A: Aspose.PDF untuk .NET menyediakan kemampuan untuk memvalidasi kepatuhan dokumen PDF Anda dengan standar PDF/UA menggunakan`Validate` metode dari`Document`kelas. Hal ini memastikan bahwa hyperlink dokumen dapat diakses oleh pengguna penyandang disabilitas.

#### T: Apa saja deskripsi alternatif untuk elemen struktur tautan, dan mengapa itu penting?

A: Deskripsi alternatif (teks alt) untuk elemen struktur tautan menyediakan deskripsi tekstual dari hyperlink. Deskripsi ini penting untuk aksesibilitas, yang memungkinkan pengguna dengan gangguan penglihatan untuk memahami tujuan tautan dan tujuannya.

#### T: Dapatkah saya menyesuaikan tampilan dan perilaku hyperlink yang dibuat menggunakan elemen struktur tautan?

J: Meskipun elemen struktur tautan terutama berfokus pada pembuatan hyperlink, Anda dapat menyesuaikan tampilan dan perilaku hyperlink lebih lanjut menggunakan fitur lain yang ditawarkan oleh Aspose.PDF untuk .NET. Ini termasuk menentukan warna, gaya, dan tindakan tautan.

#### T: Bagaimana elemen struktur tautan berkontribusi dalam membuat dokumen PDF lebih interaktif dan ramah pengguna?

A: Elemen struktur tautan mengubah dokumen PDF statis menjadi pengalaman interaktif dengan menambahkan hyperlink yang dapat diklik. Interaktivitas ini meningkatkan keterlibatan pengguna, memungkinkan navigasi yang lancar antara konten terkait, dan meningkatkan kegunaan dokumen secara keseluruhan.