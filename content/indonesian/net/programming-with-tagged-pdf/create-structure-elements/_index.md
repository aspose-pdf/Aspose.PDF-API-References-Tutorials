---
title: Buat Elemen Struktur
linktitle: Buat Elemen Struktur
second_title: Referensi API Aspose.PDF untuk .NET
description: Dalam tutorial ini, Anda akan mempelajari cara menggunakan Aspose.PDF untuk .NET untuk membuat elemen struktural dalam dokumen PDF yang diberi tag.
type: docs
weight: 60
url: /id/net/programming-with-tagged-pdf/create-structure-elements/
---
Kode sumber C# berikut menggunakan Aspose.PDF for .NET untuk membuat elemen struktur. Ikuti langkah-langkah di bawah ini untuk memahami cara kerja kode tersebut.

## Langkah 1: Impor pustaka yang diperlukan

```csharp
using Aspose.Pdf;
```

## Langkah 2: Tentukan direktori dokumen Anda

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Pastikan untuk menentukan jalur yang benar ke direktori dokumen Anda.

## Langkah 3: Buat dokumen PDF

```csharp
Document document = new Document();
```

Kami membuat objek Dokumen baru yang mewakili dokumen PDF.

## Langkah 4: Dapatkan konten untuk bekerja dengan TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Kami mengambil konten yang diberi tag dari dokumen PDF. Ini akan memungkinkan kami untuk memanipulasi elemen struktural.

## Langkah 5: Tetapkan judul dan bahasa dokumen

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Kami menetapkan judul dan bahasa dokumen PDF yang diberi tag. Ini meningkatkan aksesibilitas dokumen.

## Langkah 6: Buat elemen pengelompokan

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

Kami membuat berbagai elemen struktural untuk mengelompokkan konten dalam dokumen PDF.

## Langkah 7: Buat elemen struktur paragraf

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Kami membuat elemen struktural tingkat blok untuk paragraf dan judul. Contoh di atas menunjukkan pembuatan judul tingkat 1.

## Langkah 8: Buat elemen struktur tingkat sebaris

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Kami membuat elemen struktur tingkat sebaris untuk bagian teks yang muncul di dalam paragraf atau judul.

## Langkah 9: Buat elemen struktur karya seni

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Kami membuat elemen struktural untuk ilustrasi dan rumus matematika yang ada dalam dokumen.

## Langkah 10: Simpan dokumen PDF yang diberi tag

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Kami menyimpan dokumen PDF yang diberi tag dengan elemen struktur yang dibuat.

### Contoh kode sumber untuk Membuat Elemen Struktur menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Buat Dokumen Pdf
Document document = new Document();
// Dapatkan Konten untuk bekerja dengan TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
// Mengatur Judul dan Bahasa untuk Dokumen
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
// Membuat Elemen Pengelompokan
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
// Membuat Elemen Struktur Tingkat Blok Teks
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Membuat Elemen Struktur Teks Sebaris
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Membuat Elemen Struktur Ilustrasi
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// Metode sedang dalam pengembangan
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
// Simpan Dokumen Pdf yang Ditandai
document.Save(dataDir + "StructureElements.pdf");

