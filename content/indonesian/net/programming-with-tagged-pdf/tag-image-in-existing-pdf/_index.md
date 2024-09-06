---
title: Tag Gambar Dalam PDF yang Ada
linktitle: Tag Gambar Dalam PDF yang Ada
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara menandai gambar dalam PDF yang sudah ada dengan Aspose.PDF untuk .NET. Panduan Langkah demi Langkah untuk Menambahkan Tag ke Gambar.
type: docs
weight: 210
url: /id/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
Dalam tutorial terperinci ini, kami akan memandu Anda melalui kode sumber C# yang disediakan langkah demi langkah untuk menandai gambar dalam PDF yang sudah ada menggunakan Aspose.PDF untuk .NET. Ikuti petunjuk di bawah ini untuk memahami cara menambahkan tag ke gambar dalam PDF.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda telah mengonfigurasi lingkungan pengembangan Anda untuk menggunakan Aspose.PDF untuk .NET. Ini termasuk menginstal pustaka Aspose.PDF dan mengonfigurasi proyek Anda untuk merujuknya.

## Langkah 2: Buka dokumen PDF yang ada

Pada langkah ini, kita akan membuka dokumen PDF yang ada menggunakan Aspose.PDF.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Jalur file input dan output
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Buka dokumennya
Document document = new Document(inFile);
```

Kami membuka dokumen PDF yang ada menggunakan Aspose.PDF.

## Langkah 3: Dapatkan Konten yang Ditandai dan Elemen Struktur Root

Sekarang kita akan mendapatkan konten yang ditandai dari dokumen PDF dan elemen struktur akar yang sesuai.

```csharp
// Dapatkan konten yang ditandai dan elemen struktur root
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Kami mendapatkan konten yang ditandai dari dokumen PDF dan elemen struktur akar yang sesuai.

## Langkah 4: Mengatur judul untuk dokumen PDF yang diberi tag

Sekarang mari kita tetapkan judul untuk dokumen PDF yang diberi tag.

```csharp
// Tentukan judul untuk dokumen PDF yang diberi tag
taggedContent.SetTitle("Document with images");
```

Kami telah menetapkan judul untuk dokumen PDF yang diberi tag.

## Langkah 5: Tetapkan teks alt dan kotak pembatas ke gambar

