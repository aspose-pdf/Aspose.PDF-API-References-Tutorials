---
title: Elemen Struktur Sebaris
linktitle: Elemen Struktur Sebaris
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk menggunakan elemen struktur online dengan Aspose.PDF untuk .NET. Atur PDF Anda dengan judul dan paragraf.
type: docs
weight: 110
url: /id/net/programming-with-tagged-pdf/inline-structure-elements/
---
Dalam panduan langkah demi langkah ini, kami akan menunjukkan cara menggunakan elemen struktur sebaris dengan Aspose.PDF untuk .NET. Aspose.PDF adalah perpustakaan canggih yang memungkinkan Anda memanipulasi dokumen PDF secara terprogram. Elemen struktur sebaris memungkinkan Anda membuat struktur hierarki dalam dokumen PDF Anda menggunakan judul dari berbagai tingkat dan paragraf.

Mari selami kodenya dan pelajari cara menggunakan elemen struktur sebaris dengan Aspose.PDF untuk .NET.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

1. Pustaka Aspose.PDF untuk .NET diinstal.
2. Pengetahuan dasar tentang bahasa pemrograman C#.

## Langkah 1: Menyiapkan lingkungan

Untuk memulai, buka lingkungan pengembangan C# Anda dan buat proyek baru. Pastikan Anda telah menambahkan referensi ke perpustakaan Aspose.PDF untuk .NET di proyek Anda.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat dokumen

 Langkah pertama adalah membuat dokumen PDF baru menggunakan`Document` kelas.

```csharp
// Buat dokumen PDF
Document document = new Document();
```

## Langkah 3: Bekerja dengan konten yang diberi tag

Kemudian kita mendapatkan konten dokumen yang diberi tag untuk dikerjakan.

```csharp
// Dapatkan konten dokumen yang diberi tag
ITaggedContent taggedContent = document.TaggedContent;
```

## Langkah 4: Tetapkan judul dan bahasa dokumen

Sekarang kita dapat mengatur judul dan bahasa dokumen.

```csharp
// Tentukan judul dan bahasa dokumen
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Langkah 5: Tambahkan elemen struktural secara online

Sekarang kita akan menambahkan elemen struktur sebaris seperti judul dari berbagai level dan paragraf ke dokumen kita.

```csharp
// Dapatkan elemen struktur root
StructureElement rootElement = taggedContent.RootElement;

// Tambahkan header dari level yang berbeda
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Tambahkan konten ke setiap header
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// Tambahkan satu paragraf
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Tambahkan konten ke paragraf
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

Di sini kita membuat elemen struktur sebaris, seperti judul pada tingkat yang berbeda dan paragraf, dan menambahkan konten ke dalamnya.

## Langkah 6: Simpan dokumen PDF yang diberi tag

Terakhir, kami menyimpan dokumen PDF yang diberi tag.

