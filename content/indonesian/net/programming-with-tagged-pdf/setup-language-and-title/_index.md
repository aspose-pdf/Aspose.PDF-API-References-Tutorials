---
title: Pengaturan Bahasa Dan Judul
linktitle: Pengaturan Bahasa Dan Judul
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk mengonfigurasi bahasa dan judul dokumen PDF dengan Aspose.PDF untuk .NET. Buat dokumen multibahasa yang dipersonalisasi.
type: docs
weight: 140
url: /id/net/programming-with-tagged-pdf/setup-language-and-title/
---
Dalam panduan ini, kami akan memberi tahu Anda cara mengonfigurasi bahasa dan judul dokumen PDF menggunakan perpustakaan Aspose.PDF untuk .NET. Aspose.PDF adalah perpustakaan canggih yang memungkinkan Anda membuat, memanipulasi, dan mengonversi file PDF secara terprogram.

Mari selami kodenya dan pelajari cara mengonfigurasi bahasa dan judul dokumen PDF menggunakan Aspose.PDF untuk .NET.

## Prasyarat

Sebelum memulai, pastikan Anda telah menginstal Aspose.PDF untuk .NET dan menyiapkan lingkungan pengembangan Anda.

## Langkah 1: Membuat dokumen

 Langkah pertama adalah membuat dokumen PDF baru menggunakan`Document` kelas.

```csharp
// Buat dokumen PDF
Document document = new Document();
```

## Langkah 2: Akses konten yang diberi tag

 Selanjutnya, kita mengakses konten dokumen yang diberi tag menggunakan`ITaggedContent` obyek.

```csharp
// Akses konten yang diberi tag
Tagged.ITaggedContent taggedContent = document.TaggedContent;
```

## Langkah 3: Tetapkan judul dan bahasa

 Sekarang kita dapat mengatur judul dan bahasa dokumen menggunakan`SetTitle` Dan`SetLanguage` metode dari`ITaggedContent` obyek.

```csharp
// Tentukan judul dokumen
taggedContent.SetTitle("Example of tagged document");

// Atur bahasa dokumen
taggedContent.SetLanguage("fr-FR");
```

## Langkah 4: Tambahkan konten multibahasa

Selanjutnya, kami menambahkan konten multibahasa ke dokumen menggunakan elemen paragraf untuk setiap bahasa.

```csharp
// Tambahkan paragraf dalam bahasa Inggris
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Tambahkan paragraf dalam bahasa Jerman
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hello Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

//Tambahkan paragraf dalam bahasa Prancis
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Hello world!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Tambahkan paragraf dalam bahasa Spanyol
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);
```

## Langkah 5: Simpan dokumen PDF yang diberi tag

Terakhir, kami menyimpan dokumen PDF yang diberi tag.

```csharp
// Simpan dokumen PDF yang diberi tag
document.Save(dataDir + "SetupLanguageAndTitle.pdf");
```

### Contoh kode sumber untuk Bahasa Pengaturan dan Judul menggunakan Aspose.PDF untuk .NET 
```csharp

Document document = new Document();

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dapatkan Konten yang Ditandai
Tagged.ITaggedContent taggedContent = document.TaggedContent;

// Tetapkan Judul dan Bahasa
taggedContent.SetTitle("Example Tagged Document");
taggedContent.SetLanguage("en-US");

// Header (en-US, diwarisi dari dokumen)
LogicalStructure.HeaderElement h1 = taggedContent.CreateHeaderElement(1);
h1.SetText("Phrase on different languages");
taggedContent.RootElement.AppendChild(h1);

// Paragraf (Bahasa Inggris)
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Paragraf (Jerman)
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hallo Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Paragraf (Perancis)
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Bonjour le monde!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Paragraf (Spanyol)
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);

// Simpan Dokumen Pdf yang Ditandai
document.Save(dataDir + "SetupLanguageAndTitle.pdf");

```

## Kesimpulan

Selamat! Anda sekarang mengetahui cara mengonfigurasi bahasa dan judul dokumen PDF menggunakan Aspose.PDF untuk .NET. Anda dapat menjelajahi lebih jauh fitur Aspose.PDF untuk membuat dokumen PDF yang dipersonalisasi dan multibahasa.

### FAQ

#### T: Apa pentingnya mengonfigurasi bahasa dan judul dokumen PDF?