Sekarang, untuk setiap elemen gambar, kita akan menetapkan teks alt dan kotak pembatas.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Tetapkan teks alternatif ke gambar
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Membuat dan menetapkan kotak pembatas (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

Kami telah menetapkan teks alt dan kotak pembatas untuk setiap elemen gambar dalam dokumen PDF.

## Langkah 6: Memindahkan elemen Span ke dalam paragraf

Sekarang mari pindahkan elemen Span ke dalam paragraf.

```csharp
// Pindahkan elemen Span ke paragraf (temukan span dan paragraf yang salah di TD pertama)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Pindahkan elemen Span di paragraf
spanElement.ChangeParentElement(paragraph);
```

Kami memindahkan elemen Span ke paragraf yang ditentukan.

## Langkah 7: Menyimpan dokumen PDF yang dimodifikasi

Sekarang setelah kita membuat perubahan yang diperlukan, kita akan menyimpan dokumen PDF yang telah dimodifikasi.

```csharp
// Simpan dokumen PDF
document. Save(outFile);
```

Kami menyimpan dokumen PDF yang dimodifikasi di direktori yang ditentukan.

### Contoh kode sumber untuk Tag Gambar dalam PDF yang Ada menggunakan Aspose.PDF untuk .NET 

```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Buka dokumen
Document document = new Document(inFile);

// Mendapatkan konten yang ditandai dan elemen struktur akar
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Tetapkan judul untuk dokumen pdf yang diberi tag
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Tetapkan Teks Alternatif untuk Gambar
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// Membuat dan Mengatur Atribut BBox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Pindahkan Elemen Span ke Paragraf (temukan span dan paragraf yang salah di TD pertama)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Pindahkan Elemen Span ke Paragraf
spanElement.ChangeParentElement(paragraph);

// Simpan dokumen
document.Save(outFile);

//Memeriksa Kepatuhan PDF/UA untuk dokumen kami
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menandai gambar dalam PDF yang sudah ada menggunakan Aspose.PDF untuk .NET. Kini Anda dapat menggunakan Aspose.PDF untuk menambahkan tag dan mengedit gambar dalam dokumen PDF Anda.

### Pertanyaan yang Sering Diajukan

#### T: Apa tujuan utama tutorial ini untuk menandai gambar dalam PDF yang ada menggunakan Aspose.PDF for .NET?

J: Tujuan utama tutorial ini adalah memandu Anda melalui proses penandaan gambar dalam dokumen PDF yang ada menggunakan Aspose.PDF for .NET. Tutorial ini menyediakan petunjuk langkah demi langkah dan contoh kode sumber C# untuk membantu Anda memahami cara menetapkan teks alternatif dan kotak pembatas pada gambar, memindahkan elemen dalam dokumen, dan menambahkan tag pada gambar.

#### T: Apa saja prasyarat untuk mengikuti tutorial penandaan gambar dalam PDF menggunakan Aspose.PDF for .NET?

J: Sebelum memulai, pastikan Anda telah menyiapkan lingkungan pengembangan untuk menggunakan Aspose.PDF untuk .NET. Ini melibatkan pemasangan pustaka Aspose.PDF dan konfigurasi proyek Anda untuk merujuknya.

#### T: Bagaimana cara membuka dokumen PDF yang ada dan mengakses konten yang diberi tag menggunakan Aspose.PDF untuk .NET?

A: Tutorial ini menyediakan contoh kode sumber C# yang menunjukkan cara membuka dokumen PDF yang ada menggunakan Aspose.PDF for .NET dan mengakses konten yang diberi tag untuk manipulasi lebih lanjut.

#### T: Apa tujuan menetapkan teks alternatif dan kotak pembatas pada gambar dalam dokumen PDF?

A: Menetapkan teks alternatif dan kotak pembatas pada gambar meningkatkan aksesibilitas dengan menyediakan teks deskriptif untuk gambar dan menentukan tata letak serta posisinya dalam dokumen. Informasi ini penting untuk pembaca layar dan teknologi bantuan lainnya.

#### T: Bagaimana cara menetapkan judul untuk dokumen PDF yang diberi tag menggunakan Aspose.PDF untuk .NET?

A: Tutorial menyertakan contoh kode sumber C# yang mengilustrasikan cara menetapkan judul untuk dokumen PDF yang diberi tag menggunakan Aspose.PDF untuk .NET.

#### T: Apa saja proses pemindahan elemen dalam dokumen PDF?

A: Memindahkan elemen dalam dokumen PDF melibatkan perubahan elemen induk dari elemen tertentu. Dalam tutorial ini, Anda akan mempelajari cara memindahkan elemen Span ke elemen Paragraph tertentu dalam tabel.

#### T: Bagaimana cara menyimpan dokumen PDF yang dimodifikasi setelah menambahkan tag dan mengedit gambar?

 A: Setelah Anda menambahkan tag, menetapkan teks alternatif, mengatur kotak pembatas, dan melakukan pengeditan pada dokumen PDF, Anda dapat menggunakan contoh kode sumber C# yang disediakan untuk menyimpan dokumen PDF yang dimodifikasi menggunakan`Save()` metode.

#### T: Apa tujuan dari contoh kode sumber yang disediakan dalam tutorial?

A: Contoh kode sumber berfungsi sebagai referensi praktis untuk menerapkan penandaan dan manipulasi gambar menggunakan Aspose.PDF untuk .NET. Anda dapat menggunakan kode ini sebagai titik awal dan memodifikasinya agar sesuai dengan kebutuhan spesifik Anda.

#### T: Dapatkah saya menerapkan teknik ini ke jenis elemen lain dalam dokumen PDF, bukan hanya gambar?

J: Ya, teknik yang ditunjukkan dalam tutorial ini dapat disesuaikan untuk bekerja dengan berbagai jenis elemen dalam dokumen PDF. Anda dapat menerapkan prinsip serupa untuk memberi tag dan memanipulasi elemen lain seperti teks, tabel, dan lainnya.

#### T: Bagaimana saya dapat memvalidasi kepatuhan PDF/UA dari dokumen PDF yang dimodifikasi?

 A: Tutorial ini menyediakan contoh kode sumber C# yang menunjukkan cara memvalidasi kepatuhan PDF/UA dari dokumen PDF yang dimodifikasi dengan menggunakan`Validate()` metode dan menghasilkan laporan XML.

#### T: Fitur lain apa yang ditawarkan Aspose.PDF for .NET untuk bekerja dengan dokumen PDF?

J: Aspose.PDF untuk .NET menawarkan berbagai fitur untuk bekerja dengan dokumen PDF, termasuk manipulasi teks, penyisipan gambar, pembuatan tabel, manajemen bidang formulir, tanda tangan digital, anotasi, dan banyak lagi. Lihat dokumentasi dan sumber daya resmi untuk eksplorasi lebih lanjut.