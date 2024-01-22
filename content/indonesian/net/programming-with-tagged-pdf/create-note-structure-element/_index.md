---
title: Buat Elemen Struktur Catatan
linktitle: Buat Elemen Struktur Catatan
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk membuat item catatan terstruktur dalam dokumen PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 30
url: /id/net/programming-with-tagged-pdf/create-note-structure-element/
---
Dalam tutorial ini, kami akan memberi Anda panduan langkah demi langkah tentang cara membuat elemen struktur catatan dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Aspose.PDF adalah perpustakaan canggih yang memungkinkan Anda membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram. Dengan menggunakan fitur struktur konten yang ditandai dari Aspose.PDF, Anda dapat menambahkan catatan terstruktur ke dokumen PDF Anda.

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

## Langkah 3: Membuat Dokumen PDF dan Catatan Elemen Terstruktur

Gunakan kode berikut untuk membuat dokumen PDF dan menambahkan elemen terstruktur catatan:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

Kode ini membuat dokumen PDF kosong dan menambahkan elemen catatan terstruktur ke paragraf. Setiap catatan dibuat menggunakan metode yang disediakan oleh Aspose.PDF.

## Langkah 4: Menyimpan Dokumen PDF

Gunakan kode berikut untuk menyimpan dokumen PDF:

```csharp
document. Save(outFile);
```

Kode ini menyimpan dokumen PDF dengan elemen terstruktur catatan ke file tertentu.

### Contoh kode sumber untuk Membuat Elemen Struktur Catatan menggunakan Aspose.PDF untuk .NET 

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Buat Dokumen Pdf
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Tambahkan Elemen Paragraf
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// Tambahkan NoteElement
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// Tambahkan NoteElement
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// Tambahkan NoteElement
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// Harus mengeluarkan pengecualian - Aspose.Pdf.Tagged.TaggedException : Elemen struktur dengan ID='note_002' sudah ada
//note3.SetId("catatan_002");
// Dokumen yang dihasilkan tidak sesuai dengan PDF/UA Jika ClearId() digunakan untuk Elemen Struktur Catatan
//catatan3.ClearId();
// Simpan Dokumen Pdf yang Ditandai
document.Save(outFile);
// Memeriksa kepatuhan PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Kesimpulan

Dalam tutorial ini, Anda mempelajari cara membuat elemen struktur catatan dalam dokumen PDF menggunakan Aspose.PDF untuk .NET. Elemen catatan terstruktur memungkinkan Anda menambahkan informasi tambahan dan terstruktur ke dokumen PDF Anda.

### FAQ

#### T: Apa tujuan membuat elemen struktur catatan dalam dokumen PDF menggunakan Aspose.PDF untuk .NET?

J: Membuat elemen struktur catatan dalam dokumen PDF menggunakan Aspose.PDF untuk .NET memungkinkan Anda menambahkan catatan terstruktur ke konten dokumen. Catatan ini dapat memberikan konteks tambahan, penjelasan, atau referensi ke bagian konten tertentu.

#### T: Bagaimana perpustakaan Aspose.PDF membantu dalam membuat elemen struktur catatan dalam dokumen PDF?

J: Aspose.PDF untuk .NET adalah perpustakaan canggih yang menyediakan fungsionalitas untuk membuat, memanipulasi, dan mengonversi dokumen PDF secara terprogram. Dalam tutorial ini, fitur struktur konten yang ditandai perpustakaan digunakan untuk membuat elemen catatan terstruktur dalam konten dokumen PDF.

#### T: Apa saja prasyarat untuk membuat elemen struktur catatan dalam dokumen PDF menggunakan Aspose.PDF untuk .NET?

J: Sebelum memulai, pastikan Anda telah menginstal Visual Studio dengan kerangka .NET dan memiliki pustaka Aspose.PDF untuk .NET yang direferensikan dalam proyek Anda.

#### T: Bagaimana cara kode C# yang disediakan membuat elemen struktur catatan di konten dokumen PDF?

J: Kode ini menunjukkan cara membuat dokumen PDF, menentukan elemen terstruktur catatan, dan menambahkannya ke paragraf. Setiap catatan dibuat menggunakan metode yang disediakan oleh Aspose.PDF, memungkinkan Anda memasukkan catatan terstruktur ke dalam konten.

#### T: Dapatkah saya menyesuaikan konten dan properti elemen struktur catatan yang saya buat?

J: Ya, Anda dapat mengkustomisasi konten dan properti elemen struktur catatan dengan menggunakan metode dan properti yang disediakan oleh pustaka Aspose.PDF. Kode ini menunjukkan cara mengatur teks dan ID elemen catatan, tetapi Anda dapat menyesuaikannya lebih lanjut sesuai kebutuhan.

#### T: Bagaimana hubungan hierarki terbentuk antara elemen struktur catatan dan konten dokumen?

 J: Hubungan hierarki dibuat dengan menambahkan elemen struktur catatan sebagai turunan dari elemen terstruktur lainnya, misalnya paragraf. Dalam kode, elemen catatan ditambahkan ke elemen paragraf menggunakan`AppendChild` metode.

#### T: Bisakah saya menetapkan ID unik ke elemen struktur catatan?

J: Ya, Anda dapat menetapkan ID unik ke elemen struktur catatan menggunakan`SetId` metode. Kode ini menunjukkan cara mengatur ID elemen catatan ke nilai unik.

#### T: Apa yang terjadi jika saya mencoba menetapkan ID duplikat ke elemen struktur catatan?

J: Mencoba menetapkan ID duplikat ke elemen struktur catatan akan menghasilkan pengecualian. Kode yang disediakan dalam tutorial menyertakan komentar yang menggambarkan skenario ini.

#### T: Bagaimana cara memastikan kepatuhan PDF/UA saat membuat elemen struktur catatan?

 J: Kode yang diberikan dalam tutorial menunjukkan cara memvalidasi kepatuhan PDF/UA menggunakan`Validate` metode. Dengan memvalidasi dokumen berdasarkan standar PDF/UA, Anda dapat memastikan bahwa elemen struktur catatan yang ditambahkan mematuhi pedoman aksesibilitas.

#### T: Dapatkah saya menggunakan pendekatan ini untuk menambahkan elemen struktur catatan ke dokumen PDF yang sudah ada?

J: Ya, Anda dapat mengubah pendekatan yang disediakan untuk menambahkan elemen struktur catatan ke dokumen PDF yang sudah ada. Daripada membuat dokumen baru, Anda akan memuat dokumen yang sudah ada menggunakan Aspose.PDF lalu ikuti langkah serupa untuk menambahkan elemen catatan.
