---
title: Elemen Struktur Tautan
linktitle: Elemen Struktur Tautan
second_title: Referensi API Aspose.PDF untuk .NET
description: Pelajari cara membuat elemen struktur tautan dalam PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah untuk menambahkan tautan yang dapat diakses, gambar, dan validasi kepatuhan.
type: docs
weight: 120
url: /id/net/programming-with-tagged-pdf/link-structure-elements/
---
## Perkenalan

Membuat dan mengelola elemen struktur tautan dalam PDF dapat menjadi hal yang penting untuk dokumen yang memerlukan aksesibilitas dan navigasi yang lancar. Dalam tutorial ini, kami akan memandu Anda untuk melakukannya menggunakan Aspose.PDF untuk .NET. Jika Anda baru mengenal Aspose.PDF atau manipulasi PDF secara umum, jangan khawatir. Saya akan menjelaskan setiap langkah secara terperinci sehingga Anda dapat mengikutinya dengan mudah!

## Prasyarat  

Sebelum kita mulai membuat kode, mari kita bahas beberapa hal terlebih dahulu. Berikut ini adalah persyaratan dasar untuk memastikan pengalaman pengembangan yang lancar.

1.  Aspose.PDF untuk .NET: Anda dapat mengunduh versi terbaru[Di Sini](https://releases.aspose.com/pdf/net/).
2. Lingkungan Pengembangan .NET: Baik itu Visual Studio atau IDE apa pun yang kompatibel dengan .NET, instal dan siapkan.
3.  Lisensi Aspose: Anda dapat menggunakan versi uji coba gratis Aspose.PDF[Di Sini](https://releases.aspose.com/) atau memperoleh[lisensi sementara](https://purchase.aspose.com/temporary-license/).
4. Pengetahuan Dasar C#: Kita akan bekerja dengan beberapa kode C#, jadi memahami dasar-dasarnya akan membuat segalanya lebih mudah.

## Paket Impor

Anda perlu mengimpor beberapa paket sebelum menulis kode untuk elemen struktur tautan. Mulailah dengan merujuk pustaka Aspose.PDF yang diperlukan dalam proyek Anda:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Impor ini memungkinkan kita bekerja dengan dokumen PDF, menambahkan tag, dan mengelola elemen struktur.

Sekarang kita akan membuat dokumen PDF dengan berbagai jenis struktur tautan, dan setiap langkah akan dipecah untuk membantu Anda memahami prosesnya secara menyeluruh.

## Langkah 1: Inisialisasi Dokumen  

Mari kita mulai dengan membuat dokumen PDF baru dan menyiapkan konten yang diberi tag untuk aksesibilitas.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Buat dokumen PDF baru
Document document = new Document(); 

// Ambil antarmuka TaggedContent
ITaggedContent taggedContent = document.TaggedContent;
```
  
 Di sini, kita menginisialisasi`Document` objek, yang mewakili file PDF kami. Kami juga mengambil`TaggedContent` antarmuka, yang memungkinkan kita menambahkan elemen struktur seperti paragraf, tautan, dan gambar.

## Langkah 2: Tetapkan Judul dan Bahasa  

Setiap PDF harus memiliki judul dan pengaturan bahasa, terutama jika Anda ingin mematuhi standar PDF/UA.

```csharp
// Mengatur judul dan bahasa dokumen
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");
```
  
Langkah ini memastikan bahwa PDF Anda memiliki judul yang bermakna dan mengatur bahasa ke Bahasa Inggris (`en-US`). Ini penting untuk aksesibilitas dan memastikan pembaca layar atau teknologi bantuan lainnya dapat menafsirkan dokumen Anda dengan benar.

## Langkah 3: Membuat dan Menambahkan Paragraf  

Pada langkah ini, kita akan menambahkan paragraf untuk menampung elemen tautan kita.

```csharp
// Buat elemen root
StructureElement rootElement = taggedContent.RootElement;

// Buat paragraf dan tambahkan ke elemen root
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```
  
Kami membuat elemen struktur akar, yang pada dasarnya merupakan wadah tingkat atas untuk semua elemen lainnya. Kemudian kami membuat paragraf (`p1`) dan menambahkannya ke elemen akar.

## Langkah 4: Tambahkan Tautan Sederhana  

Sekarang mari tambahkan hyperlink dasar yang mengarah ke Google.

```csharp
// Buat elemen tautan dan tambahkan ke paragraf
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);

// Tetapkan hyperlink dan teks untuk tautan
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
```
  
Pada langkah ini, kami membuat elemen tautan, menetapkan hyperlink-nya ke "http://google.com," dan menyediakan teks ("Google") untuk tautan tersebut. Kami juga menambahkan deskripsi alternatif untuk memastikan aksesibilitas.

## Langkah 5: Menambahkan Tautan dengan Span  

Kita juga dapat membuat tautan dengan rentang teks yang berbeda.

```csharp
// Buat paragraf lain
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);

