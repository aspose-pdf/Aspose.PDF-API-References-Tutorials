---
title: Atur Info File Dalam File PDF
linktitle: Atur Info File Dalam File PDF
second_title: Aspose.PDF untuk Referensi .NET API
description: Pelajari cara menggunakan Aspose.PDF untuk .NET untuk mengatur info file dalam file PDF dengan panduan langkah demi langkah ini.
type: docs
weight: 310
url: /id/net/programming-with-document/setfileinfo/
---
Jika Anda mengerjakan proyek yang memerlukan pengelolaan file PDF menggunakan Aspose.PDF untuk .NET, salah satu fitur yang mungkin ingin Anda manfaatkan adalah kemampuan untuk mengatur informasi file untuk dokumen PDF. Informasi file mencakup berbagai detail seperti penulis, tanggal pembuatan, kata kunci, tanggal modifikasi, subjek, dan judul. Panduan ini akan memandu Anda melalui proses pengaturan informasi file untuk dokumen PDF menggunakan kode sumber C# dengan Aspose.PDF untuk .NET.

## Panduan langkah demi langkah untuk mengatur info file menggunakan Aspose.PDF untuk .NET

1. Buat proyek C# baru di Visual Studio IDE Anda.
2. Tambahkan referensi ke perpustakaan Aspose.PDF untuk .NET di proyek Anda.
3. Buat objek dokumen PDF baru dengan memberikan jalur ke file PDF yang informasi filenya ingin Anda ubah.

## Langkah 1: Tetapkan jalur ke direktori dokumen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buka dokumen PDF

```csharp
// Buka dokumen
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Langkah 3: Gunakan objek DocumentInfo untuk mengakses informasi file dokumen PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Langkah 4: Tetapkan nilai informasi file yang diinginkan menggunakan properti objek DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Langkah 5: Simpan dokumen PDF yang diperbarui ke lokasi yang ditentukan.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Langkah 6: Verifikasi bahwa informasi file telah berhasil diperbarui.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Anda telah berhasil mengatur informasi file untuk dokumen PDF menggunakan Aspose.PDF untuk .NET.

### Contoh kode sumber untuk Mengatur Info File menggunakan Aspose.PDF untuk .NET


```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buka dokumen
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Tentukan informasi dokumen
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// Simpan dokumen keluaran
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Kesimpulan

Kesimpulannya, Aspose.PDF untuk .NET menyediakan cara sederhana dan efektif dalam mengatur informasi file untuk dokumen PDF. Dengan mengikuti langkah-langkah yang disebutkan di atas, Anda dapat dengan mudah mengatur nilai informasi file yang diinginkan untuk dokumen PDF Anda menggunakan kode sumber C#.

### FAQ untuk mengatur info file dalam file PDF

#### T: Dapatkah saya menyetel properti informasi file tambahan yang tidak disebutkan dalam contoh?

 J: Ya, Anda dapat mengatur properti informasi file tambahan menggunakan`DocumentInfo` objek di Aspose.PDF untuk .NET. Itu`DocumentInfo`kelas menyediakan berbagai properti yang memungkinkan Anda mengatur informasi tambahan seperti produsen, versi, dan properti khusus.

#### T: Apakah mungkin untuk mengambil informasi file dari dokumen PDF yang sudah ada?

 J: Ya, Anda dapat mengambil informasi file dari dokumen PDF yang ada menggunakan Aspose.PDF untuk .NET. Untuk melakukan ini, Anda dapat menggunakan`DocumentInfo` objek untuk mengakses properti informasi file dan membaca informasi yang disimpan dalam dokumen PDF.

#### T: Apakah pengaturan informasi file mengubah dokumen PDF asli?

J: Tidak, mengatur informasi file menggunakan Aspose.PDF untuk .NET tidak mengubah dokumen PDF asli. Sebaliknya, ini membuat dokumen PDF baru dengan informasi file yang diperbarui. Dokumen PDF asli tetap tidak berubah.