```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menggunakan Aspose.PDF untuk .NET guna membuat elemen struktur dalam dokumen PDF yang diberi tag. Elemen struktural membantu meningkatkan aksesibilitas dokumen dan mengatur konten dengan cara yang bermakna. Kini Anda dapat menggunakan pengetahuan ini untuk membuat dokumen PDF yang terstruktur dan mudah dinavigasi.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan membuat elemen struktur dalam dokumen PDF menggunakan Aspose.PDF for .NET?

A: Membuat elemen struktur dalam dokumen PDF menggunakan Aspose.PDF for .NET meningkatkan aksesibilitas dan pengaturan konten dokumen. Elemen struktur menyediakan struktur hierarki yang meningkatkan navigasi, semantik, dan kompatibilitas dengan teknologi bantuan.

#### T: Bagaimana kode C# yang disediakan membuat elemen struktur dalam dokumen PDF?

A: Contoh kode menunjukkan cara membuat berbagai jenis elemen struktur, termasuk elemen pengelompokan (seperti bagian, seksi, dan div), elemen tingkat blok (seperti paragraf dan judul), elemen tingkat sebaris (span, kutipan, catatan), dan elemen karya seni (seperti gambar dan rumus). Elemen struktur ini membantu mengatur konten.

####  T: Mengapa penting untuk mengatur judul dan bahasa dokumen menggunakan`SetTitle` and `SetLanguage` methods?

 A: Mengatur judul dan bahasa dokumen menggunakan`SetTitle` Dan`SetLanguage`metode meningkatkan aksesibilitas dan semantik dokumen. Judul memberikan deskripsi singkat tentang tujuan dokumen, sementara atribut bahasa meningkatkan tampilan dan aksesibilitas khusus bahasa.

####  T: Bagaimana cara mengelompokkan elemen seperti`PartElement` and `SectElement`, contribute to the structure of the PDF document?

A: Pengelompokan elemen menciptakan struktur hierarkis dalam dokumen PDF, yang memungkinkan Anda mengatur dan mengelompokkan konten terkait secara logis. Hal ini meningkatkan navigasi dan menyediakan struktur yang jelas bagi pengguna.

#### T: Apa itu elemen struktur tingkat blok dan tingkat sebaris, dan apa perbedaannya?

A: Elemen struktur tingkat blok merepresentasikan blok konten yang lebih besar, seperti paragraf dan judul, sedangkan elemen tingkat sebaris merepresentasikan bagian teks dalam paragraf atau judul, seperti rentang, kutipan, dan catatan. Elemen ini membantu menentukan hierarki dan hubungan konten.

####  T: Bagaimana karya seni menyusun elemen-elemen, seperti`FigureElement` and `FormulaElement`, contribute to the document?

A: Elemen struktur karya seni memungkinkan Anda menambahkan ilustrasi, gambar, dan rumus matematika ke dalam dokumen. Elemen-elemen ini menyediakan cara terstruktur untuk menyertakan konten visual dan matematika.

#### T: Dapatkah saya menggunakan teknik serupa untuk membuat jenis elemen struktur lainnya, seperti daftar, tabel, atau anotasi?

A: Ya, Anda dapat menggunakan teknik serupa untuk membuat jenis elemen struktur lainnya seperti daftar, tabel, anotasi, referensi, dan lainnya. Aspose.PDF menyediakan berbagai metode pembuatan elemen struktur.

####  T: Bagaimana cara menyimpan dokumen PDF yang diberi tag menggunakan`Save` method ensure the preservation of structure elements?

 Sebuah:`Save` Metode ini menyimpan dokumen PDF bersama dengan elemen struktur yang dibuat, memastikan bahwa struktur hierarki dan semantik dokumen dipertahankan untuk aksesibilitas dan navigasi.

#### T: Manfaat apa yang diberikan elemen struktur pada dokumen PDF dalam hal aksesibilitas dan kompatibilitas dengan teknologi bantuan?

A: Elemen struktur meningkatkan aksesibilitas dengan menyediakan struktur dan semantik yang bermakna pada dokumen. Hal ini memungkinkan teknologi bantuan seperti pembaca layar untuk menafsirkan dan menyampaikan konten dokumen secara lebih efektif kepada pengguna penyandang disabilitas.

#### T: Bagaimana saya dapat menyesuaikan lebih lanjut dan menggabungkan berbagai jenis elemen struktur dalam dokumen PDF saya?

J: Anda dapat menggabungkan dan menyesuaikan elemen struktur dengan menggunakan metode pembuatan yang sesuai yang disediakan oleh Aspose.PDF. Bereksperimenlah dengan berbagai elemen dan propertinya untuk membuat dokumen PDF yang terstruktur dan terorganisasi dengan baik.