J: Mengonfigurasi bahasa dan judul dokumen PDF penting untuk aksesibilitas dan metadata. Mengatur bahasa yang benar memastikan penandaan bahasa dan ekstraksi teks yang tepat, sekaligus memberikan judul yang sesuai akan meningkatkan identifikasi dan pengorganisasian dokumen.

#### T: Bagaimana Aspose.PDF untuk .NET memfasilitasi konfigurasi bahasa dan judul dokumen?

 J: Aspose.PDF untuk .NET menyediakan API untuk mengatur judul dan bahasa dokumen dengan mudah menggunakan`SetTitle` Dan`SetLanguage` metode dari`ITaggedContent` obyek. Hal ini memungkinkan Anda memastikan representasi bahasa yang akurat dan judul dokumen yang bermakna.

#### T: Bisakah saya mengatur bahasa berbeda untuk bagian tertentu dokumen PDF menggunakan Aspose.PDF untuk .NET?

 J: Ya, Anda dapat mengatur bahasa berbeda untuk bagian tertentu dokumen PDF menggunakan Aspose.PDF untuk .NET. Dengan menerapkan`Language` properti ke elemen paragraf, Anda dapat menentukan bahasa untuk setiap bagian konten, memungkinkan dokumen multibahasa.

#### T: Mengapa konten multibahasa penting, dan bagaimana cara menambahkannya ke dokumen PDF menggunakan Aspose.PDF untuk .NET?

J: Konten multibahasa meningkatkan aksesibilitas dan jangkauan global dokumen PDF. Aspose.PDF untuk .NET memungkinkan Anda menambahkan konten multibahasa dengan membuat elemen paragraf untuk setiap bahasa, mengatur properti teks dan bahasa yang sesuai.

####  T: Bagaimana caranya`SetTitle` method contribute to improving document accessibility and organization?

 J: Itu`SetTitle` metode menetapkan judul dokumen PDF, yang digunakan untuk identifikasi dokumen, hasil pencarian, dan organisasi. Memberikan judul yang jelas dan bermakna akan meningkatkan aksesibilitas dokumen dan meningkatkan pengalaman pengguna.

####  T: Apa peran dari`SetLanguage` method in PDF document configuration?

 J: Itu`SetLanguage` metode menetapkan bahasa default untuk dokumen PDF, memastikan penandaan bahasa dan ekstraksi teks yang akurat. Ini membantu menjaga konsistensi bahasa dan aksesibilitas di seluruh dokumen.

#### T: Bisakah saya menggunakan Aspose.PDF untuk .NET untuk mengatur judul dan bahasa dokumen secara dinamis berdasarkan preferensi pengguna?

J: Ya, Anda dapat mengatur judul dan bahasa dokumen secara dinamis berdasarkan preferensi pengguna menggunakan Aspose.PDF untuk .NET. Dengan mengintegrasikan input pengguna atau data sistem, Anda dapat menyesuaikan judul dokumen dan bahasanya.

#### T: Bagaimana cara memverifikasi bahwa konfigurasi bahasa dan judul telah diterapkan dengan benar pada dokumen PDF?

J: Anda dapat memverifikasi konfigurasi bahasa dan judul dengan memeriksa properti dan metadata dokumen PDF. Anda juga dapat menggunakan penampil PDF atau alat ekstraksi teks untuk memastikan penandaan bahasa dan judul dokumen akurat.

#### T: Apakah ada praktik terbaik yang harus diikuti saat mengonfigurasi bahasa dan judul dokumen PDF?

J: Saat mengonfigurasi bahasa dan judul, pertimbangkan audiens yang dituju, konten dokumen, dan persyaratan aksesibilitas. Pilih judul deskriptif dan pengaturan bahasa yang akurat untuk meningkatkan kegunaan dan aksesibilitas dokumen.

#### T: Dapatkah saya mengubah bahasa dan judul dokumen PDF yang sudah ada menggunakan Aspose.PDF untuk .NET?

 J: Ya, Anda dapat mengubah bahasa dan judul dokumen PDF yang ada menggunakan Aspose.PDF untuk .NET. Dengan memuat dokumen, mengakses konten yang diberi tag, dan menggunakan`SetTitle` Dan`SetLanguage`metode, Anda dapat memperbarui atribut ini sesuai kebutuhan.
