---
title: Tag Gambar Dalam PDF yang Ada
linktitle: Tag Gambar Dalam PDF yang Ada
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara memberi tag pada gambar dalam PDF yang ada menggunakan Aspose.PDF for .NET. Panduan langkah demi langkah untuk meningkatkan aksesibilitas dengan kepatuhan PDF/UA.
type: docs
weight: 210
url: /id/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## Perkenalan

Dalam tutorial ini, kami akan memandu Anda untuk memberi tag pada gambar dalam PDF yang sudah ada menggunakan Aspose.PDF for .NET. Di akhir panduan ini, Anda akan dapat mengatur teks alternatif untuk gambar, menyesuaikan atribut tata letak, dan memastikan PDF Anda mematuhi standar aksesibilitas.

## Prasyarat

Sebelum kita mulai, mari kita bahas apa saja yang Anda perlukan untuk memulai:

-  Aspose.PDF untuk .NET: Pastikan Anda telah mengunduh dan menginstal versi terbaru Aspose.PDF untuk .NET.[Unduh di sini](https://releases.aspose.com/pdf/net/).
- .NET Framework: Pastikan Anda telah menyiapkan lingkungan pengembangan .NET seperti Visual Studio.
- Pemahaman Dasar tentang Struktur PDF: Keakraban dengan elemen struktur PDF seperti paragraf, rentang, tabel, dan gambar.
-  Lisensi yang Valid: Anda dapat membeli lisensi[Di Sini](https://purchase.aspose.com/buy) atau gunakan yang sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

## Paket Impor

Untuk memulai pengodean, Anda perlu mengimpor namespace penting dari Aspose.PDF untuk .NET. Ini akan memberi Anda akses ke kelas dan metode yang diperlukan untuk memanipulasi dokumen PDF.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Sekarang setelah kita menyiapkan tahapannya, mari kita uraikan proses penandaan gambar ke dalam beberapa langkah.

## Langkah 1: Muat Dokumen PDF yang Ada

Langkah pertama adalah memuat berkas PDF yang ingin Anda gunakan. Ini bisa berupa berkas PDF apa pun dengan gambar yang ingin Anda beri tag.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Buka dokumennya
Document document = new Document(inFile);
```

-  Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke berkas Anda.
-  Itu`Document` kelas memungkinkan Anda memuat PDF yang sudah ada. Anda akan memodifikasi PDF ini untuk menandai gambar.

## Langkah 2: Akses Konten yang Ditandai dan Elemen Struktur Root

Setelah Anda membuka PDF, langkah selanjutnya adalah mengakses konten yang diberi tag dan mengidentifikasi elemen struktur akar. Hal ini penting karena memungkinkan Anda menelusuri elemen-elemen dalam PDF dan melakukan modifikasi.

```csharp
// Dapatkan konten yang ditandai dan elemen struktur root
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent` menyediakan akses ke elemen terstruktur dalam PDF.
-  Itu`RootElement` adalah elemen struktur paling atas, dari mana Anda dapat menelusuri ke elemen lain seperti paragraf, tabel, dan gambar.

## Langkah 3: Tetapkan Judul untuk Dokumen PDF yang Ditandai

Menambahkan judul pada dokumen PDF yang diberi tag memastikan bahwa dokumen Anda diberi label dengan benar, yang berguna untuk aksesibilitas dan kepatuhan PDF/UA.

```csharp
// Tetapkan judul untuk dokumen PDF yang diberi tag
taggedContent.SetTitle("Document with images");
```

- Menetapkan judul untuk PDF yang diberi tag akan meningkatkan aksesibilitas dan menambah kejelasan dokumen untuk pembaca layar dan teknologi bantuan.

## Langkah 4: Temukan dan Beri Tag pada Gambar

 Sekarang, mari kita temukan elemen gambar (disebut sebagai`FigureElement` dalam Aspose.PDF), tetapkan teks alternatif untuknya, dan konfigurasikan atribut tata letaknya.

```csharp
// Ulangi semua elemen Gambar (gambar) dan atur teks alternatif serta atribut tata letak
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    // Tetapkan teks alternatif untuk gambar
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    // Membuat dan mengatur atribut BBox (kotak pembatas)
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    // Tetapkan atribut tata letak untuk gambar
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

-  Kode ini mengulang semua`FigureElement` objek dalam struktur akar, yang merepresentasikan gambar.
- Ini menetapkan teks alternatif untuk aksesibilitas (pembaca layar akan menggunakan ini untuk mendeskripsikan gambar).
- Kotak pembatas (`BBox`menentukan koordinat untuk tata letak gambar, memastikannya ditampilkan dengan benar dalam dokumen.

## Langkah 5: Ubah Elemen Span dalam Tabel

 Dalam beberapa kasus, Anda mungkin perlu mengubah elemen span dalam tabel. Di sini, kami akan menunjukkan cara menemukan`SpanElement` dan memindahkannya ke dalam paragraf.

```csharp
// Temukan elemen tabel, rentang, dan paragraf
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Pindahkan elemen span ke dalam paragraf
spanElement.ChangeParentElement(paragraph);
```

-  Di sini, kita menemukan`TableElement`, `SpanElement` , Dan`ParagraphElement` dalam PDF.
-  Menggunakan`ChangeParentElement` metode, kami memindahkan rentang ke dalam paragraf untuk memastikan penandaan dan struktur yang tepat.

## Langkah 6: Simpan Dokumen dan Validasi Kepatuhan PDF/UA

Setelah semua perubahan dibuat, langkah terakhir adalah menyimpan PDF yang diperbarui dan memeriksa apakah sudah mematuhi standar PDF/UA.

```csharp
// Simpan dokumen PDF yang diperbarui
document.Save(outFile);

// Validasi kepatuhan PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

-  Itu`Validate` Metode ini memeriksa dokumen PDF terhadap standar PDF/UA dan mencatat hasilnya.
- Memastikan kepatuhan membantu meningkatkan aksesibilitas dan memenuhi persyaratan peraturan untuk penerbitan dokumen.

## Kesimpulan

Dalam tutorial ini, kami telah menunjukkan kepada Anda cara memberi tag pada gambar dalam PDF yang sudah ada menggunakan Aspose.PDF untuk .NET. Dengan menetapkan teks alternatif, menyesuaikan atribut tata letak, dan memvalidasi dokumen untuk kepatuhan PDF/UA, Anda dapat memastikan bahwa PDF Anda dapat diakses dan memenuhi standar modern. Aspose.PDF memudahkan Anda untuk bekerja dengan elemen terstruktur, memberi Anda kendali atas tata letak dan aksesibilitas dokumen Anda.

## Pertanyaan yang Sering Diajukan

### Untuk apa Aspose.PDF for .NET digunakan?
Aspose.PDF untuk .NET adalah pustaka hebat yang digunakan untuk membuat, mengedit, dan memanipulasi dokumen PDF secara terprogram dalam lingkungan .NET.

### Bagaimana cara memastikan kepatuhan PDF/UA?
 Anda dapat menggunakan Aspose.PDF`Validate` metode untuk memeriksa kepatuhan PDF/UA setelah membuat modifikasi pada dokumen.

### Apa itu teks alternatif dalam PDF?
Teks alternatif adalah deskripsi yang ditambahkan ke gambar dalam PDF untuk meningkatkan aksesibilitas, khususnya bagi pengguna yang mengandalkan pembaca layar.

### Bisakah saya memanipulasi tabel dan rentang dalam PDF dengan Aspose.PDF?
Ya, Aspose.PDF memungkinkan Anda memanipulasi tabel, rentang, dan elemen terstruktur lainnya dalam dokumen PDF.

### Di mana saya dapat mengunduh Aspose.PDF untuk .NET?
 Anda dapat mengunduh versi terbaru Aspose.PDF untuk .NET[Di Sini](https://releases.aspose.com/pdf/net/).