// Buat tautan dengan elemen span
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");

SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);

link2.AlternateDescriptions = "Link to Google";
```
  
Di sini, kami menggunakan elemen span untuk melampirkan bagian teks di dalam tautan, yang memungkinkan kami menyesuaikan bagaimana bagian tertentu dari tautan muncul.

## Langkah 6: Tautan Multiline  

Bagaimana jika teks tautan Anda terlalu panjang? Jangan khawatir, Anda dapat membaginya menjadi beberapa baris.

```csharp
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);

LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google...");
link4.AlternateDescriptions = "Link to Google (multiline)";
```
  
Dalam kasus ini, kami membuat tautan multibaris hanya dengan menetapkan nilai teks yang panjang, dan teks akan otomatis terbungkus dalam beberapa baris.

## Langkah 7: Tambahkan Gambar ke Tautan  

Terakhir, Anda juga dapat menambahkan gambar di dalam tautan.

```csharp
// Buat paragraf baru dan elemen tautan
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);

LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");

// Tambahkan gambar ke tautan
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
link5.AppendChild(figure5);

link5.AlternateDescriptions = "Link to Google";
```
  
Langkah ini menunjukkan cara memperindah tautan dengan gambar. Dalam kasus ini, kami menambahkan ikon Google di dalam tautan. Kami juga memastikan aksesibilitas dengan menetapkan teks alternatif untuk gambar.

## Langkah 8: Validasi PDF untuk Kepatuhan  

Jika Anda ingin mematuhi PDF/UA (standar aksesibilitas), praktik yang baik adalah memvalidasi dokumen Anda.

```csharp
// Simpan dokumen PDF
document.Save(outFile);

// Validasi dokumen untuk kepatuhan PDF/UA
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```
  
Kami menyimpan dokumen dan memvalidasinya terhadap standar PDF/UA, yang memastikan PDF memenuhi persyaratan aksesibilitas.

## Kesimpulan  

Dalam tutorial ini, kami membahas cara membuat dokumen PDF terstruktur menggunakan Aspose.PDF untuk .NET. Dari menambahkan hyperlink dasar hingga struktur yang lebih kompleks seperti span, tautan multiline, dan bahkan gambar, panduan ini menyediakan dasar yang kuat untuk memanipulasi elemen tautan dalam PDF Anda. Dengan manfaat tambahan dari kepatuhan PDF/UA, Anda sekarang siap untuk membuat PDF yang mudah diakses dan dinavigasi.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menambahkan struktur yang lebih kompleks seperti tabel di dalam tautan?  
Tidak, tautan terutama untuk teks dan gambar, tetapi Anda dapat menyematkan elemen kompleks di dekatnya.

### Apakah validasi PDF/UA wajib?  
Tidak selalu, tetapi sangat disarankan jika Anda khawatir dengan aksesibilitas.

### Apa yang terjadi jika jalur berkas gambar salah?  
Dokumen tidak akan menampilkan gambar, dan mungkin menimbulkan kesalahan saat ditampilkan.

### Bisakah saya memberi gaya pada teks dalam tautan?  
Ya, Anda dapat menerapkan gaya teks menggunakan elemen span.

### Apakah mungkin untuk membuat tautan dokumen internal?  
Tentu saja! Anda dapat menautkan ke bagian tertentu dalam dokumen yang sama.