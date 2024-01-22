---
title: Ganti Font yang Hilang
linktitle: Ganti Font yang Hilang
second_title: Aspose.PDF untuk Referensi .NET API
description: Panduan langkah demi langkah untuk mengganti font yang hilang dalam file PDF menggunakan Aspose.PDF untuk .NET.
type: docs
weight: 260
url: /id/net/document-conversion/replace-missing-fonts/
---
Dalam tutorial ini, kami akan memandu Anda melalui proses penggantian font yang hilang dalam file PDF menggunakan Aspose.PDF untuk .NET. Saat Anda membuka file PDF di mesin yang font tertentu tidak ada, mungkin ada masalah tampilan font. Dalam kasus seperti ini, dimungkinkan untuk mengganti font yang hilang dengan font lain yang tersedia di mesin. Dengan mengikuti langkah-langkah di bawah ini, Anda akan dapat mengganti font yang hilang di file PDF.

## Prasyarat
Sebelum memulai, pastikan Anda memenuhi prasyarat berikut:

- Pengetahuan dasar tentang bahasa pemrograman C#.
- Pustaka Aspose.PDF untuk .NET diinstal di sistem Anda.
- Lingkungan pengembangan seperti Visual Studio.

## Langkah 1: Menemukan font yang hilang
Langkah pertama adalah mencari font yang hilang di file PDF. Gunakan kode berikut:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     // Temukan font aslinya
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     // Font tidak ada di mesin tujuan
     // Tambahkan substitusi font sederhana
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

 Pastikan untuk mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan direktori sebenarnya tempat file PDF Anda berada.

## Langkah 2: Ganti font yang hilang
Selanjutnya, kita akan mengganti font yang hilang dengan font lain yang tersedia. Gunakan kode berikut:

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

// Konversikan file PDF ke format PDF/A dengan penghapusan kesalahan
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// Simpan file PDF yang dihasilkan
pdf.Save(fileNew.FullName);
```

 Pastikan untuk mengganti`"input.pdf"` dengan jalur sebenarnya ke file PDF asli Anda dan`"newfile_out.pdf"` dengan nama yang diinginkan untuk file PDF yang dihasilkan.

## Langkah 3: Menyimpan file PDF yang dihasilkan
Terakhir, kami akan menyimpan file PDF yang dihasilkan dengan font yang diganti. Gunakan kode berikut:

```csharp
// Simpan file PDF yang dihasilkan
pdf.Save(fileNew.FullName);
```

Pastikan Anda telah menetapkan jalur tujuan yang benar untuk file PDF yang dihasilkan.

### Contoh kode sumber untuk Ganti Font yang Hilang menggunakan Aspose.PDF untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	// Font hilang di mesin tujuan
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## Kesimpulan
Dalam tutorial ini, kami membahas proses langkah demi langkah mengganti font yang hilang dalam file PDF menggunakan Aspose.PDF untuk .NET. Dengan mengikuti petunjuk yang diuraikan di atas, Anda akan berhasil mengganti font yang hilang di file PDF Anda.

### FAQ

#### T: Apa itu Aspose.PDF untuk .NET?

J: Aspose.PDF untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan dokumen PDF dalam aplikasi C#. Ia menawarkan berbagai fungsi, termasuk kemampuan untuk mengganti font yang hilang dalam file PDF.

#### T: Mengapa saya menemukan font yang hilang di file PDF?

J: Font yang hilang dalam file PDF dapat terjadi ketika file dibuka di mesin yang tidak menginstal font yang diperlukan. Hal ini dapat menyebabkan penggantian font, sehingga memengaruhi tampilan visual dokumen.

#### T: Bagaimana cara menemukan dan mengganti font yang hilang dalam file PDF menggunakan Aspose.PDF untuk .NET?

 A: Untuk mencari dan mengganti font yang hilang, Anda dapat menggunakan`FontRepository.FindFont` metode untuk memeriksa keberadaan font yang diperlukan. Jika fontnya hilang, Anda dapat menambahkan substitusi font menggunakan`FontRepository.Substitutions` Properti.

#### T: Dapatkah saya menyesuaikan proses penggantian font?

J: Ya, Anda dapat menyesuaikan proses penggantian font dengan menentukan font berbeda untuk penggantian tersebut. Dalam kode yang diberikan, kami menggunakan Arial sebagai pengganti font "AgencyFB" yang hilang, tetapi Anda dapat memilih font lain sesuai preferensi Anda.

#### T: Bagaimana cara memastikan keakuratan rendering font setelah substitusi?

J: Aspose.PDF untuk .NET memberikan kemampuan penanganan font yang kuat, memastikan rendering font yang akurat setelah substitusi. Anda dapat melihat pratinjau file PDF yang dihasilkan untuk memverifikasi penggantian font.