```csharp
// Simpan dokumen PDF yang diberi tag
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Contoh kode sumber untuk Elemen Struktur Inline menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat Dokumen Pdf
Document document = new Document();

// Dapatkan Konten untuk bekerja dengan TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Tetapkan Judul dan Bahasa untuk Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Dapatkan Elemen Struktur Akar
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// Simpan Dokumen Pdf yang Ditandai
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Kesimpulan

Selamat! Anda telah mempelajari cara menggunakan elemen struktur sebaris dengan Aspose.PDF untuk .NET. Anda sekarang dapat membuat struktur hierarki dalam dokumen PDF Anda dengan menggunakan judul pada tingkat dan paragraf yang berbeda. Jelajahi lebih banyak fitur Aspose.PDF untuk menemukan potensi penuhnya.

### FAQ

#### T: Apa yang dimaksud dengan elemen struktur sebaris dalam dokumen PDF, dan bagaimana kontribusinya dalam menciptakan struktur hierarki?

J: Elemen struktur sebaris dalam dokumen PDF, seperti judul pada tingkat dan paragraf yang berbeda, digunakan untuk membuat struktur hierarki yang mengatur dan menyajikan konten secara terstruktur. Elemen-elemen ini memungkinkan Anda membuat hierarki dan aliran informasi yang jelas dalam dokumen.

#### T: Bagaimana elemen struktur sebaris dapat meningkatkan keterbacaan dan pengorganisasian dokumen PDF?

J: Elemen struktur sebaris, khususnya judul dan paragraf, membantu meningkatkan keterbacaan dan pengorganisasian dokumen PDF dengan menyediakan struktur logis. Judul menunjukkan tingkat kepentingan yang berbeda dan membantu pembaca menavigasi konten, sementara paragraf mengelompokkan informasi terkait.

#### T: Bagaimana Aspose.PDF untuk .NET memfasilitasi penggunaan elemen struktur sebaris?

J: Aspose.PDF untuk .NET menawarkan kelas dan metode untuk membuat dan memanipulasi elemen struktur sebaris, seperti judul dan paragraf. Elemen-elemen ini dapat disesuaikan, diatur secara hierarki, dan diperkaya dengan konten untuk meningkatkan presentasi visual dan aksesibilitas dokumen.

####  T: Apa tujuan dari`taggedContent` object in relation to inline structure elements?

 J: Itu`taggedContent` objek, diperoleh dari`TaggedContent` milik a`Document`, memungkinkan Anda bekerja dengan elemen terstruktur, termasuk elemen struktur sebaris. Ini memungkinkan Anda membuat, menyesuaikan, dan mengatur judul dan paragraf dalam dokumen.

#### T: Bagaimana elemen struktur sebaris membantu menciptakan hierarki dokumen yang jelas?

J: Elemen struktur sebaris, seperti judul dari berbagai tingkat, berkontribusi dalam membangun hierarki yang jelas dan terdefinisi dengan baik dalam dokumen. Pembaca dapat dengan cepat mengidentifikasi topik utama, subtopik, dan konten terkait, sehingga dokumen lebih mudah dinavigasi dan dipahami.

#### T: Dapatkah saya mengkustomisasi tampilan dan pemformatan elemen struktur sebaris menggunakan Aspose.PDF untuk .NET?

J: Ya, Anda dapat menyesuaikan tampilan dan format elemen struktur sebaris. Anda dapat mengatur properti seperti gaya font, ukuran, warna, perataan, indentasi, dan spasi untuk mencapai presentasi visual yang diinginkan untuk judul dan paragraf.

#### T: Bagaimana cara membuat dan menambahkan judul dengan tingkat berbeda ke dokumen PDF menggunakan elemen struktur sebaris di Aspose.PDF untuk .NET?

 J: Anda dapat membuat judul dengan level berbeda menggunakan`CreateHeaderElement` metode dan kemudian menambahkannya ke elemen struktur akar. Selanjutnya, Anda dapat menambahkan konten ke setiap elemen judul menggunakan`CreateSpanElement` metode untuk membuat bentang teks.

#### T: Dapatkah saya menggunakan elemen struktur sebaris untuk membuat daftar, poin-poin, atau jenis organisasi konten lainnya dalam dokumen PDF?

J: Meskipun elemen struktur sebaris sendiri terutama digunakan untuk judul dan paragraf, Anda dapat menggunakannya dalam kombinasi dengan fitur lain yang ditawarkan oleh Aspose.PDF untuk .NET untuk membuat daftar, poin-poin, tabel, dan jenis organisasi konten lainnya secara komprehensif struktur dokumen.

#### T: Bagaimana elemen struktur inline berkontribusi terhadap aksesibilitas dokumen?

J: Elemen struktur sebaris memainkan peran penting dalam meningkatkan aksesibilitas dokumen. Judul dan paragraf yang terstruktur dengan baik memberikan hierarki dokumen yang jelas yang membantu pembaca layar dan teknologi bantu lainnya dalam menafsirkan dan menyampaikan konten secara akurat kepada pengguna penyandang disabilitas.

#### T: Bisakah saya mengeksplorasi penggunaan elemen struktur inline lebih lanjut, seperti membuat elemen interaktif atau menyematkan multimedia?

J: Tentu saja! Meskipun tutorial ini berfokus pada pembuatan judul dan paragraf, Aspose.PDF untuk .NET menawarkan fitur-fitur canggih untuk membuat elemen interaktif, menyematkan multimedia, menambahkan hyperlink, dan banyak lagi. Periksa dokumentasi dan contoh perpustakaan untuk mempelajari kemampuan tingkat lanjut ini.